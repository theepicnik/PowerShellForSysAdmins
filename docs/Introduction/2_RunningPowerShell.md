---
layout: default
title: Running PowerShell
parent: Introduction
nav_order: 2
permalink: "/introduction/running-powershell"
---

# Running PowerShell

---

In PowerShell, you can run commands using the PowerShell console or by executing PowerShell scripts. Here are the steps to run PowerShell commands:

## PowerShell Console:
1. Open the PowerShell console by searching for "PowerShell" in the Start menu or by running the `pwsh` command in the terminal.
2. Type the command you want to run and press Enter.
3. The output of the command will be displayed in the console.

## PowerShell Script:
1. Open a text editor such as Notepad or Visual Studio Code.
2. Write the PowerShell command in the editor.
3. Save the file with a ".ps1" extension (for example, "myscript.ps1").
4. Open the PowerShell console.
5. Navigate to the directory where the script is saved using the `cd` command.
6. Run the script by typing its name (including the ".ps1" extension) and press Enter.
7. The output of the script will be displayed in the console.

Note: By default, PowerShell restricts the execution of scripts for security reasons. To run scripts, you need to change the execution policy by running the command `Set-ExecutionPolicy RemoteSigned` or `Set-ExecutionPolicy Unrestricted` in the PowerShell console. It's recommended to change the execution policy back to the default setting after running the script by running the command `Set-ExecutionPolicy Restricted`.






