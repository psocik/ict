---
title: ConnectWise Shuts Off Cloud Services After Unauthorized Access to Microsoft 365 Tenants
date: 2026-10-19
categories: [CYBERSECURITY]
tags: [CONNECTWISE,CLOUD SERVICES,MICROSOFT 365,UNAUTHORIZED ACCESS,CYBERSECURITY]
---

## ConnectWise Shuts Off Cloud Services After Unauthorized Access to Microsoft 365 Tenants

🚨 **IT management software provider ConnectWise has suspended access to several of its cloud services** after discovering that unauthorized actors gained access to Microsoft 365 tenants. ConnectWise began investigating suspicious activity on **October 15**. By **October 17**, the company identified "unauthorized access to application identities within the ConnectWise Cloud Backup environment." 

This discovery has led to several ConnectWise cloud services, including **Cloud Backup** (previously known as SkyKick), **SaaS Security**, and **Cloud Management**, being taken offline while the company investigates the incident. ConnectWise stated, "We understand that this interruption affects your ability to support your customers. We do not yet have a confirmed restoration time and will share a timeline as soon as we can do so reliably," in an update on **October 19**.

The action was taken due to the discovery of unauthorized access to application identities associated with ConnectWise Cloud Backup. An attacker could potentially abuse this access to gain unauthorized entry into customers' Microsoft 365 environments by authenticating to the app using the tenant's tooling, leveraging this access to obtain tokens with the app's existing permissions, thereby providing access to the environment. With this access, an attacker could reach the same directories and data as a backup service, putting tenant users' corporate data at risk. 

Justin Kohler, chief product officer at SpecterOps, explained, "The credential belongs to the application itself, so the attacker inherited the permissions granted to it. Multi-factor authentication (MFA) doesn't apply because this is an application sign-in, so no user, device, or MFA prompt is involved." He added, "Backup tools need broad access to read and restore data. Anyone holding the app's credential can reach the same mailboxes, OneDrive and SharePoint files, Teams data, and directory information the backup service can."

Cybersecurity analysts at Huntress have been monitoring the ConnectWise incident. In a blog post, they noted that in at least one customer tenant being observed, the attacker assigned themselves a **Global Administrator role**, using this access to attempt to modify permissions for other applications, including an MSP management application and Huntress's own security application. While ConnectWise has stated it has yet to discover any indication that partner backup data has been compromised, the company will "continue investigating potential unauthorized access." Currently, there is no attribution regarding who could be behind the attack. ConnectWise mentioned, "We cannot discuss threat actor attribution at this time. Our focus is on investigation, remediation, and supporting affected partners and their customers."

ConnectWise has also advised its customers to take the following actions to help identify any potential incidents:
- Verify the status of the listed application connections and keep affected applications disabled until ConnectWise provides restoration instructions.
- Preserve available sign-in and audit records promptly, while taking any urgent containment action.
- Review application and user authentication, application credentials and federation trusts, directory roles, owners, consent grants, and recent policy changes.
- Check for unauthorized mailbox forwarding, inbox or transport rules, and delegated mailbox access.
- Investigate any other identities changed or used during suspicious activity; disabling the original applications does not remove those separate access paths.

For more details, [Read full article](https://www.infosecurity-magazine.com/news/connectwise-shuts-off-cloud/).