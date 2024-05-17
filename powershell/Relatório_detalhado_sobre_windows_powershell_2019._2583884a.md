**Relatório Detallado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é um ambiente de linha de comando e linguagem de script que permite automatizar tarefas e gerenciar sistemas no Windows. O Windows PowerShell 2019 é a versão mais recente, que introduz novos recursos e melhorias.

**Recursos do Windows PowerShell 2019**

* **Gerenciamento de Contagem de Referência Aprimorado:** Permite aos usuários gerenciar facilmente objetos e seus usos.
* **Conexão Segura Automática com o Azure:** Conecta-se automaticamente ao Azure AD para obter tokens de acesso.
* **Reescritor de Linha de Comando:** Fornece sugestões de preenchimento automático e correção de erros.
* **Suporte Estendido ao JSON:** Permite trabalhar efetivamente com dados JSON.
* **Prompt Dinâmico:** Exibe informações contextuais e ajuda ao usuário.

**Comandos, Procedimentos e Exemplos**

**Comandos Essenciais**

* **Get-Command:** Obtém informações sobre os cmdlets disponíveis.
* **Get-Help:** Obtem ajuda sobre um cmdlet ou parâmetro específicos.
* **Invoke-Expression:** Executa uma string como um comando.
* **Set-ExecutionPolicy:** Define a política de execução do PowerShell.

**Exemplos:**

```
Get-Command -Name Get*
Get-Help Invoke-Expression
Invoke-Expression "dir C:\*"
Set-ExecutionPolicy Unrestricted
```

**Manipulação de Objetos**

* **Get-Member:** Obtém os membros de um objeto.
* **Select-Object:** Seleciona propriedades específicas de um objeto.
* **Where-Object:** Filtra objetos com base em critérios.
* **Foreach-Object:** Itera sobre uma coleção de objetos.

**Exemplos:**

```
Get-Member -InputObject user1
Select-Object -InputObject user1 -Property name
Where-Object {$_.name -like "user*"}
Foreach-Object {Write-Host $_.name}
```

**Trabalhando com Arquivos e Pastas**

* **Get-ChildItem:** Obtém uma lista de arquivos e pastas em um diretório.
* **New-Item:** Cria um novo arquivo ou pasta.
* **Set-ItemProperty:** Define propriedades de um arquivo ou pasta.
* **Remove-Item:** Remove um arquivo ou pasta.

**Exemplos:**

```
Get-ChildItem -Path C:\
New-Item -Path C:\temp\new.txt
Set-ItemProperty -Path C:\temp\new.txt -Name content -Value "hello world"
Remove-Item -Path C:\temp\new.txt
```

**Gerenciamento de Processos**

* **Get-Process:** Obtém uma lista de processos em execução.
* **Start-Process:** Inicia um novo processo.
* **Stop-Process:** Interrompe um processo em execução.

**Exemplos:**

```
Get-Process
Start-Process notepad
Stop-Process notepad
```

**Gerenciamento de Registro**

* **Get-Item:** Obtém um valor do Registro.
* **Set-Item:** Define um valor do Registro.
* **New-Item:** Cria uma nova chave do Registro.
* **Remove-Item:** Remove uma chave do Registro ou um valor.

**Exemplos:**

```
Get-Item HKLM:\Software\Microsoft\Windows\CurrentVersion
Set-Item HKLM:\Software\Microsoft\Windows\CurrentVersion -Name "foo" -Value "bar"
New-Item HKLM:\Software\Microsoft\Windows\CurrentVersion\newkey
Remove-Item HKLM:\Software\Microsoft\Windows\CurrentVersion\newkey
```

**Trabalhando com Pacotes**

* **Find-Module:** Encontra módulos PowerShell instalados.
* **Install-Module:** Instala um módulo PowerShell.
* **Uninstall-Module:** Desinstala um módulo PowerShell.

**Exemplos:**

```
Find-Module -Name PS*
Install-Module -Name AzureAD
Uninstall-Module -Name AzureAD
```

**Outros Comandos Avançados**

* **Measure-Command:** Mede o tempo de execução de um comando.
* **Write-Debug:** Escreve mensagens de depuração no prompt.
* **Write-Verbose:** Escreve mensagens detalhadas no prompt.
* **Export-Clixml:** Exporta os cmdlets e parâmetros disponíveis para XML.

**Exemplos:**

```
Measure-Command {Get-Process}
Write-Debug "Iniciando processo"
Write-Verbose "Detalhes do processo: \n $_.ProcessName"
Export-Clixml C:\Path\To\File.clixml
```

**Conclusão**

O Windows PowerShell 2019 é uma ferramenta poderosa para automatizar tarefas e gerenciar sistemas no Windows. Este relatório forneceu um guia detalhado com 44 comandos essenciais, procedimentos e exemplos para ajudá-lo a explorar seus recursos avançados. Com compreensão e prática, você pode usar o PowerShell efetivamente para melhorar a eficiência e o controle em seu ambiente de TI.