**Manual Avançado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é uma estrutura de linha de comando e linguagem de script projetada para gerenciar e automatizar tarefas no Windows. Este manual fornecerá instruções avançadas sobre o uso do PowerShell 2019.

**Comandos Avançados**

**1. Get-Command**
* Obter informações sobre comandos disponíveis e seus parâmetros.
```powershell
Get-Command -Name *get-process*
```

**2. Format-List**
* Formatar a saída de outros comandos em uma lista legível.
```powershell
Get-Process | Format-List -Property Name, Id
```

**3. Select-Object**
* Selecionar propriedades específicas da saída de outros comandos.
```powershell
Get-Process | Select-Object -Property Name, Id, StartTime
```

**4. Where-Object**
* Filtrar objetos com base em uma condição.
```powershell
Get-Process | Where-Object {$_.Name -like "powershell*"}
```

**5. Sort-Object**
* Classificar objetos com base em uma ou mais propriedades.
```powershell
Get-Process | Sort-Object -Property StartTime -Descending
```

**6. Group-Object**
* Agrupar objetos com base em uma ou mais propriedades.
```powershell
Get-Process | Group-Object -Property ProcessName
```

**7. Measure-Object**
* Calcular estatísticas agregadas em objetos.
```powershell
Get-Process | Measure-Object -Property WorkingSet -Average
```

**8. New-Object**
* Criar novas instâncias de objetos.
```powershell
New-Object -TypeName System.IO.FileInfo -ArgumentList "C:\myfile.txt"
```

**9. Set-Variable**
* Definir e manipular variáveis.
```powershell
$myVariable = "Hello World"
```

**10. Get-Variable**
* Obter informações sobre variáveis.
```powershell
Get-Variable -Name myVariable
```

**11. Remove-Variable**
* Remover variáveis.
```powershell
Remove-Variable -Name myVariable
```

**12. Invoke-Expression**
* Executar comandos dinamicamente a partir de uma string.
```powershell
Invoke-Expression "Get-Process | Format-List"
```

**13. Out-File**
* Direcionar a saída de comandos para um arquivo.
```powershell
Get-Process | Out-File -FilePath "process-list.txt"
```

**14. Tee-Object**
* Copiar a saída de comandos para vários destinos.
```powershell
Get-Process | Tee-Object -Variable outputFile -OutFile "process-list.txt"
```

**15. Export-Csv**
* Exportar objetos como arquivos CSV.
```powershell
Get-Process | Export-Csv -Path "process-list.csv" -NoTypeInformation
```

**16. New-WebServiceProxy**
* Criar objetos proxy para acesso a serviços da Web.
```powershell
New-WebServiceProxy -Uri "http://example.com/service"
```

**17. Invoke-WebRequest**
* Fazer solicitações HTTP e HTTPS.
```powershell
Invoke-WebRequest -Uri "http://example.com"
```

**18. Send-MailMessage**
* Enviar mensagens de email.
```powershell
Send-MailMessage -From "sender@example.com" -To "recipient@example.com" -Subject "Test Email" -Body "Hello World"
```

**19. Get-ChildItem**
* Obter informações sobre arquivos e diretórios.
```powershell
Get-ChildItem -Path "C:\mydirectory" -Recurse
```

**20. Set-Location**
* Alterar o diretório atual.
```powershell
Set-Location -Path "C:\mydirectory"
```

**21. Remove-Item**
* Remover arquivos e diretórios.
```powershell
Remove-Item -Path "C:\mydirectory" -Recurse
```

**22. New-Item**
* Criar arquivos e diretórios.
```powershell
New-Item -Path "C:\mydirectory\myfile.txt" -Type File
```

**23. Rename-Item**
* Renomear arquivos e diretórios.
```powershell
Rename-Item -Path "C:\mydirectory\myfile.txt" -NewName "newmyfile.txt"
```

**24. Move-Item**
* Mover arquivos e diretórios.
```powershell
Move-Item -Path "C:\mydirectory\myfile.txt" -Destination "C:\newdirectory"
```

**25. Copy-Item**
* Copiar arquivos e diretórios.
```powershell
Copy-Item -Path "C:\mydirectory\myfile.txt" -Destination "C:\newdirectory"
```

**26. Get-Member**
* Obter informações sobre os membros (métodos e propriedades) de objetos.
```powershell
Get-Process | Get-Member
```

**27. Invoke-Method**
* Chamar métodos de objetos.
```powershell
$process = Get-Process "Notepad"
Invoke-Method -InputObject $process -Name Stop
```

**28. Get-Event**
* Obter informações sobre eventos gerados por objetos.
```powershell
Get-Event -SourceIdentifier "Microsoft-Windows-WMIService"
```

**29. Register-Event**
* Registrar manipuladores de eventos para objetos.
```powershell
Register-Event -SourceIdentifier "Microsoft-Windows-WMIService" -EventName "ProcessStart" -Action { Write-Host "Process Started" }
```

**30. Unregister-Event**
* Desregistrar manipuladores de eventos de objetos.
```powershell
Unregister-Event -SourceIdentifier "Microsoft-Windows-WMIService" -EventName "ProcessStart"
```

**31. New-Alias**
* Criar aliases para comandos.
```powershell
New-Alias -Name gp -Value Get-Process
```

**32. Remove-Alias**
* Remover aliases.
```powershell
Remove-Alias -Name gp
```

**33. Measure-Command**
* Medir o tempo e os recursos necessários para executar comandos.
```powershell
Measure-Command { Get-Process }
```

**34. Import-Module**
* Importar módulos do PowerShell que contêm comandos adicionais.
```powershell
Import-Module -Name PSDesiredStateConfiguration
```

**35. Export-Module**
* Exportar módulos do PowerShell para compartilhá-los com outras pessoas.
```powershell
Export-Module -Name MyModule -Path "C:\mymodule.psd1"
```

**36. Invoke-Command**
* Executar comandos em computadores remotos.
```powershell
Invoke-Command -ComputerName Server1 -ScriptBlock { Get-Process }
```

**37. Enter-PSSession**
* Estabelecer uma sessão persistente com um computador remoto.
```powershell
Enter-PSSession -ComputerName Server1
```

**38. Exit-PSSession**
* Encerrar uma sessão persistente com um computador remoto.
```powershell
Exit-PSSession
```

**39. Start-Job**
* Iniciar trabalhos em segundo plano.
```powershell
Start-Job -ScriptBlock { Get-Process }
```

**40. Receive-Job**
* Obter os resultados de trabalhos em segundo plano.
```powershell
Receive-Job -JobId 1
```

**41. Stop-Job**
* Parar trabalhos em segundo plano.
```powershell
Stop-Job -JobId 1
```

**42. Remove-Job**
* Remover trabalhos em segundo plano.
```powershell
Remove-Job -JobId 1
```

**43. Write-Host**
* Escrever mensagens na tela.
```powershell
Write-Host "Hello World"
```

**44. Read-Host**
* Ler entrada do usuário da tela.
```powershell
$input = Read-Host "Enter your name"
```