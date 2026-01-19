---
title: RPi-Jukebox-RFID 2.8.0 - Remote Command Execution
date: 2026-01-17
categories: [SECURITY]
tags: [CVE-2025-10327,RPI-JUKEBOX-RFID,REMOTE COMMAND EXECUTION]
---

A remote code execution vulnerability, identified as CVE-2025-10327, has been discovered in RPi-Jukebox-RFID version 2.8.0. The exploit, authored by Beatriz Fresno Naumova, was dated 2025-09-25.  This vulnerability impacts RPi-Jukebox-RFID v2.8.0, tested on Raspberry Pi OS with this version.

The Proof-of-Concept (PoC) demonstrates an OS command injection vulnerability in the `shuffle.php` API endpoint. The vulnerable parameter "playlist" is passed directly to a shell command without sanitization, allowing an attacker to execute arbitrary system commands.

The PoC outlines the attack methodology targeting an endpoint designated as `https:YOUR-TARGET-IP/phoniebox/api/playlist/shuffle.php`. The exploitation process involves sending a malicious JSON payload to trigger command injection. The payload for Proof of Execution is `test';touch rced_by_xu17.txt;echo '`. The complete JSON payload sent is `{"playlist": INJECTED_COMMAND, "shuffle": "true"}`.

Upon execution, the PoC prints "[+] Sending malicious JSON payload to trigger command injection..." and then "[+] HTTP Status Code: [response.status_code]". If the target is vulnerable, the command should be executed on the server, creating a file named `rced_by_xu17.txt` as an indicator of successful remote code execution.

To read the complete article, see: [Exploit Database](https://www.exploit-db.com/exploits/52468).