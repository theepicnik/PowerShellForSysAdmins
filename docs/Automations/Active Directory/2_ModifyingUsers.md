---
layout: default
title: Modifying Users
parent: Active Directory
grand_parent: Automations
nav_order: 2
permalink: "/automations/ad/modifying-users"
---

# Modifying Users

---

Please find the examples below to modify the user using PowerShell:

<div class="code-example" markdown="1">
```powershell
#Import the ActiveDirectory module
Import-Module ActiveDirectory

#Add User into Group
Add-ADGroupMember -Identity "Sales" -Members "jdoe"

#Remove User from Group
Remove-ADGroupMember -Identity "Marketing" -Members "jdoe"

#Clear Attribute of AD Account
#In the example, we are clearing a userParameter attribute of the AD account jdoe.
Set-ADUser -Identity "jdoe" -Clear userParameter

#Modify attribute value of AD Account
#-Title is the name of the attribute in below exmaple.
Set-ADUser -Identity "jdoe" -Title "Manager"

#Unlock AD Account
Unlock-ADAccount -Identity "Username"

#Find disabled accounts
Search-ADAccount -AccountDisabled -UsersOnly

#Get list of AD users with properties DisplayName, SamAccountName, UserPrincipalName, EmailAddress, Enabled, SmartcardLogonRequired, MemberOf and export it in csv
Get-ADUser -Filter * -Properties DisplayName, SamAccountName, UserPrincipalName, EmailAddress, Enabled, SmartcardLogonRequired, MemberOf `
| Select-Object DisplayName, SamAccountName, UserPrincipalName, EmailAddress, Enabled, SmartcardLogonRequired, @{Name="MemberOf";Expression={($_.MemberOf | Get-ADGroup `
| Select-Object -ExpandProperty Name) -join ", "}} `
| Export-Csv -Path "C:\Users\UserName\Documents\ADUsers.csv" -NoTypeInformation

```
</div>

{: .note }
The backtick (`) is a line continuation character in PowerShell, used to break a long command into multiple lines for readability.