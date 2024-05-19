**3. Configurando um Usuário e Diretório Base**

**Objetivo:**

Configurar um novo usuário e seu diretório base associado para gerenciamento e organização eficazes do sistema.

**Pré-requisitos:**

* Acesso de superusuário (root)
* Editor de texto (por exemplo, nano, vi)

**Passos:**

**1. Criando um Novo Usuário**

* Use o comando `adduser` para criar um novo usuário:
  ```bash
  sudo adduser username
  ```
* Insira uma senha e quaisquer outras informações solicitadas.

**2. Configurando o Diretório Base**
* O diretório base padrão para usuários não root é `/home/username`.
* Para criar um diretório base personalizado:
  ```bash
  sudo mkdir /home/custom_directory
  sudo chown username:username /home/custom_directory
  ```

**3. Definindo o Diretório Base**

* Edite `/etc/passwd` para definir o diretório base:
  ```bash
  sudo nano /etc/passwd
  ```
* Encontre a linha para o novo usuário e altere o campo "home" para o diretório base desejado:
  ```
  username:x:1001:1001:User Name:/home/custom_directory:/bin/bash
  ```

**4. Configurando o Shell Padrão**

* Se necessário, defina o shell padrão para o usuário:
  ```bash
  sudo chsh -s /bin/zsh username
  ```

**5. Copiando Arquivos de Configuração**

* Crie um diretório temporário:
  ```bash
  mkdir /tmp/user-config
  ```
* Copie os arquivos de configuração do diretório base padrão (/home/username):
  ```bash
  cp -r /home/username /tmp/user-config
  ```
* Renomeie o diretório para corresponder ao novo diretório base:
  ```bash
  mv /tmp/user-config /home/custom_directory
  ```

**6. Permissões do Diretório Base**

* Defina as permissões adequadas para o diretório base:
  ```bash
  sudo chmod 755 /home/custom_directory
  ```

**7. Configurando o Grupo Primário**

* Se necessário, atribua o usuário a um grupo primário diferente:
  ```bash
  sudo usermod -g new_group username
  ```

**8. Configurando o Grupo Secundário**

* Adicione o usuário a grupos secundários adicionais (se necessário):
  ```bash
  sudo usermod -a -G group1,group2 username
  ```

**9. Criando Arquivos de Inicialização**

* Crie arquivos de inicialização no diretório base do usuário (por exemplo, `.bashrc`, `.profile`):
  ```bash
  touch /home/custom_directory/.bashrc
  touch /home/custom_directory/.profile
  ```

**10. Configurando Variáveis de Ambiente**

* Adicione variáveis de ambiente personalizadas aos arquivos de inicialização:
  ```bash
  echo "export PATH=$PATH:/new/path" >> /home/custom_directory/.bashrc
  ```

**11. Definindo Variáveis de Shell**

* Defina variáveis de shell personalizadas:
  ```bash
  echo "SHELL=/bin/zsh" >> /home/custom_directory/.profile
  ```

**12. Configurando Aliases de Comando**

* Crie aliases de comando personalizados:
  ```bash
  echo "alias ll='ls -la'" >> /home/custom_directory/.bash_aliases
  ```

**13. Configurando Funções de Shell**

* Defina funções de shell personalizadas:
  ```bash
  echo "my_function() { echo 'Hello, world!'; }" >> /home/custom_directory/.bash_functions
  ```

**14. Configurando o Gerenciador de Pacotes**

* Configure o gerenciador de pacotes padrão para o usuário:
  ```bash
  sudo apt update
  sudo apt install apt-get
  ```

**15. Instalando Pacotes Essenciais**

* Instale pacotes essenciais para o usuário:
  ```bash
  sudo apt-get install build-essential git
  ```

**16. Configurando o Editor de Texto**

* Instale e configure um editor de texto preferred:
  ```bash
  sudo apt-get install vim
  echo "set number" >> ~/.vimrc
  ```

