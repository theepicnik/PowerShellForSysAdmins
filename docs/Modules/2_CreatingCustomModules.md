---
layout: default
title: Creating custom modules
parent: Modules
nav_order: 2
permalink: "/modules/creating-custom-modules"
---

# Creating custom modules

---

In PowerShell, modules are a way to organize, distribute, and manage reusable code. Creating custom modules allows you to package your own PowerShell functions, cmdlets, and scripts so that they can be easily shared and used by others. 

To create a custom module, you can start by defining a module manifest file that includes information about the module such as the name, version, author, and dependencies. Then you can create the folder structure for your module and add your PowerShell scripts and functions to it. You can also include any required files or resources that your module depends on.

Once your module is created, you can install it on your local machine or on remote machines by copying the module folder to the appropriate location or by using the PowerShell Gallery to distribute it to a wider audience. You can also manage your modules using the `Import-Module`, `Get-Module`, and `Remove-Module` cmdlets to load, query, and unload modules as needed.

Overall, creating custom modules in PowerShell is a powerful way to package and share your PowerShell code and to extend the functionality of PowerShell with new commands and functions.

**Here's an example of how to create a custom PowerShell module:**

First, create a new directory with the name of your module. This directory will contain all the files for your module.

<div class="code-example" markdown="1">
   ```shell
   mkdir MyModule
   ```
</div>

Next, create a new PowerShell script file with the same name as your module. This file will contain the code for your module.

<div class="code-example" markdown="1">
   ```powershell
   cd MyModule
   New-Item MyModule.psm1 -ItemType File
   ```
</div>

Open the script file in your preferred text editor and write your module code. Here's an example:

<div class="code-example" markdown="1">
   ```powershell
   function Get-Greeting {
       param(
           [string]$Name = "World"
       )
   
       "Hello, $Name!"
   }
   ```
</div>

This code defines a function called `Get-Greeting` that takes an optional parameter `$Name` (with a default value of "World") and returns a greeting string.

Save your script file and exit your text editor.

Finally, create a new manifest file for your module. This file describes the properties of your module and is required for PowerShell to recognize it as a module. Here's an example:

<div class="code-example" markdown="1">
   ```powershell
   New-ModuleManifest -Path .\MyModule.psd1 -RootModule .\MyModule.psm1 -Author "Your Name" -Description "A sample module for demonstrating custom modules in PowerShell."
   ```
</div>

This command creates a new manifest file called `MyModule.psd1` and specifies that the root module for your module is `MyModule.psm1`. You should also fill in the author and description properties with appropriate values.

Your module is now ready to be used! To test it out, import it into your PowerShell session with the following command:

<div class="code-example" markdown="1">
   ```powershell
   Import-Module .\MyModule
   ```
</div>

You can then use the `Get-Greeting` function by running the following command:

<div class="code-example" markdown="1">
   ```powershell
   Get-Greeting -Name "Alice"
   ```
</div>

This should return the string "Hello, Alice!"