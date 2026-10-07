---
title: Blinder Tunnel Targets Critical Infrastructure
date: 2026-10-06
categories: [CYBERSECURITY]
tags: [IRAN,MALWARE,CYBERATTACK,INFRASTRUCTURE]
---

## Blinder Tunnel Targets Critical Infrastructure

An Iranian state-aligned threat actor has been masquerading as the Dubai Airports IT department to deliver trojanized coding challenges to high-value targets. Unit 42 tracks this activity as CL-STA-1178. A campaign, dubbed "Blinder Tunnel," targeted Iraqi critical infrastructure in March 2026, following infrastructure staging observed as early as November 2025. We assess with high confidence that this activity aligns with an Iranian-nexus threat. The attackers behind this cluster target high-value infrastructure, including telecommunications, aviation, and other critical entities across Iraq, Israel, and the United Arab Emirates (UAE). This campaign incorporates a "Peaky Blinders" theme by naming infrastructure components after the British crime drama's branding -- even embedding its theme song into the malware. 🚀

### Attack Methodology

Attackers established an initial foothold using a three-step chain:
- Exploited legitimate Windows developer .csproj files
- Performed AppDomainManager hijacking
- Executed binaries through DLL sideloading

These steps deployed custom malware, ShelbyLoader V2. For C2 communication, the campaign misused GitHub's API infrastructure for living off the cloud, leveraging repositories to fetch decryption keys, download payloads, and use GitHub issues as a resilient C2 fallback. The GitHub repository also hosted an in-memory wrapper executing the open-source Chisel tunneling utility. GitHub has taken down the malicious infrastructure. OpSec missteps by the attackers, including exposing tools on public repositories and embedding metadata within the show's theme song, linked Blinder Tunnel infrastructure to a separate campaign against an Israeli entity in May-June 2026.

### Social Engineering Campaign

Starting in late March 2026, the threat actor launched a social engineering campaign disguised as a professional recruitment process to compromise a specific individual, likely a software engineer. Impersonating the Dubai Airports IT department, attackers approached a target with a job offer. The first stage involved downloading a file named Dubai Airport Careers, an Inno Setup installer masquerading as a career portal. This decoy built credibility, as submitting the questionnaire did not trigger malicious execution. In April 2026, the threat actor sent a weaponized Microsoft Visual Studio project archive, DubaiAirport_Carrers_IT_Test.zip, disguised as a coding assessment. This project contained personalized instructions from a claimed senior manager, instructing the recipient to open the C# Flight Management System project. Attackers instructed the target to build and run the project to find and fix an intentional bug, under the pretense of evaluating technical abilities. 🚀

### Initial Infection

The initial infection is triggered by a malicious .csproj file. Attackers weaponized the C# project's .csproj configuration file by misusing Visual Studio's built-in evaluation process. This caused the payload to execute the moment the project was loaded into the IDE, even before compilation. Visual Studio performs a design-time build, running GetFrameworkPaths. Attackers defined a custom XML target with this name in their malicious .csproj file, overriding Microsoft default behavior. When the target opened the project, Visual Studio executed the attacker's custom instructions without user intervention. The script created a deceptive folder in %LOCALAPPDATA%\Microsoft\RuntimeBrokers, copied hidden malware binaries, and launched RuntimeBroker.exe.

[Read full article](https://unit42.paloaltonetworks.com/blinder-tunnel-targets-critical-infrastructure/) 