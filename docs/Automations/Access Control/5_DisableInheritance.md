---
layout: default
title: Disable Inheritance
parent: Access Control
grand_parent: Automations
nav_order: 5
permalink: "/automations/ac/disable-inheritance"
---

# Disable Inheritance

---

The given PowerShell commands are used to disable inheritance of permissions and **convert inherited permissions to explicit permissions**. 

First, the `Get-Acl` cmdlet is used to retrieve the Access Control List (ACL) for the file at `C:\Pets\Dog.txt`. This ACL object is then stored in the variable `$NewAcl`. 

Next, the `SetAccessRuleProtection()` method of the ACL object is used to disable inheritance of permissions and convert inherited permissions to explicit permissions. The first parameter `$isProtected` is set to `$true` to prevent inheritance of permissions from the parent folder. The second parameter `$preserveInheritance` is set to `$true` to preserve the existing inherited permissions as explicit permissions. 

Finally, the `Set-Acl` cmdlet is used to set the modified ACL object to the file at `C:\Pets\Dog.txt`. This replaces the previous ACL with the new one that has disabled inheritance and converted inherited permissions to explicit permissions.

<div class="code-example" markdown="1">
```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```
</div>