---
title: New 'Curly COMrades' APT Using NGEN COM Hijacking in Georgia, Moldova Attacks
date: 2025-08-12
categories: [APT]
tags: [CYBER ESPIONAGE,GEORGIA,MOLDOVA,APT,SECURITY]
---

A previously undocumented threat actor dubbed Curly COMrades has been observed targeting entities in Georgia and Moldova as part of a cyber espionage campaign designed to facilitate long-term access to target networks.

They repeatedly tried to extract the NTDS database from domain controllers, the primary repository for user password hashes and authentication data in a Windows network. Additionally, they attempted to dump LSASS memory from specific systems to recover active user credentials, potentially plain-text passwords, from machines where users were logged on.

The activity has been tracked by the Romanian cybersecurity company since mid-2024, singling out judicial and government bodies in Georgia, as well as an energy distribution company in Moldova. "Regarding the timeline, while we have been tracking the campaign since mid-2024, our analysis of the artifacts indicates that activity began earlier," Martin Zugec, technical solutions director at Bitdefender, told the publication. "The earliest confirmed date we have for the use of the MucorAgent malware is November 2023, though it is highly probable that the group was active before that time."

Curly COMrades are assessed to be operating with goals that are aligned with Russia's geopolitical strategy. It gets its name from the heavy reliance on the curl utility for command-and-control (C2) and data transfer, and the hijacking of the component object model (COM) objects.

The attackers relied heavily on publicly available tools, open-source projects, and LOLBins, showing a preference for stealth, flexibility, and minimal detection rather than exploiting novel vulnerabilities.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/08/new-curly-comrades-apt-using-ngen-com.html) 😊.