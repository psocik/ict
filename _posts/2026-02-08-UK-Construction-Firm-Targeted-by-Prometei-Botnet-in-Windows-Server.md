---
title: UK Construction Firm Targeted by Prometei Botnet in Windows Server
date: 2026-02-08
categories: [CYBERSECURITY]
tags: [MALWARE,BOTNET,CYBERSECURITY,WINDOWS,CONSTRUCTION]
---

## UK Construction Firm Hit by Prometei Botnet 🚧

In January 2026, a UK construction firm discovered a digital "tenant from hell" hiding on its Windows Server. Security experts from the eSentire Threat Response Unit (TRU) identified the intruder as **Prometei**, a Russian-linked botnet active since 2016. While its main job is mining **Monero** cryptocurrency, TRU’s research revealed that it also excels at stealing passwords and taking remote control of systems.

The research, which was shared with Hackread.com, suggests the attackers didn’t need to be geniuses to get in. They likely just guessed easy or default passwords to gain access via the **Remote Desktop Protocol (RDP)**.

Prometei isn’t just one file; it’s a whole toolkit. Once inside, it installs a service called **UPlugPlay** and creates a file named **sqhost.exe** to ensure it stays active every time the computer starts. Researchers noted that the malware’s first move is to download its main payload, **zsvc.exe**, from a server linked to Primesoftex Ltd. The file arrives heavily encrypted and disguised.

To keep its operators updated, Prometei gathers your computer’s name and technical details using built-in Windows tools. Further probing revealed it also uses a tool called **Mimikatz** (labelled as **miWalk**) to steal every password on the network, while routing its traffic through the anonymous **TOR network** to stay off the radar.

What makes Prometei particularly crafty is how it avoids detection. It looks for a specific file, **mshlpda32.dll**, to unpack its code. If the malware can’t find this file, it doesn’t just crash; it performs decoy actions like running fake system tasks to look harmless. According to researchers, this is a “sandbox bypass” trick designed to fool security experts who are trying to study it in a safe environment.

Prometei also acts as a jealous “tenant,” a term researchers used because the malware effectively squats on the server and “changes the locks” to keep others out. It downloads a tool called **netdefender.exe**, which actually blocks other hackers from getting in. Then it monitors for failed login attempts and prevents them from entering.

To read the complete article see:
[Read full article](https://hackread.com/uk-construction-firm-prometei-botnet-windows-server/)