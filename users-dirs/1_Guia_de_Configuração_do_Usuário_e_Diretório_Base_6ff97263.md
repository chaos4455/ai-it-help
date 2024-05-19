**Guia de Configuração do Usuário e Diretório Base**

**Capítulo 3: Configurando um Usuário e Diretório Base**

**Introdução**

Este capítulo fornecerá instruções passo a passo sobre como criar um novo usuário e configurar seu diretório base em um sistema operacional. Um diretório base é um diretório de nível superior que serve como ponto de partida para todos os outros diretórios e arquivos do usuário.

**Objetivos**

Ao concluir este capítulo, você será capaz de:

- Criar um novo usuário
- Definir um diretório base para o usuário
- Alterar o diretório base de um usuário
- Gerenciar permissões do diretório base

**Materiais Necessários**

- Conta de usuário com privilégios administrativos
- Acesso a um terminal ou prompt de comando

**Instruções**

**Criando um Novo Usuário**

1. **Abra o terminal ou prompt de comando:** O método varia dependendo do sistema operacional.
2. **Digite o comando para criar o usuário:**

   - Linux: `useradd nome_do_usuario`
   - Windows: `net user nome_do_usuario senha /add`
   - macOS: `sudo dscl . -create /Users/nome_do_usuario`

3. **Pressione Enter:** O sistema solicitará informações adicionais, como senha e detalhes do perfil.

**Definindo um Diretório Base**

1. **Use o comando para criar o diretório base:**

   - Linux: `mkdir /home/nome_do_usuario`
   - Windows: Crie uma pasta no diretório "Usuários" com o nome do usuário.
   - macOS: `sudo mkdir /Users/nome_do_usuario`

2. **Defina o diretório base do usuário:**

   - Linux: `usermod -d /home/nome_do_usuario nome_do_usuario`
   - Windows: Use o Editor do Registro para definir o valor "HomeDirectory" na subchave "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList\"nome_do_usuário\".
   - macOS: `sudo dscl . -create /Users/nome_do_usuario UserShell /bin/bash`
     ```
     sudo dscl . -create /Users/nome_do_usuario NFSHomeDirectory /Users/nome_do_usuario
     ```

**Alterando o Diretório Base**

1. **Siga as mesmas etapas para definir um diretório base, mas use um novo caminho:**
   - Linux: `usermod -d novo_diretorio_base nome_do_usuario`
   - Windows: Modifique o valor "HomeDirectory" no Editor do Registro conforme mencionado acima.
   - macOS: `sudo dscl . -create /Users/nome_do_usuario NFSHomeDirectory novo_diretorio_base`

**Gerenciando Permissões do Diretório Base**

1. **Use as seguintes permissões de diretório padrão:**

   - Propriedade: Usuário
   - Grupo: Usuário
   - Outras: Sem acesso

2. **Configure as permissões apropriadas:**

   - Linux: `chmod 700 diretorio_base`
   - Windows: Use a GUI ou o comando `icacls` para definir as permissões.
   - macOS: `chmod 700 diretorio_base`

**Conclusão**

Seguir as etapas descritas neste capítulo permitirá que você crie e gerencie usuários e diretórios base efetivamente. Depois que um usuário for criado, ele poderá acessar seu próprio diretório base e armazenar arquivos e diretórios pessoais.