---
title: Hackers Leverage AI-Generated Code to Obfuscate Its Payload and Evade Traditional Defenses
date: 2025-09-26
categories: [CYBER SECURITY]
tags: [AI,MALWARE,PHISHING,CYBERSECURITY]
---

Cybercriminals are increasingly turning to artificial intelligence to enhance their attack capabilities, as demonstrated in a sophisticated phishing campaign recently uncovered by security researchers. The campaign represents a significant evolution in malware obfuscation techniques, utilizing AI-generated code to disguise malicious payloads within seemingly legitimate business documents.

The analysis revealed that the malicious code displayed levels of complexity, verbosity, and structural patterns that strongly indicated AI assistance in its creation. Microsoft Security Copilot’s assessment concluded that the code was “not something a human would typically write from scratch due to its complexity, verbosity, and lack of practical utility.”

Central to the campaign’s success was its use of SVG (Scalable Vector Graphics) files as the primary attack vehicle. The malicious file, named “23mb – PDF- 6 pages.svg,” was designed to appear as a legitimate PDF document despite its SVG extension. This choice proved strategic, as SVG files are text-based and scriptable, allowing attackers to embed JavaScript and other dynamic content directly within the file structure while maintaining the appearance of benign graphics files.

The payload’s core functionality was hidden within a sophisticated encoding scheme that utilized an extensive sequence of business-related terms. Words such as “revenue,” “operations,” “risk,” and “shares” were concatenated into a hidden data-analytics attribute of an invisible text element within the SVG structure. This creative approach transformed what appeared to be harmless business metadata into functional malicious code.

To read the complete article see:
[Hackers Leverage AI-Generated Code](https://cybersecuritynews.com/hackers-leverage-ai-generated-code/).