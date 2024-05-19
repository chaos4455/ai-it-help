**Dockerfile para OpenTelemetry: Um Guia para Construir Imagens Docker Personalizadas para Instâncias de OpenTelemetry**

**Objetivo:**

* Criar uma imagem Docker personalizada que contenha um agente OpenTelemetry configurado.

**Pré-requisitos:**

* Docker instalado
* Conhecimento básico de Dockerfiles

**Passos:**

**1. Criar um Novo Dockerfile**

* Crie um novo arquivo chamado `Dockerfile` no diretório do projeto.

**2. Especificar a Imagem Base**

* Indique a imagem base do Docker a ser usada, como:
```
FROM openjdk:8-jdk-slim
```

**3. Instalar o Agente OpenTelemetry**

* Instale o agente OpenTelemetry usando o gerenciador de pacotes:
```
RUN apt-get update && apt-get install -y opentelemetry-java
```

**4. Configurar o Agente OpenTelemetry**

* Crie um arquivo de configuração (`otel-config.yaml`) para o agente:
```
LABEL com.google.cloud.opentelemetry.agent.configure-jaeger=./otel-config.yaml
```

**5. Criar o Arquivo de Configuração do Jaeger**

* Adicione um arquivo de configuração para o coletor Jaeger ao diretório do projeto:
```
# otel-config.yaml
service:
  name: otel-demo
  attributes:
    otel.traces.sampled: true # Amostragem de todos os spans
  spanLimits:
    maxNumberOfAttributes: 100
    maxNumberOfEvents: 100
    maxNumberOfLinks: 100
exporter:
  jaeger:
    protocol: grpc
    endpoint: jaeger:14250 # Endereço do coletor Jaeger
traces:
  sampler: always_on
```

**6. Copiar os Arquivos de Configuração para a Imagem**

* Copie os arquivos de configuração para a imagem do Docker:
```
COPY otel-config.yaml /otel-config.yaml
```

**7. Executar o Agente OpenTelemetry**

* Execute o agente OpenTelemetry usando o comando:
```
CMD ["java", "-javaagent:/opentelemetry-api-all.jar", "-jar", "app.jar"]
```

**Exemplo de Dockerfile Completo:**

```
FROM openjdk:8-jdk-slim

RUN apt-get update && apt-get install -y opentelemetry-java

LABEL com.google.cloud.opentelemetry.agent.configure-jaeger=./otel-config.yaml

COPY otel-config.yaml /otel-config.yaml

CMD ["java", "-javaagent:/opentelemetry-api-all.jar", "-jar", "app.jar"]
```

**Conclusão:**

Seguindo esses passos, você pode criar uma imagem Docker personalizada que contém um agente OpenTelemetry configurado. Isso permite que você monitore e trace seus aplicativos instrumentados com o OpenTelemetry.