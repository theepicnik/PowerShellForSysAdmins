---
layout: default
title: Remove Access
parent: Access Control
grand_parent: Automations
nav_order: 6
permalink: "/automations/ac/remove-access"
---

# Remove Access

---

The given PowerShell code performs the following actions:

1. Sets the variable `$Path` to the path of the folder for which a specific access rule needs to be removed.
2. Gets the current ACL (access control list) of the folder using the `Get-Acl` cmdlet and assigns it to the variable `$ACL`.
3. Finds the access control entry (ACE) in the `$ACL` object where the `IdentityReference` property is equal to `"User1"`. The resulting ACE is assigned to the variable `$ACE`.
4. Removes the ACE from the `$ACL` object using the `RemoveAccessRule()` method.
5. Sets the modified ACL to the folder using the `Set-Acl` cmdlet.

In summary, the code removes a specific access rule (represented by the ACE) from the folder's ACL, thereby revoking the corresponding permissions for the specified user or group.

<div class="code-example" markdown="1">
```powershell
$Path = "C:\MyFolder"
$ACL = Get-Acl $Path
$ACE = $ACL.Access | Where-Object {$_.IdentityReference -eq "User1"}
$ACL.RemoveAccessRule($ACE)
Set-Acl $Path $ACL
```
</div>