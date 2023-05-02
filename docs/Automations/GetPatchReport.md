---
layout: default
title: Get Patch Report
parent: Automations
nav_order: 5
permalink: "/automations/patch-report"
---

# Get Patch Report

---

You can use the `Get-Hotfix` cmdlet in PowerShell to retrieve the installed hotfixes on a remote server. Here is an example script to check the latest installed patch ID and date on remote servers:

<div class="code-example" markdown="1">
```powershell
$Computers = "Server1", "Server2", "Server3"
$Result = @()

foreach ($Computer in $Computers) {
    $Hotfix = Get-Hotfix -ComputerName $Computer | Sort-Object InstalledOn -Descending | Select-Object -First 1
    $Result += [PSCustomObject]@{
        ComputerName = $Computer
        HotfixID = $Hotfix.HotfixID
        InstalledOn = $Hotfix.InstalledOn
    }
}

$Result | Export-Csv -Path "C:\Hotfixes.csv" -NoTypeInformation
```
</div>

In this script, we first define the list of remote servers in the `$Computers` variable. We then loop through each computer and use the `Get-Hotfix` cmdlet to retrieve the installed hotfixes. We sort the list of hotfixes by the `InstalledOn` property in descending order and select the first one using the `Select-Object` cmdlet.

Finally, we create a custom object that includes the computer name, hotfix ID, and installation date, and add it to an array. After processing all the servers, we output the results in a csv. The `-NoTypeInformation` parameter is used to exclude the type information from the CSV file.