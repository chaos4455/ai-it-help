## Guia Prático para Criar Imagens Docker Personalizadas para Aplicações Go

**Criando uma Imagem Docker Personalizada**

**Pré-requisitos:**

- Docker instalado
- Go instalado
- Editor de texto

**Passos:**

**1. Criar um arquivo Dockerfile:**

- Crie um arquivo chamado "Dockerfile" no diretório do projeto.

**2. Definir a imagem base:**

- Exemplo: `FROM golang:1.19-buster`
- Selecione a imagem base apropriada para sua aplicação Go.

**3. Copiar o código do projeto:**

- Copie seu código Go para o diretório da imagem Docker:
  - Exemplo: `WORKDIR /app`
  - `COPY . /app`

**4. Instalar dependências:**

- Se sua aplicação Go tiver dependências, instale-as:
  - Exemplo: `RUN go mod download`

**5. Compilar a aplicação:**

- Compile sua aplicação Go:
  - Exemplo: `RUN go build -o main`

**6. Expor porta:**

- Exponha a porta necessária para sua aplicação:
  - Exemplo: `EXPOSE 8080`

**7. Definir o comando de inicialização:**

- Especifique o comando que será executado quando a imagem for iniciada:
  - Exemplo: `CMD ["/app/main"]`

**8. Construir a imagem:**

- Construa a imagem Docker usando o comando:
  - Exemplo: `docker build -t my-go-image .`

**9. Executar a imagem:**

- Execute sua imagem Docker:
  - Exemplo: `docker run -p 8080:8080 my-go-image`

**Dicas Adicionais:**

- Pode ser necessário ajustar as configurações do Dockerfile dependendo da sua aplicação específica.
- Use o comando `docker inspect` para exibir detalhes da imagem Docker.
- Utilize o Docker Hub para armazenar e compartilhar suas imagens Docker.
- Otimize suas imagens Docker usando técnicas como build multiestágio e cache de camadas.