---
layout: default
title: Modifying Groups
parent: Active Directory
grand_parent: Automations
nav_order: 4
permalink: "/automations/ad/modifying-groups"
---

# Modifying Groups

---

Please find the examples below to modify the group using PowerShell:

<div class="code-example" markdown="1">
```powershell
#Add Group into Group
Add-ADGroupMember -Identity "Sales" -Members "Sales Managers"

#Remove Group from Group
Remove-ADGroupMember -Identity "Sales" -Members "Sales Managers"
```
</div>