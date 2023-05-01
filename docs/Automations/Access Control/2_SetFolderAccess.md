---
layout: default
title: Set Folder Access
parent: Access Control
grand_parent: Automations
nav_order: 2
permalink: "/automations/ac/set-folder-access"
---

# Set Folder Access

---

This PowerShell script is used to set custom file system permissions to a specified folder for a specified user account. 

Here's a breakdown of what the script does:
- Sets the folder path and user account to which permissions need to be granted.
- Defines the custom file system rights that need to be granted. These rights are defined using the `System.Security.AccessControl.FileSystemRights` enum.
- Creates a new access rule with the customized permissions using the `System.Security.AccessControl.FileSystemAccessRule` class.
- Gets the current Access Control List (ACL) for the specified folder using the `Get-Acl` cmdlet.
- Adds the new access rule to the ACL using the `SetAccessRule` method of the ACL object.
- Sets the modified ACL to the specified folder using the `Set-Acl` cmdlet.

This script can be modified to grant different permissions to the specified user account by modifying the `FileSystemRights` enum.

<div class="code-example" markdown="1">
```powershell
# Set the folder path and user account
$FolderPath = "C:\MyFolder"
$Account = "Domain\UserName"

# Define custom file system rights. Comment the ones not required.
$FileSystemRights = [System.Security.AccessControl.FileSystemRights]::ListDirectory -bor `
                    [System.Security.AccessControl.FileSystemRights]::ReadData -bor `
                    [System.Security.AccessControl.FileSystemRights]::WriteData -bor `
                    [System.Security.AccessControl.FileSystemRights]::CreateFiles -bor `
                    [System.Security.AccessControl.FileSystemRights]::CreateDirectories -bor `
                    [System.Security.AccessControl.FileSystemRights]::AppendData -bor `
                    [System.Security.AccessControl.FileSystemRights]::ReadExtendedAttributes -bor `
                    [System.Security.AccessControl.FileSystemRights]::WriteExtendedAttributes -bor `
                    [System.Security.AccessControl.FileSystemRights]::Traverse -bor `
                    [System.Security.AccessControl.FileSystemRights]::ExecuteFile -bor `
                    [System.Security.AccessControl.FileSystemRights]::DeleteSubdirectoriesAndFiles -bor `
                    [System.Security.AccessControl.FileSystemRights]::ReadAttributes -bor `
                    [System.Security.AccessControl.FileSystemRights]::WriteAttributes -bor `
                    [System.Security.AccessControl.FileSystemRights]::Write -bor `
                    [System.Security.AccessControl.FileSystemRights]::Delete -bor `
                    [System.Security.AccessControl.FileSystemRights]::ReadPermissions -bor `
                    [System.Security.AccessControl.FileSystemRights]::Read -bor `
                    [System.Security.AccessControl.FileSystemRights]::ReadAndExecute -bor `
                    [System.Security.AccessControl.FileSystemRights]::Modify -bor `
                    [System.Security.AccessControl.FileSystemRights]::ChangePermissions -bor `
                    [System.Security.AccessControl.FileSystemRights]::TakeOwnership -bor `
                    [System.Security.AccessControl.FileSystemRights]::Synchronize -bor `
                    [System.Security.AccessControl.FileSystemRights]::FullControl


# Create a new access rule with customized permissions
$InheritanceFlags = [System.Security.AccessControl.InheritanceFlags]::None
$PropagationFlags = [System.Security.AccessControl.PropagationFlags]::NoPropagateInherit
$AccessControlType = [System.Security.AccessControl.AccessControlType]::Allow
$AccessRule = New-Object System.Security.AccessControl.FileSystemAccessRule($Account,$FileSystemRights,$InheritanceFlags,$PropagationFlags,$AccessControlType)

# Get the current ACL for the folder
$Acl = Get-Acl $FolderPath

# Add the new access rule to the ACL
$Acl.SetAccessRule($AccessRule)

# Set the modified ACL to the folder
Set-Acl $FolderPath $Acl
```
</div>