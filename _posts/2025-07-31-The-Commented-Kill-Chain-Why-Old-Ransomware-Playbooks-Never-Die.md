---
title: The Commented Kill Chain Why Old Ransomware Playbooks Never Die
date: 2025-07-31
categories: [RESEARCH]
tags: [RANSOMWARE,CYBERSECURITY,HUNTRESS]
---

During a ransomware intrusion, we encountered a script that was filled with clear comments for what each command and function did. It was immediately, jarringly out of place, as at Huntress we typically observe malicious scripts to be heavily obfuscated. Clear, descriptive, English comments like `rem Disable WD Tasks` and `rem Remove WD context menu` preceded the corresponding blocks of code - it was like stumbling upon a criminal's detailed confession. This self-documenting script was the thread that unraveled the entire story. The comments made the attacker's intent crystal clear, and allowed us to identify the script's public origin—a Gist on GitHub—and its documented use in past attacks, most notably in a 2021 Xinglocker ransomware case.  

In our case, this ransomware actor moved swiftly. But the Huntress SOC was faster, monitoring the adversary the entire time whilst they were in the network:   

- The threat actor came in via RDP  
- They immediately began tampering with defenses and removing volume shadow copies (which benefits ransomware by eradicating local ‘copies’ of files). Then they moved laterally to the domain controller.  
- The attacker’s intended finale was to detonate `C:\Temp\file.exe -n=15 -p=F` —an executable with common ransomware binary arguments.  

To read the complete article see: [https://www.huntress.com/blog/why-old-ransomware-playbooks-never-die](https://www.huntress.com/blog/why-old-ransomware-playbooks-never-die) 