---
layout: default
title: Scope of Variables
parent: Variables
nav_order: 5
permalink: "/var-scope"
---

# Scope of Variables

---

The scope of a variable in PowerShell refers to the region or context of the script or program where the variable is accessible and can be referenced. In PowerShell, there are several levels of variable scope that determine where a variable can be used:

1. **Global Scope**: A variable that is defined in the global scope is accessible throughout the entire PowerShell session, including any scripts or functions that are executed. Global variables are created by defining them outside of any function or script block, and they can be accessed by any part of the code.

2. **Script Scope**: A variable that is defined in a script is accessible only within that script, and any functions or scripts that it calls. Script variables are created by defining them inside a script block or a function, but outside of any loops or conditional statements.

3. **Local Scope**: A variable that is defined within a function or script block is accessible only within that function or script block. Local variables are created by defining them inside a function or script block, and they are deleted when the function or script block completes.

4. **Private Scope**: A variable that is defined as private is accessible only within the scope where it is defined. Private variables are created by defining them with the "private" scope modifier, and they are deleted when the script block or function completes.

To specify the scope of a variable in PowerShell, you can use the following scope modifiers:

- **Global**: Indicates a global variable
- **Script**: Indicates a script variable
- **Local**: Indicates a local variable
- **Private**: Indicates a private variable

For example, to define a global variable in PowerShell, you can use the following syntax:

<div class="code-example" markdown="1">
```powershell
$global:myGlobalVar = "Hello, World!"
```
</div>

Overall, understanding the scope of variables in PowerShell is important for writing clean, efficient, and secure code. By using the appropriate scope modifiers, you can ensure that your variables are accessible only where they are needed, and avoid potential conflicts or security vulnerabilities.