---
title: Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks
date: 2026-07-30
categories: [CYBERSECURITY]
tags: [AI,CYBERATTACKS,THREAT-ACTOR,VULNERABILITIES]
---

## Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks

🚨 **Overview**: Unit 42 has uncovered a sophisticated AI-enabled autonomous hacking campaign orchestrated by a Chinese-speaking threat actor. This actor has targeted critical infrastructure by exploiting seven vulnerabilities, blending autonomous AI-driven enumeration with manual exploitation, resulting in confirmed impacts.

### Key Findings:
- The threat actor operates under the aliases **knaithe** and **KnYuan**.
- They utilize **DeepSeek** through the **Hermes Agent framework** as their autonomous offensive operator.
- Communication and orchestration are conducted via **Telegram**, allowing for independent target enumeration and attack initiation without human intervention.

### Tools and Techniques:
- The actor has configured multiple large language models (LLMs) including **Qwen**, **GLM**, **Kimi**, and **MiniMax** for their operations.
- Limited testing of Western platforms such as **Claude Code** and **Codex** was also observed.

### Notable Incidents:
- A significant exposure occurred when the autonomous agent inadvertently revealed its infrastructure by starting a file server in its home directory, providing unique insights into its operational environment.
- The actor primarily relied on the **Hermes Agent** with **DeepSeek** for the attack phase, utilizing various skills for red-teaming.

### Vulnerability Exploitation:
- The campaign included attempts to exploit a **Langflow vulnerability (CVE-2026-33017)**, which ultimately failed despite identifying vulnerable targets.
- The actor shifted focus to **n8n**, confirming multiple instances running vulnerable versions but did not achieve successful exploitation.

### Manual Operations:
- In addition to autonomous campaigns, the actor conducted manual operations with confirmed impacts, including data exfiltration and command execution across various organizations.

For more detailed insights, check out the full article: [Read full article](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)