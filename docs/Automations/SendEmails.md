---
layout: default
title: Send Emails
parent: Automations
nav_order: 5
permalink: "/automations/send-email"
---

# Send Emails

---

`Send-MailMessage` is a PowerShell cmdlet that allows you to send email messages from within a PowerShell script or command line. It allows you to specify the recipient's email address, the sender's email address, the subject of the email, the body of the email, and any attachments.

<div class="code-example" markdown="1">
```powershell
$To = "recipient@example.com"
$From = "sender@example.com"
$Subject = "Example Email"
$Body = @"
Hello,

This is an example email with a multi-line body.

Thank you,
Sender
"@

$SMTPServer = "smtp.example.com"

Send-MailMessage -To $To -From $From -Subject $Subject -Body $Body -SmtpServer $SMTPServer
```
</div>

In this example, we're using the `-Body` parameter to set the body of the email to a multi-line string that contains the message. We're also setting the SMTP server information using the `$SMTPServer` variable. Finally, we're passing these variables to the `Send-MailMessage` cmdlet to send the email.