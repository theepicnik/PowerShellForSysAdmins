---
layout: default
title: Basic Syntax
parent: Basics
nav_order: 1
permalink: "/basics/basic-syntax"
---

# Basic PowerShell Syntax

---

PowerShell is built on the .NET framework and uses a syntax similar to C#. Here are the basic elements of PowerShell syntax:

**Cmdlet**: A cmdlet is a pre-built command in PowerShell that performs a specific task. Cmdlets have a verb-noun naming convention, for example, "Get-ChildItem" or "Set-ItemProperty". Cmdlets can be used alone or with additional parameters.

**Parameters**: Parameters provide additional information to the cmdlet to modify its behavior or provide additional context. Parameters are added after the cmdlet and are preceded by a hyphen. For example, in the cmdlet "Get-ChildItem -Path C:\Users", "-Path" is the parameter and "C:\Users" is the value of the parameter.

**Variables**: Variables are used to store data in PowerShell. Variables start with the "$" symbol, followed by the variable name. For example, "$myVariable".

**Operators**: PowerShell supports a wide range of operators for arithmetic, comparison, logical, and other operations. Some examples include "+" for addition, "-" for subtraction, "-eq" for equality comparison, "-gt" for greater than comparison, "-and" for logical and, and "-or" for logical or.

**Comments**: Comments are used to add context to PowerShell code and are preceded by the "#" symbol. Comments are ignored by PowerShell when the code is executed.

Here is an example of basic PowerShell syntax:

<div class="code-example" markdown="1">
```powershell
Get-ChildItem -Path C:\Users | Where-Object { $_.Name -like '*john*' } | Select-Object Name, LastWriteTime
```
</div>

In this example, the cmdlet "Get-ChildItem" is used to get a list of items in the "C:\Users" directory. The pipe symbol "|" is used to pass the output to the next cmdlet. The cmdlet "Where-Object" filters the output to only include items with "john" in the name. Finally, the cmdlet "Select-Object" selects only the "Name" and "LastWriteTime" properties of the remaining items.




