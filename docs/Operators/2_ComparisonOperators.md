---
layout: default
title: Comparison Operators
parent: Operators
nav_order: 2
permalink: "/operators/comparison-operators"
---

# Comparison Operators

---

Comparison operators are used to compare two values or expressions and return a Boolean result (`$true` or `$false`) indicating whether the comparison is true or false. PowerShell provides several comparison operators, including:

1. **Equal to** (`-eq`): Checks if the left-hand side (LHS) is equal to the right-hand side (RHS). For example, `$a -eq $b` returns `$true` if the value of `$a` is equal to the value of `$b`.

2. **Not equal to** (`-ne`): Checks if the LHS is not equal to the RHS. For example, `$a -ne $b` returns `$true` if the value of `$a` is not equal to the value of `$b`.

3. **Greater than** (`-gt`): Checks if the LHS is greater than the RHS. For example, `$a -gt $b` returns `$true` if the value of `$a` is greater than the value of `$b`.

4. **Less than** (`-lt`): Checks if the LHS is less than the RHS. For example, `$a -lt $b` returns `$true` if the value of `$a` is less than the value of `$b`.

5. **Greater than or equal to** (`-ge`): Checks if the LHS is greater than or equal to the RHS. For example, `$a -ge $b` returns `$true` if the value of `$a` is greater than or equal to the value of `$b`.

6. **Less than or equal to** (`-le`): Checks if the LHS is less than or equal to the RHS. For example, `$a -le $b` returns `$true` if the value of `$a` is less than or equal to the value of `$b`.

7. **Like** (`-like`): Checks if the LHS matches the pattern specified in the RHS. The pattern can include wildcards, such as `*` and `?`. For example, `"hello" -like "h*"` returns `$true`.

8. **Not like** (`-notlike`): Checks if the LHS does not match the pattern specified in the RHS. For example, `"hello" -notlike "w*"` returns `$true`.

9. **Contains** (`-contains`): Checks if the RHS is an element in the LHS. For example, `1, 2, 3 -contains 2` returns `$true`.

10. **Not contains** (`-notcontains`): Checks if the RHS is not an element in the LHS. For example, `1, 2, 3 -notcontains 4` returns `$true`.

These comparison operators can be used with any data type in PowerShell, including strings, numbers, and arrays. They are essential for creating conditional statements in PowerShell scripts and filtering data based on certain criteria.