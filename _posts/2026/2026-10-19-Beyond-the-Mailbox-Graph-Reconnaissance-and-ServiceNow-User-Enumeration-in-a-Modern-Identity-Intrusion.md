---
title: Beyond the Mailbox Graph Reconnaissance and ServiceNow User Enumeration in a Modern Identity Intrusion
date: 2026-10-19
categories: [CYBERSECURITY]
tags: [MICROSOFT,GRAPH,SERVICENOW,IDENTITY,INTRUSION]
---

## Beyond the Mailbox: Graph Reconnaissance and ServiceNow User Enumeration in a Modern Identity Intrusion

Sophos X-Ops uncovered a new technique used by attackers to enumerate user accounts in ServiceNow by abusing Microsoft Graph permissions. This novel approach allowed attackers to identify valid user accounts within a target's ServiceNow environment by querying the Microsoft Graph API, then exploiting these identified accounts to validate login credentials via ServiceNow's login portal. The attacker's motive was to gain access to target accounts by exploiting weak or compromised credentials, which could then be used for further network infiltration. 🚀

The initial compromise in the observed incident stemmed from a VPN solution, through which the adversary established a foothold in the victim's environment. Post-initial access, the attacker pivoted to Identity Access Management (IAM) abuse and targeted Microsoft 365. This included reconnaissance of the Microsoft Graph, followed by enumeration of valid users in ServiceNow and credential validation.

Our discovery highlights a more sophisticated approach where attackers abuse permissions associated with the Microsoft Graph API to enumerate users in third-party applications like ServiceNow. This method circumvents direct interaction with ServiceNow's login page for initial enumeration, making detection more challenging. 

The specific technique involved abusing specific permissions within the Microsoft Graph API to enumerate users in ServiceNow. The attacker leveraged a Microsoft 365 tenant with a configured custom connector to ServiceNow. The custom connector was configured with an App Registration that was granted the following permissions: User.Read, User.Read.All, Directory.Read.All. The attacker used the command `Get-AzureADApplication -SearchString "ServiceNow"` to retrieve information about the App Registration. The attacker then leveraged the Microsoft Graph API to enumerate users present in ServiceNow using the command `https://graph.microsoft.com/v1.0/servicePrincipals/<app-id>/owners`. This Graph API command, when executed with appropriate permissions, returned a list of users associated with the ServiceNow application registration. The attackers used this information to identify valid usernames for the ServiceNow portal, subsequently using these UPNs in credential validation attempts against the ServiceNow login portal.

This method of user enumeration is particularly insidious because it does not directly interact with the ServiceNow login page during the enumeration phase. This makes traditional detection mechanisms that monitor failed login attempts or unusual login patterns on ServiceNow less effective. Instead, the activity is hidden within legitimate Microsoft Graph API calls, making it harder to distinguish malicious reconnaissance from benign operations. The observed attack highlights the evolving sophistication of identity-centric threats.

To mitigate the risks associated with this type of attack, organizations should consider implementing strong authentication for all accounts, enforcing multi-factor authentication (MFA) for all user accounts. Additionally, regularly review App Registration permissions, ensuring applications are only granted the minimum necessary permissions (least privilege principle). Organizations should also monitor Microsoft Graph API activity, looking for unusual patterns of activity, such as a single IP address making a large number of queries to `servicePrincipals/<app-id>/owners`.

### Key Indicators of Compromise (IoCs)
- `Get-AzureADApplication -SearchString "ServiceNow"` for retrieving information about the App Registration for ServiceNow.
- `https://graph.microsoft.com/v1.0/servicePrincipals/<app-id>/owners` for enumerating the owners of the App Registration.

[Read full article](https://news.sophos.com/en-us/blog/graph-reconnaissance-and-servicenow-user-enumeration-in-a-modern-identity-intrusion)