---
layout: default
title: For Statements
parent: Control Flow Statements
nav_order: 3
permalink: "/controlflowstatements/for-statements"
---

# `for` Statements

---

In PowerShell, a `for` loop is a type of control flow statement that allows you to iterate over a collection of items, executing a block of code for each item. The basic syntax for a `for` loop is:

<div class="code-example" markdown="1">
```powershell
for (initialization; condition; increment) {
    # Code to execute
}
```
</div>

Here's a breakdown of each component:

- `initialization`: This is where you initialize the loop variable(s). This is typically where you set a counter variable to an initial value.
- `condition`: This is the condition that is checked before each iteration of the loop. If the condition is true, the loop body is executed. If it's false, the loop is exited.
- `increment`: This is the code that is executed after each iteration of the loop. Typically, this is where you increment the loop variable(s).

Here's an example of a `for` loop that prints the numbers 1 to 10:

<div class="code-example" markdown="1">
```powershell
for ($i = 1; $i -le 10; $i++) {
    Write-Output $i
}
```
</div>

In this example, `$i = 1` initializes the loop variable to 1, `$i -le 10` is the condition that checks if `$i` is less than or equal to 10, and `$i++` increments `$i` by 1 after each iteration.

`for` loops can also be used to iterate over collections such as arrays and hashtables. In these cases, you can use the `foreach` keyword instead of `for`. The syntax for a `foreach` loop is:

<div class="code-example" markdown="1">
```powershell
foreach ($item in $collection) {
    # Code to execute
}
```
</div>

Here's an example of a `foreach` loop that iterates over an array:

<div class="code-example" markdown="1">
```powershell
$fruits = @("apple", "banana", "orange")

foreach ($fruit in $fruits) {
    Write-Output $fruit
}
```
</div>

In this example, `$fruits` is an array of strings, and `$fruit` is the loop variable that holds each element of the array as the loop iterates. The loop body simply prints each element to the console using `Write-Output`.