---
title: xHunt APT Hackers Attacking Microsoft Exchange and IIS Web Servers to Deploy Custom Backdoors
date: 2025-12-15
categories: [CYBER SECURITY]
tags: [APT,CYBER SECURITY,MICROSOFT EXCHANGE]
---

The xHunt advanced persistent threat group has firmly established itself as a sophisticated cyber-espionage actor, orchestrating targeted campaigns against organizations in Kuwait. Since its emergence in 2018, the group has focused intently on the government, shipping, and transportation sectors. Their operations are characterized by the use of a custom and evolving toolkit, with many tools bearing names derived from the Hunter x Hunter anime series. This unique naming convention accompanies a persistent drive to infiltrate critical infrastructure and harvest sensitive intelligence through bespoke malware variants like Hisoka and Netero.

Attack vectors employed by xHunt are diverse, often beginning with strategic watering hole attacks or the direct compromise of web-facing Microsoft Exchange and IIS servers. One particularly novel technique involves injecting hidden HTML tags into compromised government websites, redirecting visitors to actor-controlled servers to harvest NTLM hashes. This passive credential theft allows the attackers to gain unauthorized access without immediate detection, utilizing the collected data to compromise further systems within the network.

The impact of these intrusions is profound, as the group deploys a suite of custom backdoors to maintain long-term access. Picus Security analysts identified the malware after observing these distinctive behaviors, noting the group’s capability to blend into legitimate network traffic. Tools such as the BumbleBee webshell and PowerShell-based backdoors like TriFive and Snugy allow the attackers to execute arbitrary commands. By leveraging Exchange Web Services for command and control, the attackers communicate via email drafts within the Deleted Items folder, further complicating detection efforts.

A critical aspect of xHunt’s methodology is their reliance on scheduled tasks to ensure the persistence of their PowerShell backdoors. Once a system is compromised, the attackers establish tasks that execute malicious scripts at precise intervals, often every few minutes. These tasks are meticulously crafted to evade detection by mimicking legitimate Windows processes and placing files in trusted directories. For instance, the group uses specific commands to schedule their payloads: "schtasks /create /sc MINUTE /mo 5 /tn \"Microsoft\Windows\SideShow\SystemDataProvider\" /tr \"powershell -exec bypass -file C:\Windows\Temp\xpsrchvw.ps1\" /ru SYSTEM" Additionally, xHunt actors employ masquerading techniques, such as placing tasks in the Windows Diagnostic Infrastructure directory and naming them ResolutionHosts to resemble legitimate system files. These evasion tactics, combined with their use of SSH tunnels for lateral movement, make xHunt a resilient and elusive threat that requires comprehensive behavioral monitoring to detect effectively.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/xhunt-apt-hackers-attacking-microsoft-exchange/) 
