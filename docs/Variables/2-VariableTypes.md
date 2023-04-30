---
layout: default
title: Variable Types
parent: Variables
nav_order: 2
permalink: "/variables/var-types"
---

# Introduction to PS Variables

---

1. **Scalar Variables** - Scalar variables in PowerShell are used to store a single value, such as a string, integer, or boolean. Scalar variables can be created by assigning a value to a variable name using the "=" operator. For example, `$x = "Hello, World!"` creates a scalar variable named `$x` that holds the string "Hello, World!".

2. **Arrays** - Arrays in PowerShell are used to store a collection of values of the same data type. Arrays can be created by enclosing a comma-separated list of values in square brackets. For example, `$myArray = 1, 2, 3, 4` creates an array named `$myArray` that contains the values 1, 2, 3, and 4.

3. **Hash Tables** - Hash tables in PowerShell are used to store key-value pairs, where each key is unique and associated with a value. Hash tables can be created by enclosing a comma-separated list of key-value pairs in "@{ }" symbols. For example, `$myHash = @{ Name="John"; Age=30; City="New York" }` creates a hash table named `$myHash` that contains the keys "Name", "Age", and "City", and their associated values.

4. **Environment Variables** - Environment variables in PowerShell are used to store system-wide configuration settings or values that are used by different processes or applications. Environment variables can be created and accessed using the `Get-ChildItem Env:` command in PowerShell. For example, `$env:Path` is an environment variable that contains the list of directories that Windows searches for executable files.

It's important to note that variables in PowerShell are not strongly typed, meaning you don't need to declare the data type of a variable before using it. PowerShell automatically assigns a data type to a variable based on the value that is assigned to it. Also, PowerShell allows you to create custom types using classes and enums.