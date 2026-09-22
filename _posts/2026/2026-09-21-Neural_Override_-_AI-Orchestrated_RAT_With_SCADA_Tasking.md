---
title: Neural Override - AI-Orchestrated RAT With SCADA Tasking
date: 2026-09-21
categories: [CYBERSECURITY]
tags: [MALWARE,AI,SCADA,RAT,CYBERSECURITY]
---

## Neural Override - AI-Orchestrated RAT With SCADA Tasking 🚀

We identified and analyzed **Neural Override**, a five-build Python RAT family controlled via Telegram and featuring an autonomous, LLM-driven attack-planning loop. The malware uses OpenRouter AI to analyze compromised systems and autonomously select attack actions, including ransomware, DDoS, credential theft, persistence, and SCADA tasking. All user-facing strings are in Ukrainian.

As of **2026-08-27**, both the Telegram bot (@Skibidi_16_bot) and the OpenRouter API key were active. The Python payload contained a Telegram bot token and a Telegram user ID, allowing the identification of a bot named @Skibidi_16_bot (display name "Pomoshnik", Russian for "Helper"), using a webhook pointing to a consumer bot-building service. The payload also contained a valid OpenRouter API key providing access to 417 models on the free tier.

### Build Analysis 🔍
Five builds were identified by analyzing the Telegram bot token. The OpenRouter key is absent from Build 1 and present from Build 2 onward, dating the addition of the LLM component to **2026-08-03**. 
- **Build 1** (2026-07-08, 58KB .pyc) is a basic bot with eight capabilities and no AI integration.
- **Build 2** (2026-08-03, 56KB .pyc, neural_override_v3.py) introduces OpenRouter AI, the autopilot loop, and 11 additional capabilities, totaling 19.
- **Builds 3 and 4** (2026-08-04) add 42 new functions within approximately 24 hours, increasing from version 3 to version 9 and expanding from 19 to 61 capabilities. The rapid version increase from v3 to v9 within 24 hours, with no intermediate versions, along with the way the code is written, strongly suggests AI-assisted code generation.
- **Build 5** (2026-08-08, 54KB .pyc, neural_override_v3.py) is a deliberate rollback to the version 3 capability set.

### SCADA Component ⚙️
The SCADA component comprises:
- `scada_attack()` (which executes "python scada_commander.py --command shutdown")
- `grid_attack()` (nmap Modbus scanning across 192.168.1[.]0/24)
- Infrastructure port scans targeting ports 502 and 20000.

These tasks appear in the autonomous autopilot's action list, but inline OT/ICS protocol libraries and code (such as pymodbus or snap7) are absent, and we were unable to find scada_commander.py. The SCADA tasking is present only in builds 3 and 4; the version 3 rollback removes all SCADA references.

### Recommendations 📈
Organizations should monitor for outbound connections to api[.]telegram[.]org and openrouter[.]ai from workstations, engineering stations, or servers, particularly where both appear from the same host or from a Python process. Neither service has a legitimate role on most operational technology networks, and the pairing of a messaging API used for command and control with a large language model API used for attack planning is a strong behavioral indicator.

On hosts, the SystemHelper persistence artifacts provide direct detection opportunities, as does any process invoking scada_commander.py. The report includes SHA256 Hashes for the five Neural Override family builds, chronologically. Key network indicators include the Telegram Bot: @Skibidi_16_bot, the LLM Endpoint: openrouter[.]ai/api/v1/chat/completions, and the Modbus Port Scan Target: 192.168.1[.]0/24.

For more details, check out the full article: [Read full article](https://github.com/PaloAltoNetworks/Unit42-timely-threat-intel/blob/main/2026-09-15-Neural-Override-AI-Orchestrated-RAT.txt)