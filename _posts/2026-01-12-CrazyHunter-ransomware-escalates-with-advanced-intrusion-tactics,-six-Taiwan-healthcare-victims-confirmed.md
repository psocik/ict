---
title: CrazyHunter ransomware escalates with advanced intrusion tactics, six Taiwan healthcare victims confirmed
date: 2026-01-12
categories: [MALWARE]
tags: [RANSOMWARE,CYBERSECURITY,HEALTHCARE,TAIWAN]
---

New research from Trellix detailed that CrazyHunter ransomware has emerged as a serious and escalating threat, underscoring the growing sophistication of modern cybercriminal operations. Trellix has tracked the malware since its first appearance, observing rapid technical evolution and increasing activity. To date, the primary targets have been healthcare organizations in Taiwan, with six confirmed victims. Technically, CrazyHunter is a fork of the Prince ransomware that surfaced in mid-2024, but it incorporates meaningful enhancements, particularly in network intrusion methods and anti-malware evasion capabilities.

A typical CrazyHunter ransomware attack unfolds in a series of distinct stages. The initial compromise often begins with the exploitation of weaknesses in an organization’s Active Directory infrastructure, most commonly through weak passwords associated with domain accounts. Once access is established, attackers move laterally and propagate rapidly across the environment. In observed CrazyHunter incidents, this phase frequently involves the use of SharpGPOAbuse to deploy the ransomware payload via Group Policy Objects, enabling fast distribution to multiple systems while relying on compromised Active Directory credentials to sustain the spread.

After gaining broad access, the attackers focus on privilege escalation to disable defenses and consolidate control. CrazyHunter is notable for its use of a ‘bring-your-own-vulnerable-driver’ technique, in which a modified Zemana anti-malware driver, zam64[dot]sys, is weaponized to elevate privileges and bypass security mechanisms that would normally block such activity. The attack concludes with widespread encryption of files across the network, rendering critical data inaccessible, followed by a ransom demand that seeks payment in exchange for decryption keys.

“For the primary task of encrypting file content, CrazyHunter utilizes the ChaCha20 stream cipher,” according to Aswath. “A distinctive feature of this ransomware is its partial encryption. Instead of encrypting the entire file, it encrypts one byte of data and then skips the next two, leaving them in their original, unencrypted state. This 1:2 encryption ratio is a deliberate design choice from the underlying Prince builder.”

To read the complete article see: [Industrial Cyber](https://industrialcyber.co/ransomware/crazyhunter-ransomware-escalates-with-advanced-intrusion-tactics-six-taiwan-healthcare-victims-confirmed/).