**Capítulo 7: Otimizando Imagens Docker Personalizadas para Desempenho e Segurança**

**7.1 Criando uma Imagem Docker Personalizada**

**1. Criando um Dockerfile**
* Crie um arquivo de texto denominado "Dockerfile" no diretório raiz do seu projeto.
* Especifique a imagem base, comandos e configurações adicionais no Dockerfile.

**2. Utilizando o apt-get**
* Use o comando `RUN apt-get install` para instalar pacotes do sistema operacional na imagem.
* Adicione o sinalizador `-y` para responder automaticamente a prompts.

**3. Utilizando o Docker Compose**
* Crie um arquivo "docker-compose.yml" para definir vários serviços Docker relacionados.
* Use a diretiva `image` para especificar a imagem Docker personalizada.

**4. Imagem de vários estágios**
* Use estágios para dividir o Dockerfile em etapas lógicas.
* Crie um estágio de construção para preparar o ambiente e um estágio de execução para executar o aplicativo.

**5. Adicionando um script de entrada**
* Crie um script de entrada personalizado para executar ações adicionais no contêiner após a inicialização.
* Especifique o script de entrada usando a diretiva `ENTRYPOINT`.

**7.2 Otimizando o Desempenho**

**6. Desativando logs desnecessários**
* Defina o nível de log para `error` ou `warn` usando a variável de ambiente `LOG_LEVEL`.
* Use o comando `logger` para desativar logs de módulos específicos.

**7. Utilizando bibliotecas otimizadas**
* Use bibliotecas compiladas estaticamente, como Alpine Linux, para reduzir o tamanho da imagem.
* Instale apenas as dependências essenciais para o aplicativo.

**8. Utilizando cache de camadas**
* Use o comando `COPY --from` para reutilizar camadas de imagens existentes.
* Cache pacotes do sistema operacional usando o comando `apt-get install -q`.

**9. Minimizando o tamanho da imagem**
* Remova arquivos desnecessários, como arquivos de teste e documentação.
* Use o comando `strip` para remover símbolos de depuração do código executável.

**7.3 Aprimorando a Segurança**

**10. Definindo um usuário não-root**
* Crie um usuário não-root e execute o aplicativo como esse usuário.
* Use a diretiva `USER` no Dockerfile.

**11. Desabilitando o acesso SSH**
* Desabilite o acesso SSH ao contêiner definindo a variável de ambiente `SSH_DISABLE=true`.
* Remova o serviço SSH da imagem.

**12. Utilizando segredos de imagem**
* Armazene credenciais e dados confidenciais em segredos de imagem.
* Use o comando `RUN --mount` para montar os segredos no contêiner.

**13. Adicionando proteção de vulnerabilidade**
* Use ferramentas como o `Clair` para verificar vulnerabilidades de imagem.
* Defina o sinalizador `--security-opts` no comando `docker run` para aplicar políticas de segurança.

**7.4 Melhorias Adicionais**

**14. Automatizando a construção de imagens**
* Use ferramentas como o Jenkins ou o CircleCI para automatizar o processo de construção de imagens.
* Configure gatilhos para iniciar a construção ao fazer alterações no código.

**15. Utilizando o registro privado**
* Armazene imagens Docker personalizadas em um registro privado para maior segurança.
* Use o comando `docker push` para enviar imagens para o registro.

**16. Monitorando contêineres**
* Use ferramentas como o Prometheus ou o Grafana para monitorar o desempenho e a saúde dos contêineres.
* Configure alertas para notificá-lo sobre problemas.

**17. Fazendo o perfil de imagens**
* Use ferramentas como o `docker-profiling` para analisar o desempenho da imagem.
* Identifique gargalos e áreas de melhoria.

**18. Debugging de imagens**
* Use o comando `docker exec` para executar comandos dentro do contêiner.
* Inspecione logs e informações de diagnóstico usando o comando `docker logs`.

**19. Gerenciando vários ambientes**
* Use tags e rótulos para identificar e gerenciar diferentes versões de imagem.
* Defina variáveis de ambiente e parâmetros específicos para cada ambiente.

**20. Melhores práticas gerais**
* Mantenha as imagens atualizadas com as versões mais recentes de software.
* Teste imagens regularmente para verificar se há vulnerabilidades e problemas de desempenho.
* Documente o processo de construção e manutenção de imagens.

**7.5 Exemplos Práticos**

**21. Imagem Docker do Apache com logs desabilitados**
* Dockerfile:

```
FROM apache:latest
RUN logger -s NOTICE -t apache
```

**22. Imagem Docker do Nginx com cache de camada**
* Dockerfile:

```
FROM nginx:latest
COPY --from=alpine:latest /usr/bin/apk /usr/bin/apk
RUN apk update
```

**23. Imagem Docker do MySQL com segredos de imagem**
* Dockerfile:

```
FROM mysql:latest
RUN --mount=type=secret,id=db-secret,dst=/secret mv /secret/database.conf /etc/mysql/mysql.conf.d/
```

**24. Automação da construção de imagens com o GitHub Actions**
* Fluxo de trabalho do GitHub Actions:

```
name: Docker Image Build

on:
  push:
    branches:
      - main

jobs:
  build-image:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: docker/setup-buildx-action@v2
      - run: docker buildx build --push --platform linux/amd64,linux/arm64 -t ghcr.io/my-repo/my-image .
```

**Conclusão**

Otimizar imagens Docker personalizadas é crucial para melhorar o desempenho e a segurança. Ao seguir as práticas recomendadas e implementar as técnicas descritas neste manual, você pode criar imagens Docker eficientes e robustas que atendem aos seus requisitos específicos.