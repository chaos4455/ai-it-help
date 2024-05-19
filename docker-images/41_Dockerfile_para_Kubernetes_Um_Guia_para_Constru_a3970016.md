## 🚢 Dockerfile para Kubernetes: Construindo Imagens Docker Personalizadas

**Introdução:** ✨

* O Dockerfile é um script usado para construir imagens Docker.
* No contexto do Kubernetes, as imagens Docker personalizadas permitem que você implante e execute aplicativos personalizados em seu cluster Kubernetes.

### 1. Criando uma Imagem Docker Personalizada

**Pré-requisitos:** 🔨

* Instalação do Docker Engine
* Ferramenta de linha de comando Kubernetes (kubectl)

**Passo a Passo:** 👣

1. **Crie um Diretório para o Projeto:** 📂
   - Crie um novo diretório para seu projeto Docker.

2. **Crie um Dockerfile:** 📄
   - Crie um arquivo chamado `Dockerfile` no diretório do projeto.

3. **Especificando a Imagem Base:** 🐳
   - A primeira linha do Dockerfile especifica a imagem base sobre a qual você construirá sua imagem personalizada.
   - Por exemplo: `FROM nginx`

4. **Copiando Arquivos para a Imagem:** 📦
   - Use a instrução `COPY` para copiar arquivos ou diretórios do host para a imagem.
   - Por exemplo: `COPY index.html /usr/share/nginx/html`

5. **Executando Comandos:** 🛠️
   - A instrução `RUN` executa comandos dentro do contêiner.
   - Por exemplo: `RUN apt-get update && apt-get install -y python3`

6. **Definindo a Porta de Exposição:** 🌐
   - Use a instrução `EXPOSE` para especificar a porta que será exposta pelo contêiner.
   - Por exemplo: `EXPOSE 80`

7. **Definindo o Comando de Inicialização:** 🚢
   - A instrução `CMD` define o comando a ser executado quando o contêiner iniciar.
   - Por exemplo: `CMD ["nginx", "-g", "daemon off;"]`

8. **Construindo a Imagem:** 👷‍♀️
   - Execute o seguinte comando para construir a imagem Docker:
   `docker build -t <nome-da-imagem> <caminho-do-Dockerfile>`

### 2. Testando sua Imagem Localmente 🧪

1. **Executando o Contêiner:** 💪
   - Execute o seguinte comando para executar o contêiner localmente:
   `docker run -p 8080:80 <nome-da-imagem>`

2. **Testando o Contêiner:** 🌐
   - Abra seu navegador e visite `http://localhost:8080` para verificar se o contêiner está funcionando conforme o esperado.

### 3. Empurrando a Imagem para um Registro 🌐

1. **Fazer Login no Registro:** 🔑
   - Se você estiver usando o Docker Hub, execute:
   `docker login`

2. **Fazendo Tag na Imagem:** 🏷️
   - Use o seguinte comando para fazer tag na imagem com o nome do registro:
   `docker tag <nome-da-imagem> <nome-do-registro>/<nome-da-imagem>`

3. **Empurrando a Imagem:** 📤
   - Execute o seguinte comando para empurrar a imagem para o registro:
   `docker push <nome-do-registro>/<nome-da-imagem>`

### 4. Implantando a Imagem em Kubernetes ✨

1. **Criando um Deployment:** 🚢
   - Crie um arquivo de implantação do Kubernetes chamado `deployment.yaml`.
   - Especifique o nome da imagem, o número de réplicas e as portas de contêiner.

2. **Aplicando a Implantação:** 🛠️
   - Execute o seguinte comando para aplicar a implantação:
   `kubectl apply -f deployment.yaml`

3. **Verificando a Implantação:** 👀
   - Execute o seguinte comando para verificar a implantação:
   `kubectl get deployments`

4. **Expondo o Serviço:** 🌐
   - Crie um arquivo de serviço do Kubernetes chamado `service.yaml`.
   - Especifique o nome do serviço e a porta que será exposta.

5. **Aplicando o Serviço:** ⚙️
   - Execute o seguinte comando para aplicar o serviço:
   `kubectl apply -f service.yaml`

6. **Verificando o Serviço:** 👀
   - Execute o seguinte comando para verificar o serviço:
   `kubectl get services`

### 📚 Recursos Adicionais:

* [Documentação do Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
* [Introdução ao Kubernetes](https://kubernetes.io/docs/concepts/)
* [Implantação e Gerenciamento de Contêineres no Kubernetes](https://www.udemy.com/course/kubernetes-for-beginners/)