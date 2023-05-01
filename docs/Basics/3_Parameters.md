---
layout: default
title: Working with Parameters
parent: Basics
nav_order: 3
permalink: "/basics/parameters"
---

# Working with Parameters

---

In PowerShell, parameters are used to pass input values to cmdlets and scripts. Parameters are defined in the cmdlet or script, and can be mandatory or optional. They can also have default values, and can accept input from the pipeline.

Here are some examples of working with parameters in PowerShell:

1. **Defining parameters in a cmdlet**: To define a parameter in a cmdlet, use the `[Parameter()]` attribute followed by the name of the parameter. For example, the following code defines a parameter named "Name" with a default value of "World":

<div class="code-example" markdown="1">
```powershell
function HelloWorld {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$false)]
        [string]$Name = "World"
    )
    Write-Output "Hello, $Name!"
}
```
</div>

2. **Passing parameters to a cmdlet**: To pass a value to a parameter, include the parameter name and value separated by a space. For example, to pass the value "John" to the "Name" parameter in the "HelloWorld" cmdlet, use the following command:

<div class="code-example" markdown="1">
```powershell
HelloWorld -Name John
```
</div>

3. **Using pipeline input with parameters**: Some cmdlets accept input from the pipeline, which allows you to chain cmdlets together to perform complex tasks. To use pipeline input with a cmdlet that has parameters, you can use the $_ variable to refer to the input value. For example, the following code uses the Get-ChildItem cmdlet to retrieve a list of files in a directory, and then pipes the output to the Set-ItemOwner cmdlet to change the owner of the files:

<div class="code-example" markdown="1">
```powershell
Get-ChildItem C:\Temp | Set-ItemOwner -Owner "John"
```
</div>

These are just a few examples of working with parameters in PowerShell. Parameters provide a powerful way to customize and automate cmdlets and scripts, and allow you to perform complex tasks with ease.