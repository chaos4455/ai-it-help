**Dockerfile para Helm: Criando Imagens Docker Personalizadas para Cartas do Helm**

**Introdução**

Um Dockerfile é um arquivo de texto que contém instruções para construir uma imagem do Docker. Ele permite criar imagens personalizadas para uso com cartas do Helm, que são pacotes que gerenciam a implantação de aplicativos no Kubernetes.

**Pré-requisitos**

* Docker instalado
* Ambiente de desenvolvimento com acesso a um terminal
* Conhecimento básico de Kubernetes e Helm

**Criando um Dockerfile**

Crie um novo arquivo chamado `Dockerfile` no diretório do seu projeto.

**Instruções do Dockerfile**

**1. Escolha uma Imagem Base**

```
FROM docker.io/library/ubuntu:20.04
```

**2. Instale Pacotes (opcional)**

```
RUN apt-get update && apt-get install -y \
  curl \
  wget \
  unzip
```

**3. Defina Variaveis (opcional)**

```
ENV VAR1=value1
ENV VAR2=value2
```

**4. Copie Arquivos para a Imagem**

```
COPY my-app /usr/local/bin/my-app
```

**5. Defina o Comando de Execução**

```
CMD ["/usr/local/bin/my-app"]
```

**Exemplo de Dockerfile**

```
FROM docker.io/library/ubuntu:20.04

RUN apt-get update && apt-get install -y \
  curl \
  wget \
  unzip

ENV HELM_VERSION=3.10.2
ENV CHART_REPO=https://charts.helm.sh/stable

RUN curl -fsSL -o get_helm.sh \
  https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3

RUN chmod 700 get_helm.sh

RUN ./get_helm.sh

RUN helm repo add stable $CHART_REPO

COPY . /app

WORKDIR /app

CMD ["bin/helm"]
```

**Construindo a Imagem**

No terminal, execute o seguinte comando no diretório do projeto:

```
docker build -t my-helm-image .
```

**Testando a Imagem**

Execute o comando abaixo para executar a imagem:

```
docker run -it --rm my-helm-image
```

**Recursos Adicionais**

* [Documentação do Dockerfile](https://docs.docker.com/engine/reference/builder/)
* [Documentação do Helm](https://helm.sh/docs/)
* [Modelo de Dockerfile para Helm](https://github.com/helm/helm/blob/main/examples/helm-docker/Dockerfile)

**Conclusão**

Criar imagens Docker personalizadas para cartas do Helm permite estender as funcionalidades do Helm e personalizar os ambientes de implantação do Kubernetes. Seguindo as instruções descritas neste manual, você pode criar imagens personalizadas que atendem às necessidades específicas de seus aplicativos.