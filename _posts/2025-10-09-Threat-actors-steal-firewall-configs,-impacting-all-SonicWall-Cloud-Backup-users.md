---
title: Threat actors steal firewall configs, impacting all SonicWall Cloud Backup users
date: 2025-10-09
categories: [SECURITY]
tags: [SONICWALL,CLOUD BACKUP,SECURITY INCIDENT]
---

Threat actors stole firewall configuration backups from SonicWall’s cloud service, impacting all users of its MySonicWall cloud backup platform.

The company told affected customers to import new preference files. However, importing the new file disrupts IPSec VPNs, TOTP bindings, and user access. After import, users must reconfigure VPN pre-shared keys and reset TOTP along with user passwords. To reduce downtime, SonicWall recommends importing during maintenance windows, off-hours, or low-activity periods since the process reboots the firewall immediately.

SonicWall has completed its investigation, conducted in collaboration with leading IR Firm, Mandiant, into the scope of a recent cloud backup security incident. The investigation confirmed that an unauthorized party accessed firewall configuration backup files for all customers who have used SonicWall’s cloud backup service. The files contain encrypted credentials and configuration data; while encryption remains in place, possession of these files could increase the risk of targeted attacks. We are working to notify all impacted partners and customers and have released tools to assist with device assessment and remediation. Updated and comprehensive final lists of impacted devices are now available in the MySonicWall portal (Navigate to the Product Management > Issue List). To help prioritize remediation efforts, the lists include a field that identifies each device as either 1) “Active – High Priority” (devices with internet-facing services enabled); 2) “Active – Lower Priority” (devices without internet-facing services); or 3) “Inactive” (devices that have not pinged home for 90 days).

To read the complete article see:
[Security Affairs Article](https://securityaffairs.com/183154/security/threat-actors-steal-firewall-configs-impacting-all-sonicwall-cloud-backup-users.html)  
