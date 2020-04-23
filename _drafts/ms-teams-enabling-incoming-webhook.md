---
title: MS Teams - Enabling Incoming Webhook
date: 2020-04-22 22:00:00 +0000
categories:
- Teams
tags:
- Teams

---
In our tenant we have all 3rd Party Apps within Microsoft Teams **disabled**. We wanted to use the "Incoming Webhooks" App, but couldn't add it as it was not shown.

After some discussions with the Microsoft Support, we recevied the following information:   

_"Working with Engineering Team we have confirmed that Incoming WebHooks App, although it is registered as Microsoft Corp distributed, the reason why it is considered a 3rd party App is because Microsoft does not own the Endpoints of it."_

So the "Incoming Webhook" App is registered as an 3rd Party App and needs to be allowed.

After allowing 3rd Party Apps, we were able to create the "Incoming Webhook", but with an and not usable.

 

Confirmed no EWS Allow list is used in the company, and confirmed in the Org-Wide app settings Allow third party apps is toggled on.

Confirmed Incoming WebHooks is correctly showing “allowed” in Manage apps Portal.

And while checking then the Organization Configuration we noticed **ConnectorsEnabled** was set to false.

**Resolution:**

After allowing Incoming WebHooks in the Third Party allow configuration, making sure Third Party apps is toggled on for the Org-Wide app settings and setting ConnectorsEnabled to True with PowerShell cmdlet “Set-OrganizationConfig” we have confirmed the issue is resolved.