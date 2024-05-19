**Notion: Dockerfile para MySQL: Criando Imagens Docker Personalizadas para Instâncias de MySQL**

**Introdução**

Docker é uma plataforma que nos permite criar, implantar e executar aplicativos em contêineres, que são ambientes isolados que contêm todo o código, bibliotecas e dependências necessárias para executar um aplicativo. Neste manual, aprenderemos a criar imagens Docker personalizadas para instâncias do MySQL usando um Dockerfile.

**Pré-requisitos**

* Docker instalado em seu sistema
* Uma máquina host executando Linux ou macOS
* Conhecimento básico de comandos do Docker

**Passos**

**1. Crie um diretório de trabalho:**

Inicie criando um diretório de trabalho para armazenar o Dockerfile e outros arquivos de configuração:

```
mkdir mysql-dockerfile
cd mysql-dockerfile
```

**2. Crie um arquivo Dockerfile:**

Dentro do diretório de trabalho, crie um arquivo chamado `Dockerfile` sem extensão:

```
touch Dockerfile
```

**3. Defina a imagem base:**

Na primeira linha do Dockerfile, especifique a imagem base que usaremos para construir nossa imagem personalizada. Para MySQL, usaremos a imagem oficial do MySQL:

```
FROM mysql:8
```

**4. Defina as variáveis de ambiente:**

Definiremos algumas variáveis de ambiente para personalizar a configuração do MySQL:

```
ENV MYSQL_ROOT_PASSWORD=root_password
ENV MYSQL_DATABASE=my_database
ENV MYSQL_USER=my_user
ENV MYSQL_PASSWORD=user_password
```

**5. Crie o banco de dados e o usuário:**

Execute os comandos a seguir para criar o banco de dados, o usuário e conceder privilégios ao usuário:

```
RUN set -ex; \
    && echo '[client]' > /etc/mysql/conf.d/my_custom.cnf; \
    && echo "user=$MYSQL_ROOT_PASSWORD" >> /etc/mysql/conf.d/my_custom.cnf; \
    && echo 'password=$MYSQL_ROOT_PASSWORD' >> /etc/mysql/conf.d/my_custom.cnf; \
    && mysql --defaults-extra-file=/etc/mysql/conf.d/my_custom.cnf -u root -p"$MYSQL_ROOT_PASSWORD" -e "CREATE DATABASE IF NOT EXISTS $MYSQL_DATABASE;"; \
    && mysql --defaults-extra-file=/etc/mysql/conf.d/my_custom.cnf -u root -p"$MYSQL_ROOT_PASSWORD" -e "CREATE USER IF NOT EXISTS '$MYSQL_USER'@'%' IDENTIFIED BY '$MYSQL_PASSWORD';"; \
    && mysql --defaults-extra-file=/etc/mysql/conf.d/my_custom.cnf -u root -p"$MYSQL_ROOT_PASSWORD" -e "GRANT ALL PRIVILEGES ON $MYSQL_DATABASE.* TO '$MYSQL_USER'@'%';"; \
    && mysql --defaults-extra-file=/etc/mysql/conf.d/my_custom.cnf -u root -p"$MYSQL_ROOT_PASSWORD" -e "FLUSH PRIVILEGES;"
```

**6. Exponha a porta:**

Exponha a porta 3306 do contêiner para permitir conexões externas ao banco de dados:

```
EXPOSE 3306
```

**7. Defina o comando de entrada:**

O comando de entrada especifica o comando que será executado quando o contêiner for iniciado. No nosso caso, iniciaremos o servidor MySQL:

```
CMD ["mysqld"]
```

**Build da Imagem**

**1. Construa a imagem:**

Use o comando `docker build` para construir a imagem Docker:

```
docker build -t my-custom-mysql .
```

**2. Execute o contêiner:**

Execute o contêiner usando o comando `docker run`:

```
docker run -d --name my-custom-mysql -p 3306:3306 my-custom-mysql
```

**3. Teste a conexão:**

Use um cliente MySQL para testar a conexão com o banco de dados:

```
mysql -u my_user -puser_password -h localhost -P 3306 my_database
```

**Personalizações Adicionais**

**1. Instalar extensões:**

Você pode instalar extensões MySQL adicionais usando o comando `apt-get`:

```
RUN apt-get update && apt-get install -y mysql-server-my_extension
```

**2. Configurar parâmetros:**

Você pode configurar parâmetros de desempenho e outros parâmetros do MySQL adicionando linhas ao arquivo `/etc/mysql/my.cnf`:

```
RUN echo "max_connections=100" >> /etc/mysql/my.cnf
```

**3. Adicionar scripts de inicialização:**

Você pode executar scripts personalizados quando o contêiner for iniciado adicionando-os ao diretório `/docker-entrypoint-initdb.d/`:

```
COPY init-script.sql /docker-entrypoint-initdb.d/
```

**Conclusão**

Neste manual, aprendemos a criar imagens Docker personalizadas para instâncias do MySQL usando um Dockerfile. Essa abordagem permite personalizar as configurações do MySQL, instalar extensões e executar scripts de inicialização, tornando mais fácil implantar e gerenciar bancos de dados do MySQL em contêineres.