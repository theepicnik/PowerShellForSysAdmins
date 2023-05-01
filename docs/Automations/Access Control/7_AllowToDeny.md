---
layout: default
title: Change Allow to Deny
parent: Access Control
grand_parent: Automations
nav_order: 7
permalink: "/automations/ac/allow-to-deny"
---

# Remove Access

---

This PowerShell script block performs the following actions:

1. Sets the `$Path` variable to `"C:\MyFolder"`.
2. Gets the current Access Control List (ACL) for the folder at `$Path` using the `Get-Acl` cmdlet and stores it in the `$ACL` variable.
3. Searches for an access control entry (ACE) in the ACL where the `IdentityReference` property is equal to `"User1"`. This is done using the `Where-Object` cmdlet and the `Access` property of the `$ACL` variable. The result is stored in the `$ACE` variable.
4. Creates a new ACE for `"User1"` with the permission of "ReadAndExecute" and the `AccessControlType` of "Deny". This is stored in the `$NewACE` variable.
5. The `$ACL` variable is updated with the new ACE using the `SetAccessRule` method.
6. The old ACE is removed from the `$ACL` variable using the `RemoveAccessRule` method.
7. Finally, the `$ACL` variable with the updated permissions is applied to the folder at `$Path` using the `Set-Acl` cmdlet.

In summary, this script block removes a specific access control rule (`$ACE`) for `"User1"` and replaces it with a new rule that denies `"User1"` the "ReadAndExecute" permission.

<div class="code-example" markdown="1">
```powershell
$Path = "C:\MyFolder"
$ACL = Get-Acl $Path
$ACE = $ACL.Access | Where-Object {$_.IdentityReference -eq "User1"}
$NewACE = New-Object System.Security.AccessControl.FileSystemAccessRule("User1","ReadAndExecute","Deny")
$ACL.SetAccessRule($NewACE)
$ACL.RemoveAccessRule($ACE)
Set-Acl $Path $ACL
```
</div>