**Manual Avançado do Windows PowerShell 2019: Expansão e Aprofundamento**

## Introdução

O Windows PowerShell é um ambiente de automação e gerenciamento de tarefas do Windows que permite que os usuários executem comandos e gerenciem sistemas local e remotamente. Este manual avançado fornecerá um profundo conhecimento dos recursos avançados do PowerShell 2019, incluindo expansão e aprofundamento.

## Expansão

### Expansão de Variável

* **Get-Variable:** Obter informações sobre as variáveis existentes.
* **Set-Variable:** Criar ou modificar variáveis.
* **$PSVariable:** Substituir o valor de uma variável em um comando.

**Exemplo:**

```powershell
$name = "John"
"Hello, $name!"
```

**Saída:**

```
Hello, John!
```

### Expansão de Propriedade

* **Get-Member:** Obter informações sobre as propriedades de um objeto.
* **$PSProperty:** Substituir o valor de uma propriedade de objeto em um comando.

**Exemplo:**

```powershell
$computer = Get-ComputerInfo
"The operating system of this computer is $computer.OSFullName."
```

**Saída:**

```
The operating system of this computer is Microsoft Windows 10 Pro.
```

### Expansão de Comando

* **Invoke-Command:** Executar um comando em um computador remoto.
* **$PSCommand:** Substituir um comando em um comando.

**Exemplo:**

```powershell
$command = { Get-Process }
Invoke-Command -ComputerName "remotecomputer" -ScriptBlock $command
```

## Aprofundamento

### Canalização

* **|:** Canalizar a saída de um comando para a entrada de outro.
* **Tee-Object:** Copiar a saída de um comando para dois ou mais pipelines.
* **Where-Object:** Filtrar objetos em um pipeline com base em uma condição.

**Exemplo:**

```powershell
Get-Process | Where-Object {$_.CPU -gt 50} | Tee-Object -File "processes.txt"
```

**Saída em processes.txt:**

```
Handle  Name           PID CPU%  Id   SI ProcessName              Threads
------  ----           --- -----  -- -- ---------              -------
4984    Powershell.exe   6504  52    12  S powershell.exe           5
```

### Alias

* **New-Alias:** Criar um alias para um comando.
* **Get-Alias:** Obter informações sobre os aliases existentes.

**Exemplo:**

```powershell
New-Alias gp Get-Process
gp -Name firefox
```

**Saída:**

```
Handle  Name           PID CPU%  Id   SI ProcessName              Threads
------  ----           --- -----  -- -- ---------              -------
1234    firefox.exe     7890  25    11  S firefox.exe             7
```

### Funções

* **New-Function:** Criar uma função personalizada.
* **Get-Function:** Obter informações sobre as funções existentes.

**Exemplo:**

```powershell
function Get-MemoryUsage {
    Get-Process | Select-Object -Property Name, WS
}
```

**Saída:**

```
Name              WS
----              --
powershell.exe   272MB
```

### Módulos

* **Import-Module:** Importar um módulo do PowerShell.
* **Get-Module:** Obter informações sobre os módulos instalados.

**Exemplo:**

```powershell
Import-Module PsFile
Get-File | Sort-Object CreationTime
```

**Saída:**

```
FileName             CreationTime
--------             -------------
file1.txt            2023-03-08 10:32:15
file2.txt            2023-03-08 11:05:32
```

### Cmdlets Avançados

**Gerenciamento de Arquivos:**

* **New-Item:** Criar um novo item de arquivo ou pasta.
* **Remove-Item:** Remover um item de arquivo ou pasta.
* **Copy-Item:** Copiar um item de arquivo ou pasta.

**Gerenciamento de Processos:**

* **Start-Process:** Iniciar um novo processo.
* **Stop-Process:** Interromper um processo em execução.
* **Get-Process:** Obter informações sobre os processos em execução.

**Gerenciamento de Registro:**

* **New-ItemProperty:** Criar uma nova propriedade no registro.
* **Set-ItemProperty:** Definir o valor de uma propriedade do registro.
* **Get-ItemProperty:** Obter o valor de uma propriedade do registro.

### Exceções e Tratamento de Erros

* **try...catch...finally:** Bloco de tentativa e captura para lidar com exceções.
* **Throw:** Lançar uma exceção.

**Exemplo:**

```powershell
try {
    $file = Get-Content "non-existent-file.txt"
}
catch [System.IO.FileNotFoundException] {
    Write-Error "The file does not exist."
}
finally {
    Write-Output "Done processing file."
}
```

**Conclusão:**

Este manual avançado forneceu uma compreensão profunda dos recursos avançados de expansão e aprofundamento do Windows PowerShell 2019. Esses recursos permitem que os usuários automatizem tarefas complexas e gerenciem sistemas com eficiência e precisão. Dominar esses recursos permitirá que os usuários aproveitem todo o potencial do PowerShell e se tornem administradores de sistemas mais competentes.