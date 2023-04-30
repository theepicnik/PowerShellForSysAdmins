---
layout: default
title: Using Variables in Scripts
parent: Variables
nav_order: 6
---

# Using Variables in Scripts

---

PowerShell allows you to use variables to store and retrieve data in your scripts. Variables are useful for storing values that you need to use multiple times throughout your script, or for storing values that are computed by your script.

To create a variable in PowerShell, you simply need to assign a value to it using the "=" operator. For example:

<div class="code-example" markdown="1">
$myVariable = "Hello, World!"
</div>

This creates a variable named $myVariable and assigns the string value "Hello, World!" to it. You can then use this variable in your script by enclosing it in "$()" or using it directly. For example:

<div class="code-example" markdown="1">
Write-Host "The value of myVariable is: $myVariable"
</div>

This would output "The value of myVariable is: Hello, World!" to the console.

You can also perform arithmetic and string manipulation operations on variables in PowerShell. For example:

<div class="code-example" markdown="1">
$number1 = 5
$number2 = 10

$sum = $number1 + $number2
Write-Host "The sum of $number1 and $number2 is: $sum"

$greeting = "Hello"
$name = "John"

$message = "$greeting, $name!"
Write-Host $message
</div>

This would output "The sum of 5 and 10 is: 15" and "Hello, John!" to the console.

It's important to note that PowerShell variables are not strongly typed, which means that you can assign any value to a variable at any time, regardless of its original data type. This can be useful in some cases, but can also lead to unexpected results if you're not careful.

Overall, using variables in PowerShell scripts is a powerful way to store and manipulate data. By following best practices for variable naming, scoping, and usage, you can write clean, readable, and maintainable scripts that are easy to understand and modify.