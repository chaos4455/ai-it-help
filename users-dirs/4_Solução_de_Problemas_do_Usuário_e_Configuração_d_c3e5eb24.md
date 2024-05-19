**🛠️ Configurando um Usuário e Diretório Base**

**Introdução:**

Gerenciar usuários e diretórios base é crucial para a segurança e organização do sistema. Este guia o orientará no processo detalhado de criação e configuração de um usuário e seu diretório base no sistema operacional Linux.

**Conceitos Básicos:**

- **Usuário:** Representa um indivíduo ou processo que interage com o sistema operacional.
- **Diretório Base:** O diretório inicial alocado a um usuário específico, que contém seus arquivos, configurações e programas.
- **Shell:** Um programa interpretador de comandos que permite que os usuários interajam com o sistema.

**Passo a Passo:**

**1. Crie um Usuário:**

```
sudo adduser nome_do_usuario
```

- Digite uma senha segura e informações adicionais conforme solicitado.

**2. Configurando um Shell:**

- Verifique o shell padrão atribuído ao novo usuário:

```
getent passwd nome_do_usuario | cut -d: -f7
```

- Defina um shell personalizado, se necessário:

```
sudo usermod -s caminho_para_o_shell nome_do_usuario
```

**3. Crie um Diretório Base:**

```
sudo mkdir /home/nome_do_usuario
```

- Atribua a propriedade ao novo usuário:

```
sudo chown nome_do_usuario:nome_do_usuario /home/nome_do_usuario
```

- Defina as permissões adequadas:

```
sudo chmod 755 /home/nome_do_usuario
```

**4. Configure as Cotas de Disco:**

- Verifique as cotas de disco atuais:

```
sudo repquota -a
```

- Defina uma cota de disco para o novo usuário (opcional):

```
sudo setquota -u nome_do_usuario -b cotas_em_blocos
```

**5. Defina um Diretório Padrão:**

- Altere para o diretório home do novo usuário:

```
cd /home/nome_do_usuario
```

- Crie um subdiretório para cada tipo de arquivo (por exemplo, Documentos, Downloads, Imagens):

```
mkdir Documentos
mkdir Downloads
mkdir Imagens
```

**6. Configure as Configurações do Ambiente:**

- Edite o arquivo `.bashrc` do usuário:

```
nano ~/.bashrc
```

- Adicione as linhas de configuração desejadas, como aliases de comando ou definições de variáveis:

```
alias ls='ls -la'
export PATH=$PATH:/usr/local/bin
```

- Salve e saia do arquivo.

**7. Configure o Sudo:**

- Verifique se o novo usuário está no grupo `sudo`:

```
grep nome_do_usuario /etc/group | grep sudo
```

- Adicione o usuário ao grupo `sudo`, se necessário:

```
sudo usermod -aG sudo nome_do_usuario
```

**8. Efetue Login como o Novo Usuário:**

```
su - nome_do_usuario
```

- Verifique se o ambiente e as configurações estão corretos.

**9. Gerenciamento de Usuários Adicionais:**

- Crie usuários adicionais seguindo as etapas acima.
- Gerencie usuários usando comandos como `adduser`, `usermod` e `deluser`.

**Sugestões Adicionais:**

- Use senhas fortes e exclusivas.
- Configure grupos de usuários para gerenciamento de acesso granular.
- Use uma ferramenta de gerenciamento de usuários para simplificar as tarefas.
- Estabeleça políticas claras de uso e armazenamento.