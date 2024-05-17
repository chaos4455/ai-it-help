**Manual Avançado do Windows PowerShell 2019**

## Introdução

O Windows PowerShell é um shell de linha de comando e linguagem de script poderosa para gerenciamento de sistemas no Windows. Este manual fornece documentação avançada sobre o Windows PowerShell 2019, incluindo comandos, procedimentos, exemplos e práticas recomendadas.

## Comandos Básicos

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Command` | Obtém comandos disponíveis | `Get-Command *Get*` |
| `Get-Help` | Exibe a ajuda para comandos | `Get-Help Get-Process` |
| `Get-Member` | Exibe os membros de um objeto | `Get-Member Get-Process` |
| `Invoke-Command` | Executa comandos em computadores remotos | `Invoke-Command -ComputerName server1 -ScriptBlock { Get-Process }` |

## Trabalhando com Objetos

| Comando | Descrição | Exemplo |
|---|---|---|
| `New-Object` | Cria novos objetos | `New-Object System.Net.WebClient` |
| `Get-Property` | Obtém propriedades de objetos | `Get-Property Get-Process -Name Name` |
| `Set-Property` | Define propriedades de objetos | `Set-Property Get-Process -Name Priority -Value High` |
| `Compare-Object` | Compara dois objetos | `Compare-Object -ReferenceObject $obj1 -DifferenceObject $obj2` |

## Automatização de Tarefas

| Comando | Descrição | Exemplo |
|---|---|---|
| `ForEach-Object` | Itera sobre uma coleção de objetos | `ForEach-Object { Write-Host $_.Name }` |
| `Where-Object` | Filtra uma coleção de objetos com base em uma condição | `Get-Process | Where-Object { $_.Name -like "powershell*" }` |
| `Select-Object` | Seleciona propriedades específicas de objetos | `Get-Process | Select-Object Name, CPU` |
| `Export-Csv` | Exporta objetos para um arquivo CSV | `Get-Process | Export-Csv process.csv` |

## Gerenciamento de Arquivos e Pastas

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-ChildItem` | Obtém os itens filhos de um diretório | `Get-ChildItem c:\windows` |
| `New-Item` | Cria diretórios ou arquivos | `New-Item c:\scripts` |
| `Remove-Item` | Remove diretórios ou arquivos | `Remove-Item c:\scripts\test.ps1` |
| `Copy-Item` | Copia arquivos ou diretórios | `Copy-Item c:\scripts\test.ps1 d:\scripts` |

## Gerenciamento de Processos

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Process` | Obtém processos em execução | `Get-Process` |
| `Start-Process` | Inicia novos processos | `Start-Process notepad.exe` |
| `Stop-Process` | Interrompe processos em execução | `Stop-Process notepad.exe` |
| `Suspend-Process` | Suspende processos em execução | `Suspend-Process notepad.exe` |

## Gerenciamento de Serviços

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Service` | Obtém serviços instalados | `Get-Service` |
| `Start-Service` | Inicia serviços | `Start-Service wuauserv` |
| `Stop-Service` | Interrompe serviços | `Stop-Service wuauserv` |
| `New-Service` | Cria novos serviços | `New-Service -Name MyService -Path c:\scripts\myservice.ps1` |

## Registro do Windows

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-ItemPropertyValue` | Obtém valores de registro | `Get-ItemPropertyValue HKLM:\Software\Microsoft\Windows` |
| `Set-ItemPropertyValue` | Define valores de registro | `Set-ItemPropertyValue HKLM:\Software\Microsoft\Windows -Name EnableAutoUpdate -Value 1` |
| `New-ItemPropertyValue` | Cria novas chaves ou valores de registro | `New-ItemPropertyValue HKLM:\Software\MyCompany -Name MyKey -Type DWORD -Value 123` |
| `Remove-ItemPropertyValue` | Remove chaves ou valores de registro | `Remove-ItemPropertyValue HKLM:\Software\MyCompany\MyKey` |

## Gerenciamento de Computadores Remotos

| Comando | Descrição | Exemplo |
|---|---|---|
| `Enter-PSSession` | Estabelece uma sessão PowerShell remota | `Enter-PSSession server1` |
| `Invoke-Command` | Executa comandos em computadores remotos | `Invoke-Command -ComputerName server1 -ScriptBlock { Get-Process }` |
| `New-PSSession` | Cria uma sessão de PowerShell persistente | `New-PSSession -ComputerName server1 -Name MySession` |
| `Get-WmiObject` | Obtem objetos WMI de computadores remotos | `Get-WmiObject -ComputerName server1 -Class Win32_Process` |

## Práticas Recomendadas

* **Use o modo de compatibilidade:** Execute `Set-ExecutionPolicy RemoteSigned` para permitir a execução de scripts de fontes confiáveis.
* **Segurança:** Cuidado com scripts não confiáveis. Verifique a confiança do script antes de executá-lo.
* **Modularidade:** Divida scripts complexos em módulos reutilizáveis.
* **Documentação:** Documente seus scripts com comentários e descrições de ajuda.
* **Teste:** Teste seus scripts completamente antes de implantá-los.

## Conclusão

Este manual fornece uma base abrangente para o uso avançado do Windows PowerShell 2019. Ao dominar esses comandos e práticas recomendadas, você pode automatizar tarefas complexas, gerenciar sistemas com eficiência e se tornar um administrador do PowerShell proficiente.