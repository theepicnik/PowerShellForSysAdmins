---
layout: default
title: Update Folder Access
parent: Access Control
grand_parent: Automations
nav_order: 3
permalink: "/automations/ac/update-folder-access"
---

# Update Folder Access

---

The code snippet is used to modify the permissions of an existing user or group that already has permissions on a folder. Here's what the commands do:

1. Set the variable `$Path` to the path of the folder whose permissions need to be modified.
2. Use the `Get-Acl` cmdlet to get the access control list (ACL) of the folder and assign it to the `$ACL` variable.
3. Use the `Where-Object` cmdlet to filter the access control entries (ACEs) in the `$ACL` variable and find the one with an `IdentityReference` of `"User1"`.
4. Set the `FileSystemRights` property of the ACE to `"FullControl"`.
5. Use the `SetAccessRule` method of the `$ACL` variable to update the ACE with the modified `FileSystemRights` value.
6. Use the `Set-Acl` cmdlet to apply the modified ACL to the folder specified by the `$Path` variable.

In short, this code snippet modifies the permissions of a specific user or group that already has permissions on a folder.

<div class="code-example" markdown="1">
```powershell
# Modify permiison of existing IdentityReference (i.e. certain user/group whose permissions already exists on the folder)
$Path = "C:\MyFolder"
$ACL = Get-Acl $Path
$ACE = $ACL.Access | Where-Object {$_.IdentityReference -eq "User1"}
$ACE.FileSystemRights = "FullControl"
$ACL.SetAccessRule($ACE)
Set-Acl $Path $ACL
```
</div>