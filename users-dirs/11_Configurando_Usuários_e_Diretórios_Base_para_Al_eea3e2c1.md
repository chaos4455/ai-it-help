**Configuração de Usuários e Diretórios Base para Alta Disponibilidade**

**Seção 3. Configurando um Usuário e Diretório Base**

**Introdução:**

Nesta seção, configuraremos um usuário e diretório base para o serviço de alta disponibilidade (HA). Isso garantirá que todos os processos do serviço HA usem um usuário e diretório base consistentes, facilitando o gerenciamento e a manutenção.

**Tarefas:**

1. **Crie um usuário do sistema:**

    - Crie um novo usuário do sistema usando o comando `adduser`.
    - Atribua uma senha segura ao usuário.

    ```sh
    sudo adduser hauser
    sudo passwd hauser
    ```

2. **Crie um diretório base do usuário:**

    - Crie um diretório base para o usuário do sistema.
    - Defina o diretório base do usuário como o local padrão para armazenar dados e configurações.

    ```sh
    sudo mkdir /home/hauser
    sudo chown hauser:hauser /home/hauser
    ```

3. **Ajuste as configurações do shell:**

    - Configure o shell padrão do usuário para `/bin/bash`.
    - Garanta que o usuário tenha permissão para executar comandos como `sudo`.

    ```sh
    sudo chsh -s /bin/bash hauser
    sudo usermod -aG sudo hauser
    ```

4. **Configure as variáveis de ambiente do usuário:**

    - Adicione variáveis de ambiente necessárias ao perfil do usuário, como `PATH` e `HOME`.
    - Defina o diretório base do usuário como o diretório inicial padrão.

    ```sh
    sudo echo "export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin" >> /home/hauser/.bashrc
    sudo echo "export HOME=/home/hauser" >> /home/hauser/.bashrc
    ```

5. **Copie arquivos de configuração para o diretório base do usuário:**

    - Copie os arquivos de configuração necessários do diretório base padrão para o diretório base do usuário.
    - Isso inclui arquivos como `.ssh/config` e `.bashrc`.

    ```sh
    sudo cp /etc/ssh/ssh_config /home/hauser/.ssh/
    sudo cp /etc/bash.bashrc /home/hauser/.bashrc
    ```

6. **Teste o novo usuário:**

    - Faça login como o novo usuário e verifique se todas as configurações estão funcionando conforme o esperado.
    - Execute comandos como `ls`, `cd` e `sudo` para testar.

7. **Proteja as permissões do diretório base do usuário:**

    - Certifique-se de que o diretório base do usuário tenha permissões adequadas para evitar acesso não autorizado.
    - Defina as permissões para 755.

    ```sh
    sudo chmod 755 /home/hauser
    ```

8. **Documente as alterações:**

    - Documente todas as alterações feitas na configuração do usuário e diretório base.
    - Isso facilitará a referência e a solução de problemas posteriormente.

**Conclusão:**

Configurar um usuário e diretório base exclusivos para o serviço HA garante consistência, facilidade de gerenciamento e segurança aprimorada. Ao seguir estas etapas, você pode garantir uma base sólida para seu ambiente HA.