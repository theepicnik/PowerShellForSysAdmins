---
layout: default
title: if Statements
parent: Control Flow Statements
nav_order: 1
permalink: "/controlflowstatements/if-statements"
---

# `if` Statements

---

If statements in PowerShell are used to execute a block of code if a condition is true and skip the code if the condition is false. The syntax for an If statement in PowerShell is as follows:

<div class="code-example" markdown="1">
```powershell
if (condition) {
    # code to execute if condition is true
}
```
</div>

The condition in the parentheses must evaluate to either $true or $false. The code to execute if the condition is true is enclosed in curly braces. If the condition is false, the code inside the curly braces will be skipped.

Here's an example of an If statement:

<div class="code-example" markdown="1">
```powershell
$age = 25

if ($age -lt 18) {
    Write-Output "You are not old enough to vote."
} else {
    Write-Output "You are old enough to vote."
}
```
</div>

In this example, if the value of `$age` is less than 18, the code inside the first block will be executed and the output will be "You are not old enough to vote." If the value of `$age` is greater than or equal to 18, the code inside the second block will be executed and the output will be "You are old enough to vote."

If statements can also be nested inside each other to create more complex conditions. For example:

<div class="code-example" markdown="1">
```powershell
$grade = "A"

if ($grade -eq "A") {
    if ($score -ge 90) {
        Write-Output "Excellent!"
    } else {
        Write-Output "Good job!"
    }
} else {
    Write-Output "You need to work harder."
}
```
</div>

In this example, the If statement checks if the value of `$grade` is "A". If it is, it checks the value of `$score` and outputs "Excellent!" if the score is greater than or equal to 90, or "Good job!" if the score is less than 90. If the value of `$grade` is not "A", it outputs "You need to work harder."