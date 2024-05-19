###### ![config user] Configurando Usuários e Diretórios Base para Ambientes de Microsserviços

### 📝 Visão Geral

* Os microsserviços geralmente são executados em contêineres ou VMs, que precisam de usuários e diretórios base configurados para operações seguras e eficientes.
* Esta seção fornece instruções detalhadas sobre como configurar usuários e diretórios base para microsserviços.

### 🏗️ Pré-requisitos

* Ambiente de microsserviços existente com containers ou VMs implantados
* Acesso ao sistema operacional host (por exemplo, Linux)
* Privilégios de superusuário (por exemplo, sudo)

### 👨‍💻 Criando um Usuário para Microsserviços

**Passo 1: Criar um novo usuário**

```bash
sudo useradd -m -s /bin/bash microservice_user
```

* `-m`: Cria um diretório home para o usuário.
* `-s`: Define o shell padrão para o usuário.

**Passo 2: Definir uma senha**

```bash
sudo passwd microservice_user
```

**Passo 3: Adicionar o usuário ao grupo sudo**

```bash
sudo usermod -aG sudo microservice_user
```

### 📂 Configurando Diretórios Base

**Passo 1: Criar um diretório base para os dados do microsserviço**

```bash
sudo mkdir /opt/microservice_data
```

**Passo 2: Definir permissões para o diretório base**

```bash
sudo chown microservice_user:microservice_user /opt/microservice_data
sudo chmod 755 /opt/microservice_data
```

* `chown`: Altera o proprietário e o grupo do diretório.
* `chmod`: Define as permissões de acesso ao diretório.

**Passo 3: Criar diretórios de log**

```bash
sudo mkdir -p /opt/microservice_data/logs
sudo chown microservice_user:microservice_user /opt/microservice_data/logs
sudo chmod 755 /opt/microservice_data/logs
```

### 🛠️ Configurando Contêineres

**Passo 1: Definir o usuário e o diretório base nos arquivos de contêiner**

* Para contêineres Docker, adicione o seguinte ao arquivo `Dockerfile`:

```docker
USER microservice_user
WORKDIR /opt/microservice_data
```

* Para contêineres Kubernetes, defina o usuário e o diretório base no manifesto `yaml`:

```yaml
containers:
  - name: my-microservice
    image: my-image
    user: microservice_user
    workingDir: /opt/microservice_data
```

### ⚖️ Configurando VMs

**Passo 1: Definir o usuário e o diretório base no script de provisionamento da VM**

* Para VMs provisionadas com Ansible, adicione o seguinte ao playbook:

```ansible
- name: Create microservice user
  user:
    name: microservice_user
    groups: sudo
    shell: /bin/bash
    append: yes

- name: Create microservice data directory
  file:
    path: /opt/microservice_data
    state: directory
    owner: microservice_user
    group: microservice_user
    mode: 0755
```

* Para VMs provisionadas com Terraform, adicione o seguinte ao módulo:

```terraform
resource "local_user" "microservice_user" {
  name = "microservice_user"
  home_dir = "/opt/microservice_data"
  groups = ["sudo"]
}

resource "directory" "microservice_data" {
  path = "/opt/microservice_data"
  owner = "microservice_user"
  group = "microservice_user"
  mode = "755"
}
```

### 💡 Dicas Adicionais

* Mantenha o usuário e o diretório base consistentes em todos os contêineres e VMs.
* Use variáveis de ambiente para especificar o diretório base, permitindo alterações fáceis.
* Considere criar vários usuários para diferentes tipos de microsserviços ou fins.
* Implemente medidas de segurança adicionais, como gerenciamento de acesso baseado em função (RBAC) e criptografia.
* Monitore e registre todas as alterações feitas nos usuários e diretórios base.