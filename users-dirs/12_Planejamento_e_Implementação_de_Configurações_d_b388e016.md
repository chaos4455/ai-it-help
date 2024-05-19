**Capítulo 3: Configurando Usuários e Diretórios Base**

**Introdução:**

Estabelecer usuários e diretórios base é crucial para gerenciar e organizar sistemas de forma eficaz. Este guia fornecerá instruções detalhadas para configurar usuários e diretórios base em um ambiente Linux.

**Objetivos:**

Ao concluir este capítulo, você será capaz de:

- Criar e gerenciar usuários
- Configurar diretórios base do usuário
- Definir opções de login
- Atribuir permissões de diretório

**Pré-requisitos:**

- Acesso de root a um sistema Linux
- Uma compreensão básica da linha de comando

**Seção 1: Criação e Gerenciamento de Usuários**

**1. Criando um Novo Usuário:**

```
useradd nome_do_usuario
```

* Adiciona um novo usuário com o nome de usuário especificado.

**2. Definindo uma Senha:**

```
passwd nome_do_usuario
```

* Define uma senha para o novo usuário.

**3. Adicionando o Usuário a um Grupo:**

```
usermod -aG nome_do_grupo nome_do_usuario
```

* Adiciona o usuário ao grupo especificado.

**4. Excluindo um Usuário:**

```
userdel nome_do_usuario
```

* Remove o usuário do sistema.

**5. Bloqueando e Desbloqueando um Usuário:**

```
usermod -L nome_do_usuario
```

* Bloqueia o usuário.

```
usermod -U nome_do_usuario
```

* Desbloqueia o usuário.

**Seção 2: Configurando Diretórios Base de Usuário**

**6. Definindo o Diretório Base:**

```
usermod -d /caminho/para/diretorio_base nome_do_usuario
```

* Define o diretório base para o usuário especificado.

**7. Criando o Diretório Base:**

Se o diretório base não existir, crie-o usando:

```
mkdir /caminho/para/diretorio_base
```

**8. Definindo Propriedade e Permissões:**

```
 chown nome_do_usuario:nome_do_grupo /caminho/para/diretorio_base
 chmod 755 /caminho/para/diretorio_base
```

* Define o proprietário e o grupo e as permissões para o diretório base.

**Seção 3: Definindo Opções de Login**

**9. Modificando o Shell Padrão:**

```
chsh -s /bin/bash nome_do_usuario
```

* Altera o shell padrão para bash.

**10. Definindo Variáveis de Ambiente:**

```
export VARIAVEL=VALOR
```

* Define uma variável de ambiente para o usuário.

**11. Criando um Arquivo .bashrc:**

```
touch ~/.bashrc
```

* Cria um arquivo .bashrc para armazenar comandos personalizados.

**12. Configurando o Prompt:**

```
PS1="\u@\h \W\$"
```

* Personaliza o prompt do shell.

**Seção 4: Atribuindo Permissões de Diretório**

**13. Definindo Permissões de Subdiretório:**

```
chmod 700 /caminho/para/subdiretorio
```

* Restrição de acesso de leitura, gravação e execução para o proprietário.

**14. Atribuindo Permissões de Grupo:**

```
chmod 660 /caminho/para/diretorio
```

* Concede acesso de leitura e gravação ao proprietário e ao grupo.

**15. Permitindo Acesso de Leitura a Todos:**

```
chmod 444 /caminho/para/arquivo
```

* Concede acesso de leitura somente a todos os usuários.

**16. Definindo Permissões Recursivas:**

```
find /caminho/para/diretorio -type d -exec chmod 755 {} +
```

* Define recursivamente as permissões de diretório para 755.

**17. Usando o Comando Chown:**

```
chown user:group /caminho/para/arquivo
```

* Altera o proprietário e o grupo de um arquivo.

**18. Atribuindo Permissões Especiais:**

```
chmod a+x /caminho/para/arquivo
```

* Concede permissão de execução para todos os usuários.

**19. Revogando Permissões:**

```
chmod a-r /caminho/para/arquivo
```

* Revoga permissão de leitura para todos os usuários.

**Seção 5: Tarefas Adicionais**

**20. Criando um Grupo:**

```
groupadd nome_do_grupo
```

* Cria um novo grupo.

**21. Adicionando um Usuário a um Grupo:**

```
gpasswd -a nome_do_usuario nome_do_grupo
```

* Adiciona um usuário ao grupo especificado.

**22. Removendo um Usuário de um Grupo:**

```
gpasswd -d nome_do_usuario nome_do_grupo
```

* Remove um usuário do grupo especificado.

**23. Excluindo um Grupo:**

```
groupdel nome_do_grupo
```

* Remove o grupo do sistema.

**24. Criando um Subdiretório:**

```
mkdir /caminho/para/subdiretorio
```

* Cria um subdiretório dentro de um diretório existente.

**25. Renomeando um Subdiretório:**

```
mv /caminho/para/subdiretorio_antigo /caminho/para/subdiretorio_novo
```

* Renomeia um subdiretório.

**26. Removendo um Subdiretório:**

```
rmdir /caminho/para/subdiretorio
```

* Remove um subdiretório vazio.

**27. Criando um Arquivo:**

```
touch /caminho/para/arquivo
```

* Cria um arquivo vazio.

**28. Renomeando um Arquivo:**

```
mv /caminho/para/arquivo_antigo /caminho/para/arquivo_novo
```

* Renomeia um arquivo.

**29. Removendo um Arquivo:**

```
rm /caminho/para/arquivo
```

* Remove um arquivo.

**Seção 6: Recapitulação e Próximas Etapas**

**30. Recapitulação:**

Neste capítulo, você aprendeu a criar e gerenciar usuários, configurar diretórios base de usuários, definir opções de login e atribuir permissões de diretório.

**31. Próximas Etapas:**

* Pratique os comandos e conceitos aprendidos neste capítulo.
* Explore recursos avançados de gerenciamento de usuário e permissão.
* Automatize tarefas de gerenciamento de usuário usando scripts.

**Seção 7: Referências**

* [Gestão de Utilizadores no Linux](https://phoenixnap.com/kb/linux-user-management)
* [Comandos do Linux para Gerenciamento de Usuários](https://www.tecmint.com/linux-user-management-with-commands/)
* [Exemplo de Configuração de Diretório Base do Usuário](https://help.ubuntu.com/lts/serverguide/base-layout.html)

**Ícones e Emojis para Referência:**

- 👤 Usuário
- 📁 Diretório
- 🔐 Senha
- ✏️ Bash
- 💬 Variável de Ambiente
- ⚙️ Opções de Login
- 🛡️ Permissões
- 📚 Grupo
- 📜 Arquivo
- 📖 Referência