---
layout: default
title: Installing Softwares and Services
parent: Automations
nav_order: 3
permalink: "/automations/installing-softwares-and-services"
---

# Installing and Configuring Software and Services

---

In this article, we will discuss how to install and configure software and services with PowerShell.

## Installing Software

Installing software with PowerShell is relatively simple. To install software, we use the `Install-Package` cmdlet. This cmdlet is used to install packages from a package repository. For example, to install the latest version of Google Chrome, we can use the following command:

<div class="code-example" markdown="1">
```powershell
Install-Package -Name GoogleChrome
```
</div>

This command will install the latest version of Google Chrome from the default package repository. If you want to install a specific version of the software, you can use the `-Version` parameter, followed by the version number.

<div class="code-example" markdown="1">
```powershell
Install-Package -Name GoogleChrome -Version 112.0.5615.137
```
</div>

In addition to the default package repository, PowerShell allows us to create our own private package repositories. This is particularly useful in environments where we need to install software that is not available in the default package repository.

## Configuring Services

Configuring services with PowerShell can also be done with ease. PowerShell provides the `Set-Service` cmdlet, which can be used to modify the configuration of a Windows service. For example, to set the startup type of the Windows Update service to Automatic, we can use the following command:

<div class="code-example" markdown="1">
```powershell
Set-Service -Name wuauserv -StartupType Automatic
```
</div>

This command will set the startup type of the Windows Update service to Automatic, which means the service will start automatically when the system is started.

In addition to setting the startup type of a service, we can also start, stop, and restart services using PowerShell. The `Start-Service`, `Stop-Service`, and `Restart-Service` cmdlets can be used for this purpose.

<div class="code-example" markdown="1">
```powershell
Start-Service -Name wuauserv
Stop-Service -Name wuauserv
Restart-Service -Name wuauserv
```
</div>