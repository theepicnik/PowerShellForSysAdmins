---
layout: default
title: Switch Statements
parent: Control Flow Statements
nav_order: 2
permalink: "/controlflowstatements/switch-statements"
---

# `switch` Statements

---

In PowerShell, a switch statement is used to evaluate an expression and perform different actions based on the value of that expression. It is similar to a series of if/elseif statements, but it is more concise and easier to read.

The basic syntax of a switch statement is as follows:

<div class="code-example" markdown="1">
```powershell
switch (expression)
{
    value1 { statement(s) }
    value2 { statement(s) }
    default { statement(s) }
}
```
</div>

Here, `expression` is the value that is being evaluated, and `value1`, `value2`, etc. are the possible values that `expression` can have. The statements under each `value` block are executed if `expression` has the corresponding value. If `expression` does not match any of the specified values, the statements under the `default` block are executed.

For example, let's say we want to write a script that takes a number as input and prints out the corresponding month name. We can use a switch statement to accomplish this:

<div class="code-example" markdown="1">
```powershell
$num = Read-Host "Enter a number between 1 and 12"

switch ($num)
{
    1 { Write-Host "January" }
    2 { Write-Host "February" }
    3 { Write-Host "March" }
    4 { Write-Host "April" }
    5 { Write-Host "May" }
    6 { Write-Host "June" }
    7 { Write-Host "July" }
    8 { Write-Host "August" }
    9 { Write-Host "September" }
    10 { Write-Host "October" }
    11 { Write-Host "November" }
    12 { Write-Host "December" }
    default { Write-Host "Invalid input" }
}
```
</div>