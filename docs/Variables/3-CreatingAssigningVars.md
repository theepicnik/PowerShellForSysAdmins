---
layout: default
title: Creating and Assigning Variables
parent: Variables
nav_order: 3
---

# Creating and Assigning Variables

---

To create a variable in PowerShell, you simply assign a value to a variable name using the "=" operator. For example, to create a scalar variable named `$myVar` that holds the value "Hello, World!", you would type `$myVar = "Hello, World!"` in PowerShell.

You can also create an empty variable by assigning it a value of `$null`, like this: `$myVar = $null`. This creates an empty scalar variable named $myVar that does not have a value assigned to it.

To assign a new value to a variable, simply assign a different value to the variable name using the "=" operator. For example, to change the value of $myVar to "Goodbye, World!", you would type $myVar = "Goodbye, World!".

When you assign a value to a variable in PowerShell, PowerShell automatically determines the data type of the variable based on the value assigned to it. For example, if you assign a string value to a variable, PowerShell will create a scalar variable of type "string". Similarly, if you assign an array to a variable, PowerShell will create an array variable of the appropriate data type.

You can also create variables with dynamic names using variable expansion. For example, to create a variable with a name that includes the value of another variable, you can use the "$()" syntax. For example, to create a variable named $myVar1, you can use the following code: $varName = "myVar1"; New-Variable -Name $("$" + $varName) -Value "Hello, World!".

Overall, creating and assigning variables in PowerShell is a simple process that involves assigning a value to a variable name using the "=" operator. PowerShell automatically determines the data type of the variable based on the value assigned to it.