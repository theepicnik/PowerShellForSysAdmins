---
layout: default
title: Logical Operators
parent: Operators
nav_order: 3
permalink: "/operators/logical-operators"
---

# Logical Operators

---

Logical operators in PowerShell are used to combine or negate Boolean expressions and return a Boolean value (`$True` or `$False`) based on the result. PowerShell supports the following logical operators:

1. **And** (`-and`): Returns `$True` if both expressions are `$True`.

2. **Or** (`-or`): Returns `$True` if either expression is `$True`.

3. **Not** (`-not`): Negates the expression and returns `$True` if the expression is `$False`.

Logical operators are typically used in conjunction with comparison operators to create more complex expressions. For example, the following code uses the `-and` operator to combine two comparisons:

<div class="code-example" markdown="1">
```powershell
$a = 10
$b = 5
$c = 8
$a -gt $b -and $a -gt $c
```
</div>

This code will return `$True` if both comparisons are `$True` (i.e., if `$a` is greater than both `$b` and `$c`).

Logical operators can also be used with parentheses to create more complex expressions. For example, the following code uses parentheses to group the `-and` and `-or` operators:

<div class="code-example" markdown="1">
```powershell
$a = 10
$b = 5
$c = 8
($a -gt $b) -and ($b -lt $c -or $a -gt $c)
```
</div>

This code will return `$True` if the first comparison is `$True` AND either the second comparison is `$True` OR the third comparison is `$True`.

Overall, logical operators are an essential tool for creating complex Boolean expressions in PowerShell scripts.