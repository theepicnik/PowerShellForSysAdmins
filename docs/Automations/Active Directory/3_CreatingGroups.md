---
layout: default
title: Creating Groups
parent: Active Directory
grand_parent: Automations
nav_order: 3
permalink: "/automations/ad/creating-groups"
---

# Creating Groups

---

The `New-ADGroup` cmdlet creates a new Active Directory group with the specified parameters:

<div class="code-example" markdown="1">
```powershell
New-ADGroup -Name "Test Group" -SamAccountName "Test Group" -DisplayName "Security Group Name" `
            -Description "Brief description" -Server "theepicnik.local" `
            -GroupCategory Security -GroupScope Global -Path "CN=Groups,DC=theepicnik,DC=local"
```
</div>

- `-Name`: Specifies the name of the group.
- `-SamAccountName`: Specifies the SAM account name of the group.
- `-DisplayName`: Specifies the display name of the group.
- `-Description`: Specifies a brief description of the group.
- `-Server`: Specifies the Active Directory Domain Services instance to connect to, in the format of a fully qualified domain name (FQDN).
- `-GroupCategory`: Specifies the group category. In this case, `Security` indicates a security group.
- `-GroupScope`: Specifies the group scope. In this case, `Global` indicates a global group.
- `-Path`: Specifies the distinguished name (DN) of the container where the group is created.