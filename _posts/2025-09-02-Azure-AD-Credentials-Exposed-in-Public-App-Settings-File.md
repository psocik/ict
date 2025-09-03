---
title: Azure AD Credentials Exposed in Public App Settings File
date: 2025-09-02
categories: [SECURITY]
tags: [AZURE AD,CREDENTIALS,SECURITY,APPLICATION CONFIGURATION]
---

Resecurity’s HUNTER Team discovered that application credentials, specifically the ClientId and ClientSecret, were left exposed in a publicly accessible appsettings.json file.

These credentials allow direct authentication against Microsoft’s OAuth 2.0 endpoints. In practice, this means an attacker could impersonate the trusted application and access sensitive Microsoft 365 resources. Depending on the permissions granted to the compromised app, attackers might:

- Retrieve files and emails from SharePoint, OneDrive or Exchange Online.
- Enumerate users, groups and directory roles in Azure AD.
- Abuse the Microsoft Graph API to escalate privileges or maintain persistence.
- Deploy malicious applications under the organization’s tenant.

In ASP.NET Core applications, appsettings.json is a central configuration file. It usually stores database connection strings, API keys and cloud service credentials. When Azure AD details, such as ClientId, TenantId and ClientSecret, are included, the file becomes a blueprint not just for how the application runs, but also for how attackers might break in.

To read the complete article see: [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/azure-ad-credentials-exposed/) 

