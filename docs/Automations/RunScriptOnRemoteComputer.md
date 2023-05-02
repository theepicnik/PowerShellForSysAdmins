---
layout: default
title: Run Script on Remote Computer
parent: Automations
nav_order: 4
permalink: "/automations/run-script-remotely"
---

# Run Script on Remote Computer

---

To run a query remotely, you can use PowerShell's `Invoke-Command` cmdlet. This cmdlet allows you to run commands or scripts on one or more remote computers.

Here is an example of how to use `Invoke-Command` to run a query on a remote computer:

<div class="code-example" markdown="1">
```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-Service }
```
</div>

In this example, we're using the `Invoke-Command` cmdlet to run a PowerShell script block on a remote computer named `Server01`. The script block is simply calling the `Get-Service` cmdlet to retrieve information about all the services running on `Server01`.

Note that you'll need to have the appropriate permissions to run remote commands on the remote computer, and the remote computer must have PowerShell remoting enabled.