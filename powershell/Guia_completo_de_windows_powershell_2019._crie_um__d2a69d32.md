**Guia Completo do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é um shell de linha de comando avançado e orientado a objetos projetado para automação de tarefas, gerenciamento de sistemas e configuração em ambientes Windows. Este guia fornecerá uma compreensão abrangente do PowerShell, incluindo comandos, procedimentos e melhores práticas.

**Comandos Básicos**

* `Get-Command`: Obtém uma lista de comandos disponíveis.
* `Get-Help`: Obtém ajuda para um comando específico.
* `Set-ExecutionPolicy`: Define a política de execução do PowerShell.
* `New-Item`: Cria um novo item, como um diretório, arquivo ou valor de registro.
* `Get-Item`: Obtém um item existente.
* `Remove-Item`: Remove um item existente.

**Comandos Avançados**

* `Where-Object`: Filtra objetos com base em um critério especificado.
* `Sort-Object`: Classifica objetos por um campo especificado.
* `Group-Object`: Agrupa objetos por uma propriedade comum.
* `Select-Object`: Seleciona propriedades específicas de objetos.
* `Expand-Object`: Expande propriedades aninhadas de objetos.

**Comandos de Gerenciamento de Sistemas**

* `Get-Service`: Obtém uma lista de serviços instalados.
* `Start-Service`: Inicia um serviço.
* `Stop-Service`: Para um serviço.
* `Restart-Service`: Reinicia um serviço.
* `Get-Process`: Obtém uma lista de processos em execução.
* `Stop-Process`: Encerra um processo.

**Comandos de Configuração**

* `Get-WmiObject`: Obtém informações sobre objetos WMI.
* `Set-WmiInstance`: Define propriedades de objetos WMI.
* `Invoke-Command`: Executa comandos em um computador remoto.
* `New-ScheduledTask`: Cria uma nova tarefa agendada.
* `Start-ScheduledTask`: Inicia uma tarefa agendada.

**Comandos de Scripting**

* `New-Variable`: Cria uma nova variável.
* `$`: Acessa o valor de uma variável.
* `If`: Executa um bloco de código se uma condição for verdadeira.
* `For`: Executa um bloco de código para cada item em uma coleção.
* `While`: Executa um bloco de código enquanto uma condição for verdadeira.

**Procedimentos**

* **Criando um novo script:** Crie um arquivo `.ps1` com um editor de texto e salve-o em um local apropriado.
* **Executando um script:** Digite o caminho do arquivo de script no prompt do PowerShell ou use `Invoke-Expression` para executar o script de uma variável.
* **Passando parâmetros para scripts:** Use `param` no início do script para declarar parâmetros e `$args` para acessá-los.
* **Lidando com erros:** Use blocos `try...catch` para capturar e tratar erros.
* **Depuração de scripts:** Use `Set-PSDebug` para habilitar a depuração e `Debug-Process` para depurar scripts.

**Passo a Passo: Criando um Script de Automação de Tarefas**

1. Abra o Bloco de Notas ou um editor de texto.
2. Cole o código abaixo:

```powershell
param (
    [string]$NomeDoDiretorio = "MeusDocumentos"
)

New-Item -ItemType Directory -Path $NomeDoDiretorio
Copy-Item C:\temp\*.txt $NomeDoDiretorio
```

3. Salve o arquivo como "CriarDiretorio.ps1".
4. Abra o PowerShell e execute o script:

```powershell
Invoke-Expression .\CriarDiretorio.ps1 -NomeDoDiretorio 'MyDocs'
```

5. Verifique se o diretório "MyDocs" foi criado e se os arquivos `.txt` foram copiados para ele.

**Melhores Práticas**

* Use nomes descritivos para comandos e variáveis.
* Indente seu código para melhorar a legibilidade.
* Adicione comentários ao seu código para explicar seu propósito.
* Teste seus scripts completamente antes de implantá-los.
* Use o recurso de preenchimento automático do PowerShell para descobrir comandos e parâmetros.

**Recursos Adicionais**

* [Documentação do Windows PowerShell](https://docs.microsoft.com/en-us/powershell/)
* [Tutoriais do Windows PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/tutorials/)
* [Fórum Comunitário do Windows PowerShell](https://social.technet.microsoft.com/Forums/en-US/home?forum=winserverpowershell)