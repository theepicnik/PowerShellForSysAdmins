---
layout: default
title: Storage Report
parent: Automations
nav_order: 7
permalink: "/automations/storage-report"
---

# Storage Report

---
`Get-ChildItem` is a PowerShell cmdlet that retrieves the child items (files, directories, and other items) in one or more specified locations. It is used to navigate through a file system and obtain information about the contents of directories, including files and subdirectories. Get-ChildItem can be used to display the contents of a single directory or multiple directories, and can be customized with various parameters to filter the results. This cmdlet is very useful for performing operations such as file copying, file removal, and file manipulation in a script.

The `-Recurse` parameter in PowerShell is used with `Get-ChildItem` cmdlet to retrieve all items (files and directories) recursively from the specified directory and its subdirectories. This means that it will retrieve items not only from the specified directory, but also from its child directories, their child directories, and so on.

The `-Depth` parameter specifies the maximum depth of recursion. For example, `-Depth 1` will only retrieve items from the specified directory, while `-Depth 2` will retrieve items from the specified directory and its immediate child directories, and so on.

So, `-Recurse -Depth 3` will retrieve all items from the specified directory and its subdirectories up to a maximum depth of 3 levels.

Here's an example script to get storage report:

<div class="code-example" markdown="1">
```powershell
# Set email parameters
$smtpServer = "smtp.example.com"
$fromAddress = "admin@example.com"
$toAddress = "user@example.com"
$subject = "File and Folder Report"
$body = "Please find attached the report for file and folder sizes."

# Set path to report file
$reportFile = "C:\Reports\FileFolderReport.csv"

# Get report data
$data = Get-ChildItem -Path "C:\" -Recurse -Depth 3 | Select-Object Name, Length, @{Name="Path";Expression={$_.FullName}} | ConvertTo-Csv -NoTypeInformation

# Save report data to file
$data | Out-File -FilePath $reportFile

# Send email with report attachment
Send-MailMessage -To $toAddress -From $fromAddress -Subject $subject -Body $body -SmtpServer $smtpServer -Attachments $reportFile
```
</div>

This script will:

1. Set the parameters for sending the email, including the SMTP server, from and to email addresses, subject, and body message.
2. Set the path to the report file.
3. Use the `Get-ChildItem` cmdlet to retrieve information about files and folders under the `C:\` drive up to a depth of 3. The `Select-Object` cmdlet is used to retrieve the `Name`, `Length`, and `Path` properties of each item. The output is then piped to the `ConvertTo-Csv` cmdlet to convert the data to a CSV format.
4. Save the report data to a file at the specified path using the `Out-File` cmdlet.
5. Send an email using the `Send-MailMessage` cmdlet with the report file attached as the email attachment.

Please note that this script will retrieve information about all files and folders under the `C:\` drive up to a depth of 3, which may take some time to complete depending on the size and complexity of the file system. You may need to modify the parameters of the `Get-ChildItem` cmdlet to suit your needs.