---
layout: default
title: Installing and managing modules
parent: Modules
nav_order: 1
permalink: "/modules/installing-managing-modules"
---

# Installing and managing modules

---

In PowerShell, modules are used to organize and distribute scripts, functions, and other PowerShell-related content. They are essentially packages that can be installed and imported into a PowerShell session or script to provide additional functionality.

To install a module, you can use the `Install-Module` cmdlet. For example, to install the Azure PowerShell module, you can use the following command:

<div class="code-example" markdown="1">
```powershell
Install-Module -Name Az
```
</div>

This command will download and install the latest version of the Azure PowerShell module from the PowerShell Gallery.

Once a module is installed, you can import it into your PowerShell session or script using the `Import-Module` cmdlet. For example, to import the Azure PowerShell module, you can use the following command:

<div class="code-example" markdown="1">
```powershell
Import-Module -Name Az
```
</div>

This command will import the Azure PowerShell module into your current session, allowing you to use the cmdlets and functions provided by the module.

You can also use the `Get-InstalledModule` cmdlet to view a list of all installed modules on your system, and the `Uninstall-Module` cmdlet to remove a module if you no longer need it.