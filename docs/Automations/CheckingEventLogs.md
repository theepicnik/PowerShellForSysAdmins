---
layout: default
title: Checking Event Logs
parent: Automations
nav_order: 4
permalink: "/automations/checking-event-logs"
---

# Checking Event Logs

To check event logs using PowerShell, you can use the `Get-EventLog` cmdlet. Here is an example:

<div class="code-example" markdown="1">
```powershell
Get-EventLog -LogName System -Newest 100
```
</div>

This command retrieves the 100 newest events from the "System" log. You can replace "System" with the name of any other log that you want to check. 

You can also use the `-After` and `-Before` parameters to filter the events based on their date/time. For example, to retrieve events from the last 24 hours, you can use the following command:

<div class="code-example" markdown="1">
```powershell
Get-EventLog -LogName System -After (Get-Date).AddDays(-1)
```
</div>

You can also use the `Where-Object` cmdlet to filter the events based on other criteria, such as the event ID or the source. For example, to retrieve events with the ID 1001 from the "Application" log, you can use the following command:

<div class="code-example" markdown="1">
```powershell
Get-EventLog -LogName Application | Where-Object {$_.EventID -eq 1001}
```
</div>

This command retrieves all events from the "Application" log and filters them based on the event ID using the `Where-Object` cmdlet. You can replace "Application" with the name of any other log and 1001 with the ID of any other event that you want to filter by.

---

## Practical Example:

PowerShell script that can check the account locked event ID on multiple domain controllers for the last 2 days and output it in a CSV file:

<div class="code-example" markdown="1">
```powershell
# List of domain controllers to check
$DomainControllers = "dc1.theepicknik.local", "dc2.theepicknik.local", "dc3.theepicknik.local"

# Account locked event ID
$EventID = 4740

# Get current time and time 2 days ago
$Now = Get-Date
$TwoDaysAgo = $Now.AddDays(-2)

# Create an empty array to store the events
$Events = @()

# Loop through each domain controller
foreach ($DC in $DomainControllers) {
    # Get the event logs for the last 2 days
    $Logs = Get-WinEvent -ComputerName $DC -FilterHashtable @{
        LogName = 'Security'
        ID = $EventID
        StartTime = $TwoDaysAgo
        EndTime = $Now
    }
    
    # Loop through each event and add it to the array
    foreach ($Log in $Logs) {
        $Events += [PSCustomObject]@{
            Time = $Log.TimeCreated
            User = $Log.Properties[1].Value
            Computer = $Log.MachineName
            Description = $Log.Message
        }
    }
}

# Output the events to a CSV file
$Events | Export-Csv -Path 'C:\Logs\AccountLockoutEvents.csv' -NoTypeInformation
```
</div>

This script first defines the domain controllers to check, the account locked event ID, and the time range to search for events. It then loops through each domain controller, retrieves the relevant event logs, extracts the desired information, and adds it to an array. Finally, the array is output to a CSV file.