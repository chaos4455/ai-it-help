**Manual de Segurança Avançada para Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é um poderoso shell de linha de comando que permite aos administradores gerenciar e configurar sistemas Windows. No entanto, também pode ser usado para fins maliciosos. Este manual fornece um guia detalhado sobre como proteger o Windows PowerShell 2019 de ameaças à segurança.

**Capítulo 1: Protegendo o Shell**

* **Ativar a execução remota:**
   * `Set-PSRemoting -Force -Enable`
* **Configurar restrições de execução:**
   * `Set-ExecutionPolicy -Scope LocalMachine/CurrentUser -ExecutionPolicy Restricted`
* **Desabilitar scripts:**
   * `Set-PsExecutionPolicy -Scope LocalMachine/CurrentUser -ExecutionPolicy Disable`
* **Limitar o uso de cmdlet:**
   * `Get-Command -Name * -Syntax '*' | Where-Object {$_.Parameters.Count -gt 1} | foreach {$Command = "Set-ExecutionPolicy -Command \"{0}\"".f($_); Invoke-Expression $Command}`

**Capítulo 2: Gerenciando Execuções**

* **Rastrear atividades do PowerShell:**
   * `Get-EventLog -LogName Microsoft-Windows-PowerShell/Operational`
* **Auditar execuções do PowerShell:**
   * `Enable-EventLog Microsoft-Windows-PowerShell/Operational -ErrorAction SilentlyContinue`
* **Criar cmdlets de auditoria personalizados:**
   * `New-PSSession -ComputerName $ComputerName | Register-PSSession | Invoke-Command -ScriptBlock {New-EventLog -LogName My-PowerShell-Log -Source My-PowerShell-Source}`
* **Limitar o tempo de execução do PowerShell:**
   * `Set-PowerShellExecutionPolicy -ExecutionTimeout 60 -Scope LocalMachine`

**Capítulo 3: Protegendo Módulos**

* **Carregar módulos assinados:**
   * `Set-ExecutionPolicy -Scope Process -ExecutionPolicy BySignature`
* **Assinar módulos personalizados:**
   * `Publish-Module -Name MyModule -Path C:\MyModule`
* **Verificar a integridade do módulo:**
   * `Get-AuthenticodeSignature -FilePath MyModule.psd1`
* **Bloquear módulos não confiáveis:**
   * `Set-PsModuleRepository -Force -DisableRepository C:\UnTrustedModules`

**Capítulo 4: Protegendo Scripts**

* **Usar assinaturas de código:**
   * `Set-AuthenticodeSignature -FilePath MyScript.ps1 -CertificateThumbprint 1234567890`
* **Criar políticas de assinatura de script:**
   * `New-PSSession -ComputerName $ComputerName | Register-PSSession | Invoke-Command -ScriptBlock {New-AuthenticodeSignaturePolicy -Name MyPolicy -Path C:\ScriptPolicies}`
* **Verificar a assinatura do script:**
   * `Get-AuthenticodeSignature -FilePath MyScript.ps1`
* **Bloquear scripts não assinados:**
   * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned`

**Capítulo 5: Protegendo Credenciais**

* **Armazenar credenciais com segurança:**
   * `New-Object System.Management.Automation.PSCredential -Credential $(Get-Credential)`
* **Evitar o roubo de credenciais:**
   * `Set-PSBreakpoint -Command Get-Credential`
* **Monitorar o uso da credencial:**
   * `Enable-EventLog Microsoft-Windows-PowerShell/Security -ErrorAction SilentlyContinue`
* **Renomear a cmdlet Get-Credential:**
   * `$CustomFunction = {param($UserName, $Password); New-Object System.Management.Automation.PSCredential -Credential $(Get-Credential)}; Register-EngineEvent $CustomFunction -Name Get-Credential -Force`

**Capítulo 6: Protegendo Remotas**

* **Configurar limites para sessões remotas:**
   * `Set-PSSessionConfiguration -Name Microsoft.PowerShell -MaximumConnectionCount 10`
* **Rastrear sessões remotas:**
   * `Get-PSSession`
* **Limitar o acesso remoto:**
   * `Set-Item WSMan:\localhost\Client\TrustedHosts -Value *`
* **Usar conexões seguras:**
   * `Enable-PSRemoting -UseSSL`

**Capítulo 7: Proteção Avançada**

* **Monitorar eventos de segurança:**
   * `wevtutil enum-logs Microsoft-Windows-PowerShell/Security`
* **Configurar o registro em log detalhado:**
   * `Enable-PSModuleLogging -Module PowerShell -Level Verbose`
* **Usar ferramentas forenses:**
   * `Import-Module PSTrace -Force; FTReport C:\Path\To\Log.etw`
* **Implementar medidas de proteção contra malware:**
   * `Install-Module -Name WindowsDefender`
   * `Start-MpScan -ScanType FullScan`

**Conclusão**

Implementar as medidas de segurança descritas neste manual ajudará a proteger o Windows PowerShell 2019 de ameaças à segurança. Ao seguir essas orientações, as organizações podem minimizar o risco de ataques e garantir a integridade de seus sistemas.