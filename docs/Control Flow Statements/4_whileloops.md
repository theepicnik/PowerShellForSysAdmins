---
layout: default
title: While loops
parent: Control Flow Statements
nav_order: 3
permalink: "/controlflowstatements/while-loops"
---

# `while` loops

---

In PowerShell, a while loop is a control structure that allows you to execute a block of code repeatedly as long as a specified condition is true. The loop will continue to execute until the condition evaluates to false. Here's the basic syntax for a while loop in PowerShell:

<div class="code-example" markdown="1">
```powershell
while (condition) {
    # code to execute while the condition is true
}
```
</div>

The `condition` is a Boolean expression that will be evaluated at the beginning of each iteration of the loop. If the condition is true, the code block inside the curly braces will be executed. Once the code block is finished executing, the condition is checked again, and the loop continues until the condition is false.

Here's an example of a while loop that counts from 1 to 5:

<div class="code-example" markdown="1">
```powershell
$i = 1
while ($i -le 5) {
    Write-Host "Count: $i"
    $i++
}
```
</div>

In this example, the variable `$i` is initialized to 1. The while loop continues to execute as long as `$i` is less than or equal to 5. Inside the loop, the current value of `$i` is output using the `Write-Host` cmdlet, and `$i` is incremented by 1. The loop will continue to execute until `$i` is equal to 6, at which point the condition will be false, and the loop will terminate.