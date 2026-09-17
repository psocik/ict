---
title: Advisory on Iranian Cyber Targeting of Dissidents, Activists, and Journalists
date: 2026-09-16
categories: [CYBERSECURITY]
tags: [IRAN,CYBERSECURITY,MALWARE,DISSIDENTS,ACTIVISTS]
---

## Advisory on Iranian Cyber Targeting of Dissidents, Activists, and Journalists

**Date Published:** September 16, 2026

The **CHOSEN BRICK** malware family has been utilized to target individuals globally, including in the UK, US, and the Netherlands, since at least 2025. This malware allows Iranian state cyber actors to gather information on a target's contacts, emails, and social media messages, potentially enabling the tracking of their movements. Iran likely employs cyber activities to suppress individuals perceived as threats to the regime, such as dissidents, activists, and journalists. The personal details of some previous victims of CHOSEN BRICK have surfaced on pro-Iranian leak sites, heightening the risk to the personal safety of those affected. This advisory from the UK National Cyber Security Centre, the US Federal Bureau of Investigation, and the Netherlands' General Intelligence and Security Service shares technical information about the malware and its tactics, techniques, and procedures (TTPs).

### Key Insights:
- Iranian cyber actors customize their approach based on their intended targets, leading to significant variations in initial contact and operational goals.
- The attack chain typically begins with social engineering via messaging platforms like WhatsApp and Telegram, where attackers pose as trusted entities.
- The malware is often disguised as legitimate applications or files, tricking targets into downloading and executing it.

### Malware Persistence:
CHOSEN BRICK is designed to persist through device reboots, utilizing registry keys and often adding exclusions to Microsoft Defender antivirus. Once installed, it connects to Telegram for Command and Control, with each victim device linking to a unique Telegram Bot ID for operational security. The malware possesses a wide array of commands and can execute various functions through native Windows tools.

### Data Theft Capabilities:
The malware can capture screen content, gather data from Telegram and WhatsApp, and exfiltrate files through Telegram bots and cloud storage solutions. Screen capture is a frequently observed feature, allowing attackers to identify victims' contacts, locations, and daily patterns.

For more detailed information, you can read the complete article here: [Read full article](https://www.ncsc.gov.uk/sites/default/files/2026-09/Advisory-Iranian-Cyber-Targeting-of-Dissidents-Activists-and-journalists.pdf) 

🚀 Stay informed and vigilant!