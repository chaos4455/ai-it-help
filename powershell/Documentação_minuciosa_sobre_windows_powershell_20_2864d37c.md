**Manual Avançado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é uma estrutura de script e linha de comando poderosa que permite aos administradores automatizar tarefas, gerenciar sistemas e acessar recursos avançados do Windows. O PowerShell 2019 traz vários novos recursos e aprimoramentos, tornando-o uma ferramenta ainda mais versátil para administradores.

**Comandos Básicos**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Command` | Obtém comandos disponíveis | `Get-Command *Get*` |
| `Get-Help` | Obtém ajuda sobre um comando | `Get-Help Get-Process` |
| `Set-Location` | Altera o diretório atual | `Set-Location C:\Temp` |
| `Get-Member` | Obtém os membros (propriedades, métodos e eventos) de um objeto | `Get-Member Get-Process` |

**Gerenciamento de Processos**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Process` | Obtém os processos em execução | `Get-Process | Select-Object Name, ID, CPU` |
| `Start-Process` | Inicia um novo processo | `Start-Process notepad.exe` |
| `Stop-Process` | Encerra um processo | `Stop-Process notepad.exe` |
| `Suspend-Process` | Suspende um processo | `Suspend-Process notepad.exe` |

**Gerenciamento de Arquivos**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-ChildItem` | Obtém os itens filho (arquivos e diretórios) de um diretório | `Get-ChildItem C:\Temp` |
| `New-Item` | Cria um novo arquivo ou diretório | `New-Item -Path C:\Temp\teste.txt -Type File` |
| `Remove-Item` | Remove um arquivo ou diretório | `Remove-Item C:\Temp\teste.txt` |
| `Copy-Item` | Copia um arquivo ou diretório | `Copy-Item C:\Temp\teste.txt C:\Destino\teste.txt` |

**Trabalhando com Registros**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-ItemProperty` | Obtém uma propriedade do registro | `Get-ItemProperty -Path HKCU:\Software\Microsoft\Windows` |
| `New-ItemProperty` | Cria uma nova propriedade do registro | `New-ItemProperty -Path HKCU:\Software\Microsoft\Windows -Name NoSleep -Value 1` |
| `Set-ItemProperty` | Define uma propriedade do registro | `Set-ItemProperty -Path HKCU:\Software\Microsoft\Windows -Name NoSleep -Value 0` |
| `Remove-ItemProperty` | Remove uma propriedade do registro | `Remove-ItemProperty -Path HKCU:\Software\Microsoft\Windows -Name NoSleep` |

**Gerenciamento de Serviços**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-Service` | Obtém os serviços instalados | `Get-Service | Select-Object Name, Status` |
| `Start-Service` | Inicia um serviço | `Start-Service "Windows Update"` |
| `Stop-Service` | Para um serviço | `Stop-Service "Windows Update"` |
| `Restart-Service` | Reinicia um serviço | `Restart-Service "Windows Update"` |

**Gerenciamento de Eventos**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Get-EventLog` | Obtém os logs de eventos | `Get-EventLog -LogName System` |
| `Write-EventLog` | Grava um evento no log de eventos | `Write-EventLog -LogName System -Source "Teste" -Message "Evento de teste"` |
| `Clear-EventLog` | Limpa um log de eventos | `Clear-EventLog -LogName System` |

**Gerenciamento de Grupo de Computadores**

| Comando | Descrição | Exemplo |
|---|---|---|
| `New-ADOrganizationalUnit` | Cria uma nova unidade organizacional do Active Directory | `New-ADOrganizationalUnit -Name "Usuários Avançados"` |
| `Add-ADUser` | Adiciona um novo usuário do Active Directory | `Add-ADUser -Name "João Silva" -DisplayName "João Silva"` |
| `Get-ADGroup` | Obtém os grupos do Active Directory | `Get-ADGroup | Select-Object Name, Description` |
| `Add-ADGroupMember` | Adiciona um usuário a um grupo do Active Directory | `Add-ADGroupMember "Usuários Avançados" "João Silva"` |

**Outros Comandos Úteis**

| Comando | Descrição | Exemplo |
|---|---|---|
| `Where-Object` | Filtra objetos com base em critérios | `Get-Process | Where-Object {$_.Name -like "*notepad*"}` |
| `Select-Object` | Seleciona propriedades específicas de objetos | `Get-Process | Select-Object Name, ID, CPU` |
| `Sort-Object` | Ordena objetos com base em propriedades | `Get-Process | Sort-Object Name` |
| `Measure-Object` | Mede o desempenho de um comando | `Get-Process | Measure-Object -Average CPU` |

**Passos Avançados**

**Criando Funções**

As funções permitem agrupar comandos relacionados e reutilizá-los. Para criar uma função:

1. Abra o Editor do Windows PowerShell (PowerShell ISE).
2. Clique em "Novo" > "Módulo".
3. Nomeie o módulo e clique em "OK".
4. Adicione o seguinte código ao arquivo `.psm1` do módulo:

```powershell
function NomeDaFuncao {
    <# Descrição da função #>
    param (
        <# Parâmetros da função #>
    )

    <# Corpo da função #>
}
```

**Usando Módulos**

Os módulos estendem a funcionalidade do PowerShell. Para importar um módulo:

1. Abra o PowerShell.
2. Digite o seguinte comando:

```powershell
Import-Module NomeDoModulo
```

**Escrevendo Scripts**

Os scripts são arquivos que contêm comandos do PowerShell. Para criar um script:

1. Abra o Editor de Bloco de Notas.
2. Adicione o seguinte código ao arquivo:

```powershell
<# Descrição do Script #>
<# Parâmetros do Script #>

<# Corpo do Script #>
```

3. Salve o arquivo com a extensão `.ps1`.

**Conclusão**

Este manual fornece uma visão abrangente dos recursos avançados do Windows PowerShell 2019. Ao dominar esses comandos e técnicas, você pode automatizar tarefas complexas, gerenciar sistemas com eficiência e aproveitar todo o poder e versatilidade do PowerShell.