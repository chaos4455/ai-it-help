**Manual Avançado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell 2019 é um shell de linha de comando aprimorado que permite que os administradores de TI e usuários avançados automatizem tarefas, gerenciem sistemas e acessem recursos avançados do Windows. Este manual irá explorar as seguintes funcionalidades avançadas:

**1. Gerenciamento de Arquivos e Pastas**

* `New-Item`: Cria um novo arquivo ou pasta
* `Get-ChildItem`: Recupera uma lista de arquivos e pastas
* `Set-Content`: Define o conteúdo de um arquivo
* `Copy-Item`: Copia um arquivo ou pasta
* `Move-Item`: Move um arquivo ou pasta
* `Remove-Item`: Remove um arquivo ou pasta

**2. Gerenciamento de Usuários e Grupos**

* `New-ADUser`: Cria um novo usuário do Active Directory
* `Get-ADUser`: Recupera as informações do usuário do Active Directory
* `Set-ADUser`: Modifica as informações do usuário do Active Directory
* `New-ADGroup`: Cria um novo grupo do Active Directory
* `Get-ADGroup`: Recupera as informações do grupo do Active Directory
* `Set-ADGroup`: Modifica as informações do grupo do Active Directory

**3. Gerenciamento de Serviços**

* `Get-Service`: Recupera uma lista de serviços
* `Start-Service`: Inicia um serviço
* `Stop-Service`: Para um serviço
* `Restart-Service`: Reinicia um serviço
* `New-Service`: Cria um novo serviço
* `Remove-Service`: Remove um serviço

**4. Gerenciamento de Eventos**

* `New-EventLog`: Cria um novo log de eventos
* `Get-EventLog`: Recupera um log de eventos
* `Clear-EventLog`: Limpa um log de eventos
* `Write-EventLog`: Grava um evento em um log de eventos
* `Subscribe-Event`: Assina eventos de um log de eventos
* `Unsubscribe-Event`: Cancela a assinatura de eventos de um log de eventos

**5. Gerenciamento de Processos**

* `Get-Process`: Recupera uma lista de processos
* `Start-Process`: Inicia um processo
* `Stop-Process`: Para um processo
* `New-Job`: Cria um novo trabalho
* `Get-Job`: Recupera as informações do trabalho
* `Receive-Job`: Recebe os resultados de um trabalho

**6. Gerenciamento de Rede**

* `Get-NetAdapter`: Recupera uma lista de adaptadores de rede
* `Enable-NetAdapter`: Habilita um adaptador de rede
* `Disable-NetAdapter`: Desabilita um adaptador de rede
* `New-NetIPAddress`: Atribui um novo endereço IP a um adaptador de rede
* `Remove-NetIPAddress`: Remove um endereço IP de um adaptador de rede
* `Resolve-DnsName`: Resolve um nome DNS

**7. Gerenciamento de Registro**

* `Get-RegistryKey`: Recupera uma chave do Registro
* `New-RegistryKey`: Cria uma nova chave do Registro
* `Set-RegistryValue`: Define um valor de registro
* `Delete-RegistryKey`: Exclui uma chave do Registro
* `Import-RegistryFile`: Importa um arquivo REG
* `Export-RegistryFile`: Exporta um arquivo REG

**8. Gerenciamento de Tarefas Agendadas**

* `Get-ScheduledTask`: Recupera uma lista de tarefas agendadas
* `New-ScheduledTask`: Cria uma nova tarefa agendada
* `Register-ScheduledTask`: Registra uma tarefa agendada
* `Unregister-ScheduledTask`: Cancela o registro de uma tarefa agendada
* `Start-ScheduledTask`: Inicia uma tarefa agendada
* `Stop-ScheduledTask`: Para uma tarefa agendada

**9. Gerenciamento de Módulos**

* `Import-Module`: Importa um módulo do PowerShell
* `Export-Module`: Exporta um módulo do PowerShell
* `Find-Module`: Localiza um módulo do PowerShell
* `Remove-Module`: Remove um módulo do PowerShell
* `Update-Module`: Atualiza um módulo do PowerShell
* `Publish-Module`: Publica um módulo do PowerShell

**10. Gerenciamento de Cmdlets**

* `Get-Command`: Recupera uma lista de cmdlets
* `New-Alias`: Cria um novo alias para um cmdlet
* `Remove-Alias`: Remove um alias para um cmdlet
* `Export-Alias`: Exporta um alias para um arquivo
* `Import-Alias`: Importa um alias de um arquivo
* `Disable-Cmdlet`: Desabilita um cmdlet

