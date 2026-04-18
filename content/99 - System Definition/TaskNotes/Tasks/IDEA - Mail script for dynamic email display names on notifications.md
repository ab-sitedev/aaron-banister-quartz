---
title: IDEA - Mail script for dynamic email display names on notifications
status: open
priority: normal
scheduled: 2026-04-08
contexts:
  - work
dateCreated: 2026-04-08T11:42:31.455-05:00
dateModified: 2026-04-08T12:12:03.938-05:00
tags:
  - idea
  - task
---

The mail script calls a script include
The script include references a custom table
The custom table stores rule sets (table conditions) and display names like:

| Table    | Condition                       | Notification Sender Display Name |
| -------- | ------------------------------- | -------------------------------- |
| incident | assignment_group=verily-support | Verily Questions                 |
### **Result: FROM Verily Questions <oneoncology@service-now.com>**

<div style="font-family: lato,arial,sans; line-height: 24px;">
<div style="text-align: center; line-height: 36px; padding-bottom: 24px; border-bottom: 1px solid #DADDE2;"><span style="font-size: 24px;">We received your request</span></div>
<div style="font-size: 16px; padding-top: 24px; padding-bottom: 16px;">Hi ${caller_id.first_name},</div>
<div style="font-size: 16px; padding-bottom: 16px;">We created <span style="font-weight: 600;">${task_effective_number}</span> to handle your recent request.</div>
<div style="font-size: 16px;">You can view your request to track updates and make changes.</div>
<div style="font-size: 16px;">${mail_script:incident_link}</div>
<div style="font-size: 20px; padding-top: 32px; padding-bottom: 16px; line-height: 30px;"><span style="font-weight: 600;">About this request</span></div>
<div style="font-size: 16px;">${mail_script:incident_was_opened}</div>
<div style="font-size: 16px; padding-bottom: 32px;">Short description: <span style="font-weight: 600;">${short_description}</span></div>
<div style="font-size: 16px; padding-bottom: 8px;">Thank you,<br>Service Desk Team</div>
</div>
