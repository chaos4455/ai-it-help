## Criação de Imagens Docker Personalizadas 🐳

### Introdução

As imagens Docker personalizadas permitem otimizar e estender os recursos do Docker para atender às necessidades específicas do seu aplicativo. Este guia irá guiá-lo pelo processo de criação de imagens Docker personalizadas, desde a preparação do seu ambiente até a implantação da imagem final.

### Pré-Requisitos 🔧

- Ambiente de desenvolvimento com Docker instalado (Docker Desktop recomendado)
- Texto editor (por exemplo, VSCode, Sublime Text)
- Conhecimento básico de Docker

### 1. Preparação do Ambiente 🛠️

- Crie um diretório para o seu projeto de aplicativo
- Crie um arquivo **Dockerfile** dentro do diretório

### 2. Escrevendo o Dockerfile 📝

**Estrutura Básica:**

```
FROM <base-image>
[INSTRUCTIONS]
[RUN COMMANDS]
[EXPOSE PORTS]
[CMD OR ENTRYPOINT]
```

**Informações detalhadas:**

- **FROM:** especifica a imagem base para a sua imagem personalizada.
- **INSTRUCTIONS:** diretrizes para construir a imagem, como **ENV**, **COPY** e **RUN**.
- **RUN COMMANDS:** comandos executados durante a construção da imagem.
- **EXPOSE PORTS:** expõe as portas que o aplicativo escutará dentro do contêiner.
- **CMD OR ENTRYPOINT:** especifica o comando padrão a ser executado quando o contêiner é iniciado.

### 3. Construindo a Imagem 🏗️

```
docker build -t <image-name> .
```

- **-t <image-name>:** atribui um nome à imagem construída.

### 4. Imprimindo a Imagem 🖼️

```
docker images
```

- Exibe uma lista de imagens Docker disponíveis, incluindo a sua imagem personalizada.

### 5. Executando o Contêiner 🏃‍♂️

```
docker run -p <host-port>:<container-port> <image-name>
```

- **-p <host-port>:<container-port>:** mapeia uma porta externa para a porta do contêiner.

### 6. Gerenciando Contêineres 📦

**Iniciar:**

```
docker start <container-id>
```

**Parar:**

```
docker stop <container-id>
```

**Reiniciar:**

```
docker restart <container-id>
```

**Remover:**

```
docker rm <container-id>
```

### 7. Gerenciando Imagens 🧹

**Listar imagens:**

```
docker images
```

**Remover imagens:**

```
docker rmi <image-id>
```

### 8. Exemplos Avançados ✨

**Usando vários estágios**:

- Cria imagens intermediárias para otimizar a construção.

**Usando volumes**:

- Compartilha dados entre o contêiner e o host.

**Usando scripts de inicialização**:

- Executa tarefas personalizadas na inicialização do contêiner.

**Configurando a rede**:

- Personaliza a configuração de rede do contêiner.

### Recursos Adicionais 📚

- [Docker Hub](https://hub.docker.com/)
- [Documentação Oficial do Docker](https://docs.docker.com/)
- [Tutorial do Docker](https://docker-docs.netlify.app/)

### Conclusão 🎉

A criação de imagens Docker personalizadas permite adaptar o contêiner às suas necessidades específicas de aplicativo, melhorando o desempenho, a segurança e a portabilidade. Ao seguir as etapas descritas neste guia, você pode criar imagens Docker personalizadas eficientes e otimizadas para seus projetos de software.