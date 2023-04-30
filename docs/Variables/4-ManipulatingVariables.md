---
layout: default
title: Manipulating Variables
parent: Variables
nav_order: 4
permalink: "/var-manipulation"
---

# Manipulating Variables

---

1. **Concatenation**: You can concatenate (combine) strings or variables by using the "+" operator. For example, `$firstName = "John"; $lastName = "Doe"; $fullName = $firstName + " " + $lastName` creates a variable named `$fullName` that holds the value "John Doe".

2. **Casting**: You can convert a variable from one data type to another by using the cast operator. For example, `[int]$myVar = "123"` creates a variable named `$myVar` that holds the integer value 123.

3. **Math Operations**: You can perform arithmetic operations on numeric variables using the standard arithmetic operators. For example, `$x = 10; $y = 5; $z = $x + $y` creates a variable named `$z` that holds the value 15.

4. **Comparison Operators**: You can compare the values of two variables using comparison operators such as "-eq" (equal to), "-ne" (not equal to), "-lt" (less than), "-le" (less than or equal to), "-gt" (greater than), and "-ge" (greater than or equal to). For example, `$x = 10; $y = 5; $x -gt $y` returns "True" because 10 is greater than 5.

5. **Array Operations**: You can manipulate array variables using various array operations, such as adding or removing elements from an array, sorting an array, or filtering an array based on specific criteria.

6. **String Manipulation**: You can manipulate string variables using various string operations, such as trimming leading or trailing whitespace from a string, converting a string to uppercase or lowercase, or replacing a specific substring in a string.

Overall, manipulating variables in PowerShell involves performing various operations on the variables, such as concatenation, casting, arithmetic, comparison, and array or string operations, based on your specific needs and use case.