---
title: CyberStrikeAI in the Wild The Use of AI in Real-World Attacks
date: 2026-11-02
categories: [CYBERSECURITY]
tags: [AI,CYBERSECURITY,MALWARE,THREAT-INTELLIGENCE]
---

## CyberStrikeAI in the Wild: The Use of AI in Real-World Attacks

As part of proactive threat monitoring, Kaspersky's Cyber Threat Intelligence team identified a malicious campaign involving C2 agents controlled by artificial intelligence. Confirmed victims of the campaign included organizations in the education sector in several countries across Africa and Latin America. **CyberStrikeAI** played a key role in the post-exploitation phase. This is an open-source framework in which an LLM orchestrator on the command-and-control server plans actions, selects tools, and generates commands, while an implant executes them on compromised hosts. Using CyberStrikeAI, the attackers progressed from reconnaissance to full domain compromise. 🚀

According to our data, this is one of the first public descriptions of a compromise involving an LLM in the wild. The campaign we discovered clearly illustrates how the role of AI in attackers' arsenals is evolving: until recently, language models were used primarily during preparatory stages - for writing phishing emails, debugging code, or searching for vulnerabilities. Now, however, they are being embedded into the very core of the attack, automating actions at every stage: payload execution, persistence on the host, discovery, lateral movement, and, finally, data collection and exfiltration. Post-exploitation - the stage that traditionally required manual work by an experienced operator - plays a particularly significant role here. 🔍

A key feature of the scheme using the CyberStrikeAI framework is that the implant ceases to be a simple tool for executing the operator's commands. Decisions are distributed across two levels: the operator defines the task in general terms, while the model determines how to execute it. 

For more details, check out the full article: [Read full article](https://securelist.com/tr/cyberstrikeai-attacks/121715/) 
