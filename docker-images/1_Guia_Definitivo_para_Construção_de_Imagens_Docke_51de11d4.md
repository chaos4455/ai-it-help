**Guia Definitivo para Construir Imagens Docker Personalizadas**

**1. Criando uma Imagem Docker Personalizada**

### Pré-requisitos

- Docker instalado
- Editor de texto (por exemplo, Visual Studio Code)

### Passos

**1. Criar um Diretório para a Imagem**

- Crie um novo diretório para armazenar os arquivos da imagem Docker.

```
mkdir my-image
```

**2. Criar um Arquivo Dockerfile**

- Dentro do diretório da imagem, crie um arquivo chamado `Dockerfile`.

**3. Escolher uma Imagem Base**

- A primeira linha do `Dockerfile` especifica a imagem base sobre a qual sua imagem personalizada será construída.
- Por exemplo, para uma imagem base do Ubuntu:

```
FROM ubuntu:latest
```

**4. Configurar o Usuário**

- Especifique o usuário que executará os comandos no contêiner.
- Por exemplo, para executar como usuário `root`:

```
USER root
```

**5. Instalar Dependências**

- Use o comando `RUN` para instalar dependências.
- Por exemplo, para instalar o Python:

```
RUN apt-get update && apt-get install -y python3-pip
```

**6. Copiar o Código**

- Use o comando `COPY` para copiar o código do aplicativo para o contêiner.
- Por exemplo, para copiar o diretório `app` do diretório atual:

```
COPY app /app
```

**7. Instalar Dependências do Código**

- Use o comando `RUN` novamente para instalar quaisquer dependências específicas do código.
- Por exemplo, para instalar uma biblioteca Python:

```
RUN pip install -r requirements.txt
```

**8. Definir o Comando de Inicialização**

- Especifique o comando que será executado quando o contêiner for iniciado.
- Por exemplo, para executar um servidor da web:

```
CMD ["python", "app.py"]
```

**9. Construir a Imagem**

- Execute o seguinte comando no diretório da imagem:

```
docker build -t my-image .
```

**10. Executar o Contêiner**

- Para executar o contêiner com a imagem personalizada:

```
docker run -it --rm --name my-container my-image
```