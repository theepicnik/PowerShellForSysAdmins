---
layout: default
title: Creating functions
parent: Functions
nav_order: 1
permalink: "/functions/creating-functions"
---

# Creating functions

---

In PowerShell, functions are created using the `function` keyword, followed by the function name and a set of curly braces `{}`. Inside the curly braces, you define the code that the function will execute when it is called.

Here is an example of a simple function that takes two parameters and returns their sum:

<div class="code-example" markdown="1">
```powershell
function Add-Numbers {
    param(
        [int]$num1,
        [int]$num2
    )
    return $num1 + $num2
}
```
</div>

In this example, the function is called `Add-Numbers` and takes two parameters, both of which are integers. Inside the function, the two parameters are added together using the `+` operator, and the result is returned using the `return` keyword.

To call this function, you simply use its name followed by the parameters you want to pass in, like this:

<div class="code-example" markdown="1">
```powershell
Add-Numbers -num1 5 -num2 7
```
</div>

This would return the value `12`, which is the sum of 5 and 7.