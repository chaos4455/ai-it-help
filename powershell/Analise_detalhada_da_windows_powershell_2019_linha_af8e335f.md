**Manual Avançado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell 2019 é um poderoso shell de linha de comando e linguagem de script que fornece acesso e controle aprimorados sobre o sistema operacional Windows. Este manual visa fornecer uma análise detalhada do PowerShell 2019, explorando seus comandos, procedimentos e recursos avançados.

**Comandos**

**1. cmdlets**

* Os cmdlets são comandos integrados que executam tarefas específicas, como gerenciar arquivos, processos e serviços.
* Exemplo: `Get-Process` retorna uma lista de processos em execução.

**2. aliases**

* Aliases são atalhos para cmdlets comuns, simplificando a digitação.
* Exemplo: `dir` é um alias para `Get-ChildItem`.

**3. scripts**

* Os scripts são conjuntos de comandos PowerShell salvos em arquivos `.ps1`.
* Exemplo: Crie um script chamado `MyScript.ps1` com o seguinte conteúdo: `Get-Process | Sort-Object Name`. Execute o script usando `./MyScript.ps1`.

**Procedimentos**

**4. canalização**

* A canalização permite que a saída de um comando seja passada como entrada para outro.
* Exemplo: `Get-Process | Where-Object {$_.Name -like "*explorer*" }` retorna os processos com "explorer" no nome.

**5. redirecionamento**

* O redirecionamento permite que você envie a saída de um comando para um arquivo ou outro comando.
* Exemplo: `Get-Process > process-list.txt` salva a lista de processos em um arquivo.

**6. loops**

* Os loops permitem que você repita um bloco de comandos com base em uma condição.
* Exemplo: `ForEach ($process in Get-Process) { Write-Host $process.Name }` imprime o nome de cada processo.

**7. funções**

* As funções são blocos reutilizáveis de código que podem ser chamados de outros comandos.
* Exemplo: Crie uma função chamada `Get-MyProcesses` com o seguinte conteúdo:
```
function Get-MyProcesses {
    Get-Process | Where-Object {$_.User -eq $env:USERNAME}
}
```
Execute a função usando `Get-MyProcesses`.

**Recursos Avançados**

**8. variáveis**

* As variáveis armazenam dados no PowerShell.
* Exemplo: `$processName = "explorer"` cria uma variável chamada `$processName` e define seu valor como "explorer".

**9. arrays**

* Arrays são coleções ordenadas de elementos.
* Exemplo: `$processes = Get-Process` cria um array chamado `$processes` contendo a lista de processos.

**10. hashtables**

* As hashtables são coleções não ordenadas de pares de valores-chave.
* Exemplo: `$processInfo = @{"Name" = "explorer"; "PID" = 1234}` cria uma hashtable chamada `$processInfo` com dois pares de valores-chave.

**11. objetos**

* Os objetos representam entidades no PowerShell.
* Exemplo: `$process = Get-Process "explorer"` retorna um objeto `System.Diagnostics.Process` representando o processo do explorer.

**12. Módulos**

* Os módulos são conjuntos reutilizáveis de comandos e funções.
* Exemplo: Importe o módulo `PSDesiredStateConfiguration` usando `Import-Module PSDesiredStateConfiguration`.

**13. Remoting**

* O remoting permite que você execute comandos em computadores remotos.
* Exemplo: `Invoke-Command -ComputerName remote-computer -ScriptBlock { Get-Process }` retorna a lista de processos no computador remoto.

**14. Serviços de Automação**

* Os Serviços de Automação do Azure fornecem automação em nuvem para tarefas do PowerShell.
* Exemplo: Crie uma tarefa do Serviço de Automação para reiniciar um computador remoto usando `New-AzureRmAutomationRunbookTask`.

**15. Azure PowerShell**

* O Azure PowerShell fornece acesso à plataforma Microsoft Azure.
* Exemplo: `Get-AzureRmSubscription` retorna a lista de assinaturas do Azure.

**16. Eventos e manipuladores de eventos**

* Eventos são notificações disparadas pelo sistema ou aplicativos.
* Exemplo: `Register-ObjectEvent -InputObject (Get-Process) -EventName Exited -Action { Write-Host "$($_.sender.Name) exited." }` exibe uma mensagem quando um processo sai.

**17. Criar arquivos e diretórios**