**17. Configurando o Navegador da Web**

* Instale e configure um navegador da web padrão:
  ```bash
  sudo apt-get install firefox
  echo "user_pref('browser.newtabpage.enabled', false);" >> ~/.mozilla/firefox/profiles.ini
  ```

**18. Configurando o Cliente de E-mail**

* Instale e configure um cliente de e-mail:
  ```bash
  sudo apt-get install thunderbird
  echo "set account.default.server.hostname 'imap.example.com'" >> ~/.thunderbird/profiles.ini
  ```

**19. Configurando o Calendário**

* Instale e configure um calendário:
  ```bash
  sudo apt-get install evolution
  echo "set calendar.visible 'true'" >> ~/.evolution/config-default
  ```

**20. Configurando o Gerenciador de Tarefas**

* Instale e configure um gerenciador de tarefas:
  ```bash
  sudo apt-get install gnome-todo
  echo "set tasklist.default-list 'Personal'" >> ~/.gnome-todo/defaults
  ```

**21. Configurando o Ambiente do Ambiente de Trabalho**

* Personalize o ambiente da área de trabalho com papel de parede, temas e extensões:
  ```bash
  gsettings set org.gnome.desktop.background picture-uri 'file:///home/custom_directory/Pictures/wallpaper.jpg'
  gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita-dark'
  ```

**22. Instalando Software de Mídia**

* Instale o software de mídia necessário:
  ```bash
  sudo apt-get install vlc gstreamer1.0-plugins-bad
  ```

**23. Configurando o Player de Música**

* Configure o player de música padrão:
  ```bash
  echo "set player.media-player 'vlc'" >> ~/.config/rhythmbox/preferences.xml
  ```

**24. Configurando o Visualizador de Imagens**

* Configure o visualizador de imagens padrão:
  ```bash
  gsettings set org.gnome.eog.preferences.launch default-image-path 'file:///home/custom_directory/Pictures/'
  ```

**25. Configurando o Editor de Vídeos**

* Instale e configure um editor de vídeo:
  ```bash
  sudo apt-get install openshot
  ```

**26. Configurando o Editor de Áudio**

* Instale e configure um editor de áudio:
  ```bash
  sudo apt-get install audacity
  ```

**27. Configurando o Ambiente de Desenvolvimento**

* Instale as ferramentas de desenvolvimento necessárias:
  ```bash
  sudo apt-get install python3 python3-pip
  pip3 install django
  ```

**28. Configurando o Servidor da Web**

* Instale e configure um servidor da web:
  ```bash
  sudo apt-get install nginx
  echo "server { ... }" >> /etc/nginx/sites-available/my_site
  ```

**29. Configurando o Banco de Dados**

* Instale e configure um banco de dados:
  ```bash
  sudo apt-get install mysql-server
  mysql -u root -p
  ```

**30. Configurando o Sistema de Controle de Versão**

* Instale e configure um sistema de controle de versão:
  ```bash
  sudo apt-get install git
  echo "[user]" >> ~/.gitconfig
  echo " name = John Doe" >> ~/.gitconfig
  echo " email = john.doe@example.com" >> ~/.gitconfig
  ```

**31. Configurando o Ambiente de Nuvem**

* Configure o acesso à nuvem:
  ```bash
  aws configure
  ```

**32. Instalando Ferramentas de Segurança**

* Instale e configure ferramentas de segurança:
  ```bash
  sudo apt-get install fail2ban
  sudo ufw enable
  ```

**33. Monitoramento do Sistema**

* Configure o monitoramento do sistema:
  ```bash
  sudo apt-get install htop
  echo "set htop.color.highlight 'yellow'" >> ~/.htoprc
  ```

**34. Personalizando Prompts de Comando**

* Personalize os prompts de comando:
  ```bash
  echo "PS1='\u@\h:\w \$ '" >> ~/.bashrc
  ```

**35. Configurando o Autocompletar**

* Habilite o autocompletar:
  