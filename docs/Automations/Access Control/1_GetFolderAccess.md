---
layout: default
title: Get Folder Access
parent: Access Control
grand_parent: Automations
nav_order: 1
permalink: "/automations/ac/get-folder-access"
---

# Get Folder Access

---

The `Get-ChildItem` cmdlet retrieves the folders/files properties.

<div class="code-example" markdown="1">
```powershell
$report = @() # create an empty array to store the report data

# get a list of all folders within the specified path and its subfolders
$folders = Get-ChildItem -Path $folderPath -Recurse -Directory -Depth 3

foreach ($folder in $folders) {
    $folderSecurity = Get-Acl -Path $folder.FullName

    # create an object containing the folder properties and add it to the report array
    $folderObject = [PSCustomObject]@{
        FolderPath = $folder.FullName
        Security = $folderSecurity.AccessToString
    }
    $report += $folderObject
}

# export the report to a CSV file
$report | Export-Csv -Path "C:\ExampleFolderPath\FolderPermissions.csv" -NoTypeInformation
```
</div>

---

### Note:

In the above script, the parameters used are:

- **`-Path`**: Specifies the path to the folder to retrieve information from.
- **`-Recurse`**: Includes subdirectories and their contents in the output.
- **`-Directory`**: Retrieves only directories in the specified path.
- **`-Depth`**: Specifies the maximum number of subdirectory levels to include in the output.

So, the command retrieves all the directories within the specified `$folderPath` and its subdirectories, up to a maximum depth of 3 levels.