* `New-Item -Path C:\MyFiles\NewDirectory -ItemType Directory` cria um novo diretório chamado "NewDirectory" no caminho especificado.
* `New-Item -Path C:\MyFiles\NewFile.txt -ItemType File` cria um novo arquivo chamado "NewFile.txt" no caminho especificado.

**18. Gerenciar arquivos e diretórios**

* `Get-ChildItem -Path C:\MyFiles` retorna todos os arquivos e diretórios no caminho especificado.
* `Copy-Item -Path C:\MyFiles\NewFile.txt -Destination C:\MyBackup` copia o arquivo "NewFile.txt" para o caminho de destino.
* `Move-Item -Path C:\MyFiles\NewDirectory -Destination C:\MyBackup` move o diretório "NewDirectory" para o caminho de destino.
* `Remove-Item -Path C:\MyFiles\NewFile.txt` remove o arquivo "NewFile.txt".
* `Remove-Item -Path C:\MyFiles\NewDirectory -Recurse` remove o diretório "NewDirectory" e todo o seu conteúdo.

**19. Criar e gerenciar registros**

* `New-EventLog -LogName "MyApplicationLog" -Source "MyApplication"` cria um novo log de eventos chamado "MyApplicationLog" com uma fonte chamada "MyApplication".
* `Write-EventLog -LogName "MyApplicationLog" -Source "MyApplication" -EntryType Information -Message "This is an informational message."` escreve uma mensagem informativa no log de eventos.
* `Get-EventLog -LogName "MyApplicationLog"` retorna todos os eventos no log de eventos.

**20. Gerenciar serviços**

* `Get-Service -Name "wuauserv"` retorna o serviço Windows Update.
* `Start-Service -Name "wuauserv"` inicia o serviço Windows Update.
* `Stop-Service -Name "wuauserv"` interrompe o serviço Windows Update.
* `Restart-Service -Name "wuauserv"` reinicia o serviço Windows Update.

**21. Gerenciar processos**

* `Get-Process -Name "explorer"` retorna o processo do explorer.
* `Start-Process -FilePath "C:\Windows\explorer.exe"` inicia o processo do explorer.
* `Stop-Process -Name "explorer"` interrompe o processo do explorer.

**22. Gerenciar registro**

* `Get-Item HKLM:\Software\Microsoft\Windows\CurrentVersion` retorna a chave "CurrentVersion" no registro do HKEY_LOCAL_MACHINE.
* `Set-Item HKLM:\Software\Microsoft\Windows\CurrentVersion\Run -Name "MyApplication" -Value "C:\MyApplication.exe"` define um novo valor de registro chamado "MyApplication" com o valor "C:\MyApplication.exe".
* `Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Run` retorna todos os valores de registro na chave "Run".

**23. Gerenciar certificados**

* `Get-ChildItem -Path Cert:\CurrentUser\My` retorna todos os certificados no armazenamento atual do usuário.
* `New-SelfSignedCertificate -Subject "MySelfSignedCertificate" -KeyUsage DigitalSignature` cria um novo certificado autoassinado.
* `Export-Certificate -Cert cert.pfx -FilePath C:\MyCertificate.pfx` exporta um certificado para um arquivo.

**24. Gerenciar usuários e grupos**

* `Get-LocalUser -Name "John Doe"` retorna o usuário local chamado "John Doe".
* `New-LocalUser -Name "New User" -Password "P@ssw0rd"` cria um novo usuário local chamado "New User" com a senha "P@ssw0rd".
* `Get-LocalGroup -Name "Administrators"` retorna o grupo local chamado "Administrators".
* `Add-LocalGroupMember -Group "Administrators" -Member "New User"` adiciona o usuário "New User" ao grupo "Administrators".

**25. Gerenciar hardware**

* `Get-WmiObject -Class Win32_OperatingSystem` retorna informações sobre o sistema operacional.
* `Get-WmiObject -Class Win32_LogicalDisk` retorna informações sobre discos lógicos.
* `Get-WmiObject -Class Win32_Processor` retorna informações sobre processadores.

**26. Gerenciar rede**

* `Get-NetAdapter` retorna todos os adaptadores de rede.
* `Enable-NetAdapter -Name "Ethernet"` habilita o adaptador de rede chamado "Ethernet".
* `Disable-NetAdapter -Name "