---
title: Even MOAR Powershell Analyzing Entra Logins
date: 2026-08-21
categories: [SECURITY]
tags: [POWERSHELL,ENTRA,LOGINS,SECURITY,ANALYSIS]
---

## Even MOAR Powershell: Analyzing Entra Logins

One thing that folks never seem to do after "going to the CLOOOOUUUUD" is to look at their logs, logs that they would have checked daily when things were on-premise. 📊 One log that really bears looking at is the log of successful and failed logins. 

The call for this involves importing the `Microsoft.Graph.Reports` module, connecting with `AuditLog.Read.All`, `Directory.Read.All` scopes, and then using `Get-MgAuditLogSignIn`. Examining a log object might show "an interactive login to OWA, which failed on a conditional access check." The article notes that the 'location' often indicates why this failed. 

To obtain specific details, "The command below shows us pulling only failed logins ("status/errorCode ne 0"), extracting the geo location info, and also the failure reason." This allows the retrieval of fields like `CreatedDateTime`, `UserPrincipalName`, `IPAddress`, `City`, `State`, `Country`, and `FailureReason`. This reveals "that otherwise hidden information!" It's this sort of list where you'll see password sprays show up. 🔍 An example shows such an attack where "the last two lines show the account is locked." Moreover, "The 'IP address with malicious activity' alert generally means that this is a rotating proxy service, and the IP's in it have been fully or partially enumerated as 'bad'."

"Or, looking for successful logins from unexpected countries," provides another critical detection method. This involves setting "the array of 'expected' Countries" and using `Get-MgAuditLogSignIn` with the filter `status/errorCode eq 0` to "Get all successful logins". Subsequently, the data is processed to "remove expected countries, and what is left is unexpected." In writing this diary, I found multiple password spray attacks. Applying these log analysis techniques "helped the client tighten up their conditional access policies, which was one of our goals going in." Utilizing Entra logs can "effect a change in your configuration (in conditional access policies for instance)." 

[Read full article](https://isc.sans.edu/forums/diary/Even%20MOAR%20Powershell,%20looking%20at%20Entra%20logins%20-%20the%20good,%20the%20bad%20and%20the%20password%20sprays/33268/)