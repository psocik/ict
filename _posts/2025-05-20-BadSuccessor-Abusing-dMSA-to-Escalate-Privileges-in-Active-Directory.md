---
title: BadSuccessor Abusing dMSA to Escalate Privileges in Active Directory
date: 2025-05-20
categories: [Research]
tags: [Active Directory,Privileged Escalation,Windows Server]
---

**Executive Summary**  
Akamai researcher Yuval Gordon discovered a privilege escalation vulnerability in Windows Server 2025 that allows attackers to compromise any user in Active Directory (AD).  
The attack exploits the delegated Managed Service Account (dMSA) feature that was introduced in Windows Server 2025, works with the default configuration, and is trivial to implement.  
This issue likely affects most organizations that rely on AD. In 91% of the environments we examined, we found users outside the domain admins group that had the required permissions to perform this attack.  
Although Microsoft states they plan to fix this issue in the future, a patch is not currently available. Therefore, organizations need to take other proactive measures to reduce their exposure to this attack. Microsoft has reviewed our findings and approved the publication of this information.  
In this blog post, we provide full details of the attack, as well as detection and mitigation strategies.  

To read the complete article see:  
[Full Article](https://www.akamai.com/blog/security-research/abusing-dmsa-for-privilege-escalation-in-active-directory)