**11. Gerenciamento de Sessões Remotas**

* `New-PSSession`: Cria uma nova sessão remota
* `Get-PSSession`: Recupera uma sessão remota
* `Enter-PSSession`: Entra em uma sessão remota
* `Exit-PSSession`: Sai de uma sessão remota
* `Invoke-Command`: Executa comandos em uma sessão remota
* `Stop-PSSession`: Para uma sessão remota

**12. Gerenciamento de Segurança**

* `Get-LocalUser`: Recupera informações sobre usuários locais
* `Set-LocalUser`: Modifica as informações do usuário local
* `New-LocalGroup`: Cria um novo grupo local
* `Get-LocalGroup`: Recupera as informações do grupo local
* `Set-LocalGroup`: Modifica as informações do grupo local
* `New-LocalGroupMember`: Adiciona um membro a um grupo local

**13. Gerenciamento de Perfomance**

* `Get-Counter`: Recupera um contador de desempenho
* `Set-Counter`: Modifica um contador de desempenho
* `New-CounterSet`: Cria um novo conjunto de contadores
* `Get-CounterSet`: Recupera um conjunto de contadores
* `Remove-CounterSet`: Remove um conjunto de contadores
* `Collect-Counter`: Coleta dados de contador de desempenho

**14. Gerenciamento de Escopo**

* `Push-Location`: Empurra o caminho atual para a pilha
* `Pop-Location`: Remove o caminho atual da pilha
* `Set-Location`: Altera o caminho atual
* `Get-Location`: Recupera o caminho atual
* `Join-Path`: Junta vários caminhos
* `Resolve-Path`: Resolve um caminho

**15. Operadores de Pipeline**

* `Where-Object`: Filtra objetos com base em uma condição
* `Select-Object`: Seleciona propriedades específicas de objetos
* `ForEach-Object`: Executa um comando para cada objeto
* `ForEach`: Executa um comando para cada elemento em uma coleção
* `Tee-Object`: Envia objetos para vários comandos
* `Checkpoint-CimSession`: Cria um ponto de verificação em uma sessão WMI

**16. Manipulação de Dados**

* `ConvertTo-Csv`: Converte objetos em um arquivo CSV
* `ConvertFrom-Csv`: Converte um arquivo CSV em objetos
* `ConvertTo-Html`: Converte objetos em um arquivo HTML
* `ConvertFrom-Html`: Converte um arquivo HTML em objetos
* `ConvertTo-Json`: Converte objetos em um arquivo JSON
* `ConvertFrom-Json`: Converte um arquivo JSON em objetos

**17. Manipulação de XML**

* `ConvertTo-Xml`: Converte objetos em um documento XML
* `ConvertFrom-Xml`: Converte um documento XML em objetos
* `Select-Xml`: Seleciona nós específicos de um documento XML
* `New-XmlDocument`: Cria um novo documento XML
* `Remove-Xml`: Remove nós específicos de um documento XML
* `Set-Xml`: Define o valor de nós específicos em um documento XML

**18. Manipulação de Strings**

* `Compare-String`: Compara duas strings
* `Split-String`: Divide uma string em uma matriz de substrings
* `Replace-String`: Substitui ocorrências de uma substring por outra
* `Join-String`: Junta uma matriz de strings em uma única string
* `To-Lower`: Converte uma string em minúsculas
* `To-Upper`: Converte uma string em maiúsculas

**19. Manipulação Numérica**

* `Compare-Object`: Compara dois objetos numéricos
* `Add-Number`: Soma dois números
* `Subtract-Number`: Subtrai dois números
* `Multiply-Number`: Multiplica dois números
* `Divide-Number`: Divide dois números
* `Round-Number`: Arredonda um número

**20. Manipulação de Data e Hora**

* `Get-Date`: Recupera a data e hora atuais
* `Set-Date`: Define a data e hora atuais
* `Add-Date`: Adiciona um intervalo de tempo a uma data e hora
* `Subtract-Date`: Subtrai um intervalo de tempo de uma data e hora
* `Compare-Date`: Compara duas datas e horas
* `Format-Date`: Formata uma data e hora

**21. Manipulação de Arrays**

* `New-Object`: Cria um novo objeto
* `Clear-Array`: Limpa uma matriz
* `Join-Array`: Junta duas