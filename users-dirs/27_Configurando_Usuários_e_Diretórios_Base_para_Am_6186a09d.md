**Configuração de Usuários e Diretórios Base para Ambientes Multilocatários**

**Seção 3: Configurando um Usuário e Diretório Base**

**Objetivo:**

* Criar um novo usuário multilocatário com os privilégios apropriados
* Configurar o diretório base que servirá como o diretório principal para os usuários multilocatários

**Pré-requisitos:**

* Uma conta de administrador global no Microsoft 365
* Conhecimento básico dos conceitos de gerenciamento de usuários e diretório do Microsoft 365

**Passo a Passo:**

**1. Criando um Novo Usuário Multilocatário**

* Acesse o Centro de Administração do Microsoft 365 (https://admin.microsoft.com) com sua conta de administrador global.
* Navegue até **Usuários** > **Usuários ativos**.
* Clique em **Novo usuário**.
* Forneça as informações necessárias para o usuário, incluindo **Nome de usuário**, **Nome de exibição** e **Senha**.
* Selecione a opção **Usuário multilocatário**.
* Clique em **Criar**.

**2. Configurando o Diretório Base**

* No Centro de Administração do Microsoft 365, navegue até **Configurações** > **Organizações conectadas**.
* Clique em **Adicionar diretório**.
* Selecione **Criar um novo diretório**.
* Forneça um **Nome do locatário** e **Nome de domínio do locatário**.
* Clique em **Avançar**.
* Configure outras opções conforme necessário, como **Segurança de domínio**, **Integração do Azure AD Connect** e **Sincronização de senha do diretório**.
* Clique em **Criar**.

**3. Atribuindo Privilégios ao Usuário Multilocatário**

* No Centro de Administração do Microsoft 365, navegue até **Usuários** > **Usuários ativos**.
* Localize o usuário multilocatário que você criou.
* Clique no usuário para abrir a página de detalhes.
* Navegue até a guia **Funções**.
* Atribua os privilégios apropriados ao usuário, como **Administrador Global**.
* Clique em **Salvar alterações**.

**4. Adicionando o Diretório Base à Conta do Usuário**

* Acesse o **Azure Active Directory** em https://portal.azure.com.
* Faça login com sua conta de administrador global.
* Navegue até **Azure Active Directory** > **Organizações conectadas**.
* Selecione o diretório base que você criou anteriormente.
* Clique em **Membros**.
* Clique em **Adicionar membros**.
* Pesquise e selecione o usuário multilocatário que você criou.
* Clique em **Adicionar**.

**5. Confirmando a Configuração**

* Faça login no diretório base usando as credenciais do usuário multilocatário.
* Verifique se o usuário tem os privilégios apropriados e se pode acessar os recursos do diretório.

**Dicas:**

* Use senhas fortes e únicas para os usuários multilocatários.
* Revise regularmente os privilégios dos usuários multilocatários para garantir que eles tenham apenas as permissões necessárias.
* Implemente políticas de gerenciamento de acesso privilegiado para controlar o acesso a recursos confidenciais.
* Monitore as atividades dos usuários multilocatários para detectar quaisquer atividades suspeitas.
* Considere usar ferramentas de segurança para aprimorar a proteção do seu ambiente multilocatário.

**Ícones e Emojis:**

* :bust_in_silhouette: - Usuário
* :earth_americas: - Diretório Base
* :gear: - Configurações
* :lock: - Privilégios
* :white_check_mark: - Concluído