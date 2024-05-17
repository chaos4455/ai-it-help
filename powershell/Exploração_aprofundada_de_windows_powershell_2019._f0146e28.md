**Manual Avançado do Windows PowerShell 2019**

**Introdução**

O Windows PowerShell é uma ferramenta avançada de linha de comando e linguagem de script desenvolvida pela Microsoft. Ele fornece aos usuários um ambiente poderoso para automatizar tarefas, gerenciar sistemas e acessar recursos avançados do Windows. Este manual aborda comandos e procedimentos avançados do Windows PowerShell 2019.

**Comandos Essenciais**

**1. Get-Command:** Retorna uma lista de cmdlets disponíveis no sistema.
**2. Measure-Command:** Mede o tempo de execução de um comando ou script.
**3. Where-Object:** Filtra objetos com base em critérios especificados.
**4. Sort-Object:** Classifica objetos com base nas propriedades especificadas.
**5. Group-Object:** Agrupa objetos com base em propriedades comuns.

**Gerenciamento de Arquivos**

**6. Get-ChildItem (ls):** Retorna uma lista de arquivos e diretórios em um caminho especificado.
**7. New-Item (mkdir):** Cria um novo arquivo ou diretório.
**8. Set-Content (sc):** Define ou substitui o conteúdo de um arquivo.
**9. Get-Content (gc):** Obtém o conteúdo de um arquivo.
**10. Remove-Item (rm):** Exclui um arquivo ou diretório.

**Gerenciamento de Processos**

**11. Get-Process:** Retorna uma lista de processos em execução no sistema.
**12. Start-Process:** Inicia um novo processo.
**13. Stop-Process:** Encerra um processo em execução.
**14. Get-Service:** Retorna uma lista de serviços do Windows.
**15. Start-Service:** Inicia um serviço do Windows.

**Gerenciamento de Registro**

**16. Get-ItemProperty -Path:** Obtém o valor de uma chave de registro.
**17. Set-ItemProperty -Path:** Define o valor de uma chave de registro.
**18. Remove-ItemProperty -Path:** Remove uma chave de registro.
**19. Export-PSSession:** Exporta uma sessão do PowerShell para um arquivo de script.
**20. Import-PSSession:** Importa uma sessão do PowerShell de um arquivo de script.

**Automação de Tarefas**

**21. New-ScheduledTask:** Cria uma nova tarefa agendada.
**22. Get-ScheduledTask:** Retorna uma lista de tarefas agendadas.
**23. Invoke-ScheduledTask:** Invoca uma tarefa agendada.
**24. New-Job:** Cria um novo trabalho em segundo plano.
**25. Get-Job:** Retorna uma lista de trabalhos em segundo plano.

**Gerenciamento de Rede**

**26. Get-NetAdapter:** Retorna uma lista de adaptadores de rede.
**27. Get-NetConnectionProfile:** Retorna uma lista de perfis de conexão de rede.
**28. New-NetIPAddress:** Cria um novo endereço IP em um adaptador de rede.
**29. Get-NetRoute:** Retorna uma tabela de rotas de rede.
**30. Set-NetFirewallRule:** Define regras do firewall de rede.

**Módulos do PowerShell**

**31. Import-Module:** Importa um módulo do PowerShell.
**32. Get-Module:** Retorna uma lista de módulos importados.
**33. Export-Module:** Exporta um módulo do PowerShell para um arquivo.
**34. Install-Module:** Instala um novo módulo do PowerShell do PowerShell Gallery.
**35. Update-Module:** Atualiza um módulo do PowerShell instalado.

**Estruturas de Dados**

**36. New-Object:** Cria um novo objeto.
**37. ConvertTo-Json:** Converte um objeto em um formato JSON.
**38. ConvertFrom-Json:** Converte um formato JSON em um objeto.
**39. Out-GridView:** Exibe objetos em uma tabela pesquisável.
**40. Export-Csv:** Exporta objetos para um arquivo CSV.

**Fluxos de Trabalho**

**41. New-PSWorkflow:** Cria um novo fluxo de trabalho do PowerShell.
**42. Get-PSWorkflow:** Retorna uma lista de fluxos de trabalho em execução.
**43. Suspend-PSWorkflow:** Suspende um fluxo de trabalho em execução.
**44. Resume-PSWorkflow:** Resume um fluxo de trabalho suspenso.