---
layout: default
title: Duplicate Folder Access
parent: Access Control
grand_parent: Automations
nav_order: 4
permalink: "/automations/ac/duplicate-folder-access"
---

# Duplicate Folder Access

---

The command `Get-Acl -Path "C:\Dog.txt"` retrieves the access control list (ACL) for the file "Dog.txt" located in the C:\ directory.

The `Set-Acl -Path "C:\Cat.txt"` part of the command sets the ACL for the file "Cat.txt" located in the C:\ directory to the same ACL retrieved from the "Dog.txt" file.

In short, this command copies the file permissions from one file ("Dog.txt") to another file ("Cat.txt").

<div class="code-example" markdown="1">
```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```
</div>