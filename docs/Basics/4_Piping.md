---
layout: default
title: Piping cmdlets together
parent: Basics
nav_order: 4
permalink: "/basics/piping"
---

# Piping cmdlets together

---

Piping cmdlets together is a powerful feature of PowerShell that allows you to pass the output of one cmdlet as input to another cmdlet. This makes it easy to perform complex tasks by chaining together simple commands.

To pipe cmdlets together, use the `|` symbol (also known as the pipeline operator) to pass the output of one cmdlet as input to the next cmdlet. For example, to get a list of files in a directory and then sort them by size, you could use the following command:

<div class="code-example" markdown="1">
```powershell
Get-ChildItem C:\Temp | Sort-Object Length
```
</div>

In this example, the "Get-ChildItem" cmdlet retrieves a list of files in the "C:\Temp" directory, and then passes that list to the "Sort-Object" cmdlet. The "Sort-Object" cmdlet sorts the list of files by their length, which is then displayed in the console.

You can also use piping to filter the output of cmdlets. For example, to get a list of files in a directory and then filter the list to show only files with a ".txt" extension, you could use the following command:

<div class="code-example" markdown="1">
```powershell
Get-ChildItem C:\Temp | Where-Object {$_.Extension -eq ".txt"}
```
</div>

In this example, the "Where-Object" cmdlet is used to filter the list of files passed from the "Get-ChildItem" cmdlet. The "-eq" operator is used to compare the file extension to the string ".txt", and only files with a matching extension are displayed in the console.

Piping cmdlets together is a powerful feature that can simplify complex tasks and make your PowerShell scripts more efficient and effective.