---
layout: default
title: Creating Users
parent: Active Directory
grand_parent: Automations
nav_order: 1
permalink: "/automations/ad/creating-users"
---

# Creating Users

---

The `New-ADUser` cmdlet creates a new Active Directory user with the specified parameters:

<div class="code-example" markdown="1">
```powershell
#Import the ActiveDirectory module
Import-Module ActiveDirectory

$domainName = "theepicnik.local"
$firstName = "John"
$lastName = "Doe"
$userName = "johndoe"
$password = ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force
$ou = "OU=Users,DC=theepicnik,DC=local"

#Create account using New-ADUser
New-ADUser -Name "$firstName $lastName" -SamAccountName $userName -AccountPassword $password -Enabled $true -Path $ou -Server $domainName
```
</div>

This script creates a new user account with the specified properties.

   - `-Name`: Specifies the display name of the user account.
   - `-SamAccountName`: Specifies the SAM account name of the user account.
   - `-AccountPassword`: Specifies the password for the user account.
   - `-Enabled`: Enables the user account.
   - `-Description`: Specifies the description for the user account.
   - `-Path`: Specifies the OU where the user account is created.
   - `-Server`: Specifies the AD domain where the user account is created.

You can modify this example to match your specific environment and create user accounts with the desired properties.

{: .note }
You can use the `Get-Help` cmdlet with the `-Parameter` option to list all available parameters for a PowerShell cmdlet. Just replace the name of the cmdlet with 'New-ADUser' in below command.

<div class="code-example" markdown="1">
```powershell
Get-Help New-ADUser -Parameter *
```
</div>