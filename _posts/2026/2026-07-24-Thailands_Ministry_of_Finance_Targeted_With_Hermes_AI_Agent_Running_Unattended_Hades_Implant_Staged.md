---
title: Thailand's Ministry of Finance Targeted With Hermes AI Agent Running Unattended, Hades Implant Staged
date: 2026-07-24
categories: [CYBERSECURITY]
tags: [THAILAND,CYBER-ESPIONAGE,AI,HADES,HERMES]
---

## Thailand's Ministry of Finance Targeted with Hermes AI 🚨

Hunt.io has uncovered a **cyber-espionage attack** on Thailand's Finance Ministry using the **Hermes AI agent** and **Hades malware** for reconnaissance and persistence. This investigation provides a rare glimpse into a live cyber-espionage operation. Instead of recovering malware post-attack, the team discovered exposed staging servers containing attack tools, stolen credentials, active session material, AI agent logs, and a previously undocumented implant known as **Hades**.

The investigation, conducted by Hunt.io and security researcher **Bob Diachenko**, traced the activity to three publicly accessible directories exposed between **July 9 and July 13** on a Hong Kong-hosted server. These directories contained nearly **600 files**, including exploit code, web shells, custom scripts, compiled implants, and credentials targeting Thailand's Ministry of Finance (MOF).

### Key Findings 🔍
- The operator had already established access to multiple internal systems, although the initial intrusion vector remains unknown.
- The use of **Hermes**, an open-source autonomous AI agent, allowed the operator to execute commands without waiting for approval. The attack was largely driven by Hermes, functioning in **YOLO mode**.
- Logs recovered from the exposed directories show the framework running in YOLO mode, executing potentially dangerous commands automatically.

### Operational Insights 💡
The investigation reveals that the operator invested considerable effort in understanding the ministry's internal environment. Custom scripts specifically targeted **Apache Hadoop** infrastructure, exploiting default authentication behavior and malicious Hive user-defined functions to execute operating system commands. The directories contained exploit code for well-known vulnerabilities, including **PwnKit (CVE-2021-4034)** and the **sudo heap overflow (CVE-2021-3156)**.

### Conclusion 🏁
The Hermes logs provide clear evidence of how AI is reshaping offensive operations. The operator delegated routine reconnaissance tasks to the agent, which executed various checks and cataloged files belonging to the Office of the Permanent Secretary for Finance. While no evidence of document exfiltration was found, the logs indicate that attackers were systematically expanding their visibility inside the environment.

For more details, you can read the full article here: [Read full article](https://securityaffairs.com/195941/hacking/thailands-ministry-of-finance-targeted-with-hermes-ai-agent-running-unattended-hades-implant-staged.html)