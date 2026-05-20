---
title: Pwn2Own Berlin 2026 Closes With $1.3 Million in Zero-Day Payouts
date: 2026-05-19
categories: [CYBERSECURITY]
tags: [PWN2OWN,ZERO-DAY,CYBERSECURITY,HACKING,VULNERABILITIES]
---

## Pwn2Own Berlin 2026 Closes With $1.3 Million in Zero-Day Payouts 🚀

The highly anticipated **Pwn2Own Berlin 2026** hacking competition concluded on **16 May 2026**, following three days of intense activity at the **OffensiveCon** conference. The event saw massive financial payouts, with researchers receiving around **$1,298,250** in total for live demos of **47 unique zero-day vulnerabilities**.

A Taiwanese research group, **DEVCORE**, was awarded the **Master of Pwn** title, receiving **50.5 points** and **$505,000** in cash rewards, while **STARLabs SG** secured second place with **25 points** ($242,500), followed by **Out Of Bounds** in third with **12.75 points** ($95,750).

The competition's largest payout went to the DEVCORE Research Team's **Cheng-Da Tsai**, aka **Orange Tsai**, who received **$200,000** for chaining three different vulnerabilities to achieve **remote code execution (RCE)** with **SYSTEM privileges** on Microsoft Exchange. On the event's opening day, Tsai had earned **$175,000** for a Microsoft Edge sandbox escape that chained four logic bugs.

At Pwn2Own Berlin, researchers targeted fully patched products from diverse categories, including local privilege escalation (LPE), virtualization, and **Large Language Model (LLM)** coding assistants. On the final day, **Nguyen Hoang Thach** of STARLabs SG successfully used a memory corruption vulnerability to exploit **VMware ESXi** with the **Cross-tenant Code Execution** add-on, earning **$200,000**. Additionally, **splitline** from DEVCORE chained two bugs to compromise **Microsoft SharePoint**, netting **$100,000**.

Operating systems were repeatedly targeted throughout the event. **Le Tran Hai Tung**, **dungnm**, and **hieuvd** of Viettel Cyber Security used an integer overflow to achieve local privilege escalation (LCE) on **Windows 11**. Another repeatedly breached platform was **Red Hat Enterprise Linux for Workstations**. Reportedly, researcher **Hyunwoo Kim** chained a use-after-free bug and an uninitialized memory vulnerability to gain privilege escalation. **Valentina Palmiotti** of IBM X-Force Offensive Research achieved root access on the platform and also exposed a **0-day** in the **NVIDIA Container Toolkit**.

The newly introduced artificial intelligence categories also faced successful exploitation. **Satoki Tsuji** of Ikotas Labs, Inc., abused an external control vulnerability within **OpenAI Codex** to execute arbitrary code on the host system. **Anthropic Claude Code AI assistant** was also targeted multiple times. Researchers from **Compass Security** and **Byung Young Yi** of Out of Bounds successfully demonstrated exploits against it, but both attempts resulted in bug collisions because the underlying vulnerabilities had already been previously disclosed to the **ZDI vendor database**.

This year, the event faced a controversy over an unlikely logistical challenge, as for the first time in its **19-year history**, the contest ran out of slots. As reported by Hackread.com earlier this month, the **Zero Day Initiative (ZDI)**, the **Trend Micro** organization that operates the event, had to close registrations on **7 May** due to the registration logjam, which led to revenge disclosures from the rejected candidates.

To read the complete article see:
[Read full article](https://hackread.com/pwn2own-berlin-2026-closes-zero-day-payouts/)