---
title: Trapping a Mustang Panda
date: 2026-08-20
categories: [CYBERSECURITY]
tags: [CYBER ESPIONAGE,ITG27,HAVENCODE,MALWARE]
---

## Trapping a Mustang Panda

**Source:** IBM X-Force  
**Date Published:** August 20, 2026  

As of mid-2026, IBM X-Force continues to monitor cyber campaigns conducted by ITG27, a China-aligned state-sponsored espionage group whose victims align with China's regional strategic interests. In collaboration with Deception.Pro, X-Force captured live ITG27 activity in simulated enterprise environments, including the deployment of a previously undiscovered VNC-capable backdoor named **Havencode**. 🚀  

The observed activity extends a campaign previously reported by Acronis, where ITG27 targeted India's energy sector and government organizations. This campaign relied on the use of **Claimloader** malware, lure documents, and the **Toneshell** backdoor. X-Force analysts captured live ITG27 operator activity in fake enterprise environments designed to resemble an operational technology company specializing in electric grids and a state-level government agency. Across both incidents, operators conducted reconnaissance, harvested credentials, and deployed malware.  

In the first incident, ITG27 deployed a previously undiscovered VNC-capable backdoor that X-Force named **Havencode**. In the second, operators collected fake documents from infected systems and exfiltrated them to an attacker-controlled SFTP server.  

X-Force is tracking ongoing campaigns attributed to ITG27 (formerly Hive0154), a China-aligned actor conducting cyber espionage. The actors are likely exploiting ongoing geopolitical events in South Asia, using emails to spread new versions of the **Toneshell** backdoor. Using Deception.Pro, X-Force observed two real ITG27 incidents in realistic, simulated victim organizations' environments. ITG27 operators maintained access over multiple days and performed hands-on-keyboard activity including reconnaissance, credential harvesting, and malware deployment.  

The actors deployed a previously unknown VNC-capable backdoor tracked as **Havencode** to manually browse the victim's desktop and exfiltrated fake documents placed in the deception environments. X-Force analysis shows that operator-initiated actions took place exclusively during weekday working hours (08:00-18:00) in China Standard Time.  

ITG27, formerly Hive0154, is a state-sponsored espionage group aligned to the strategic interests of China. Since at least 2024, ITG27 has engaged in cyberattacks targeting public and private organizations, including think tanks, policy groups, government agencies, and individuals. X-Force assesses ITG27 conducts cyber operations primarily in alignment with China's regional interests but may extend its targeting of Western entities perceived to threaten China's economic or military objectives.  

ITG27 activity overlaps with threat actors publicly reported as **Mustang Panda**, **Stately Taurus**, **UNK_SteadySplit**, **Camaro Dragon**, **Twill Typhoon**, **Polaris**, and **Earth Preta**. ITG27 employs a large malware arsenal to conduct espionage. Their arsenal includes actively developed custom malware loaders, backdoors, USB worms, and extending legitimate commercial infrastructure within their campaigns. Associated malware families such as **Toneshell**, **Pubload**, and **Claimloader** undergo frequent updates that enhance ITG27's adaptability within their target environments.  

In May 2026, X-Force uncovered an email with the subject 'China BG' delivered to recipients within the Indian government. The email includes a PDF attachment titled, "Hydropower Cooperation Project Study.pdf" imitating Nepal's Ministry of Foreign Affairs (MoFA). The lure highlights two key offices, the Office of the Minister of External Affairs and the Office of the Minister of Power (sic) within India's Government. The lure's hydropower theme aligns with India's longstanding concerns about transboundary river and dam projects.

[Read full article](https://www.ibm.com/think/x-force/trapping-a-mustang-panda)