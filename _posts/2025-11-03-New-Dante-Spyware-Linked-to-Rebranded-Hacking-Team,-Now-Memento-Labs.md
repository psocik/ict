---
title: New Dante Spyware Linked to Rebranded Hacking Team, Now Memento Labs
date: 2025-11-03
categories: [APT]
tags: [SPYWARE,HACKING,CYBERSECURITY,MEMENTO LABS]
---

Kaspersky researchers uncovered Operation ForumTroll, an attack campaign utilizing the new ‘Dante’ spyware developed by Memento Labs, the rebranded Hacking Team. The attacks utilized a Chrome zero-day vulnerability (CVE-2025-2783) and COM hijacking for persistence, confirming the continued deployment of advanced surveillance tools by the controversial Italian firm.  

The infection started when a recipient clicked a personalized link. The malicious site ran a quick check, called a Validator, to confirm the victim was a real user before executing the attack. The main trick involved exploiting a zero-day vulnerability in Google Chrome. This specific flaw, tracked as CVE-2025-2783, was particularly clever: it took advantage of a decades-old error in Windows to trick Chrome’s security process. By doing this, the attackers managed to bypass all of Chrome’s protective barriers (sandbox escape) and gain full control of the system. Kaspersky reported the issue, leading Google to swiftly release a patch. The extensive list of previous zero-day attacks shared by Kaspersky shows this is a continuous, difficult effort to catch such malicious attacks.  

Once compromised, attackers installed a secret component to ensure persistent access. They achieved this using a technique called Component Object Model (COM) hijacking, which involves manipulating the Windows registry. By placing a custom entry in the user’s private settings, the attackers forced legitimate Windows programs to load their malicious code, which then launched the actual spyware LeetAgent, a tool designed to steal files (like documents and spreadsheets), run system commands, and record keystrokes.  

Kaspersky’s researchers then found a direct operational and code link between the LeetAgent attacks and a more powerful tool they identified as Dante. This connection confirms a key development in the commercial spyware market. Dante is the new surveillance platform from Memento Labs, the company created after the infamous Hacking Team was acquired and rebranded in 2019.  

[Read the complete article here](https://hackread.com/dante-spyware-hacking-team-memento-labs/).