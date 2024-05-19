## 📝 Configurando Usuários e Diretórios Base para Ambientes de Nuvem

### 1️⃣ Introdução

No gerenciamento de nuvem, os usuários e os diretórios base são cruciais para controlar o acesso e criar ambientes organizados. Este manual fornecerá orientação abrangente para configurar usuários e diretórios base em vários ambientes de nuvem.

### 2️⃣ Configurando um Usuário

#### 2.1️⃣ Azure Active Directory (Azure AD)

1. Acesse o portal do Azure e selecione **"Azure Active Directory"**.
2. Clique em **"Novo usuário"**.
3. Insira as informações do usuário, como nome, e-mail e número de telefone.
4. Defina uma senha strong.
5. Clique em **"Criar"**.

#### 2.2️⃣ AWS Identity and Access Management (IAM)

1. Acesse o Console de Gerenciamento da AWS e selecione **"IAM"**.
2. Clique em **"Usuários"**.
3. Clique em **"Adicionar um usuário"**.
4. Insira as informações do usuário e defina uma senha strong.
5. Clique em **"Criar"**.

#### 2.3️⃣ Google Cloud Platform (GCP)

1. Acesse o Console do GCP e selecione **"IAM e Administração"**.
2. Clique em **"IAM"**.
3. Clique em **"Adicionar"**.
4. Insira as informações do usuário e defina uma senha strong.
5. Clique em **"Criar"**.

### 3️⃣ Configurando um Diretório Base

#### 3.1️⃣ Azure AD

1. Acesse o portal do Azure e selecione **"Azure Active Directory"**.
2. Clique em **"Domínios"**.
3. Clique em **"Adicionar um domínio personalizado"**.
4. Insira o nome do domínio e verifique se você possui os registros DNS necessários.
5. Clique em **"Adicionar domínio"**.

#### 3.2️⃣ AWS IAM

1. Acesse o Console de Gerenciamento da AWS e selecione **"IAM"**.
2. Clique em **"Diretórios"**.
3. Clique em **"Criar diretório"**.
4. Insira as informações do diretório, como nome e descrição.
5. Clique em **"Criar diretório"**.

#### 3.3️⃣ GCP

1. Acesse o Console do GCP e selecione **"IAM e Administração"**.
2. Clique em **"Domínios"**.
3. Clique em **"Adicionar um domínio"**.
4. Insira o nome do domínio e verifique se você possui os registros DNS necessários.
5. Clique em **"Adicionar domínio"**.

### 4️⃣ Conectando Usuários aos Diretórios Base

#### 4.1️⃣ Azure AD

1. Acesse o portal do Azure e selecione **"Azure Active Directory"**.
2. Clique em **"Usuários"**.
3. Selecione o usuário que deseja conectar ao diretório base.
4. Clique em **"Perfil"**.
5. Na seção **"Domínio"**, selecione o diretório base.

#### 4.2️⃣ AWS IAM

1. Acesse o Console de Gerenciamento da AWS e selecione **"IAM"**.
2. Clique em **"Usuários"**.
3. Selecione o usuário que deseja conectar ao diretório base.
4. Clique em **"Detalhes"**.
5. Na seção **"Diretório"**, selecione o diretório base.

#### 4.3️⃣ GCP

1. Acesse o Console do GCP e selecione **"IAM e Administração"**.
2. Clique em **"IAM"**.
3. Selecione o usuário que deseja conectar ao diretório base.
4. Clique em **"Editar"**.
5. Na seção **"Domínio do usuário"**, selecione o diretório base.

### 5️⃣ Gerenciando Usuários e Diretórios Base

#### 5.1️⃣ Azure AD

* Gerencie usuários: portal do Azure ou PowerShell
* Gerencie diretórios base: portal do Azure ou PowerShell

#### 5.2️⃣ AWS IAM

* Gerencie usuários: Console de Gerenciamento da AWS, CLI da AWS ou SDK da AWS
* Gerencie diretórios base: Console de Gerenciamento da AWS ou CLI da AWS

#### 5.3️⃣ GCP

* Gerencie usuários: Console do GCP, gcloud ou API do Google Identity
* Gerencie diretórios base: Console do GCP ou gcloud