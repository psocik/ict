---
title: KawaiiGPT – New Black-Hat AI Tool Used by Hackers to Launch Cyberattacks
date: 2025-11-25
categories: [CYBERSECURITY]
tags: [AI,CYBERSECURITY,KAWAIIGPT,BLACK-HAT AI]
---

A new free AI tool named KawaiiGPT is being leveraged by cybercriminals to automate and simplify a range of attacks, including phishing, ransomware deployment, and data exfiltration. The tool, currently at version 2.5, lowers the barrier to entry for novice attackers by providing readily available attack scripts and social engineering capabilities.

KawaiiGPT distinguishes itself from other malicious LLMs like WormGPT 4 through its open-source availability on GitHub and its zero cost. Unlike WormGPT 4 which requires a $50 monthly subscription, KawaiiGPT can be quickly set up on Linux systems in under five minutes. This ease of access, combined with its presence on public repositories, has attracted hundreds of users through Telegram channels. The tool’s CLI is lightweight and deploys easily, enabling even individuals with limited coding skills to generate sophisticated attacks. While interacting with users through playful responses like “Owo! okay! here you go… 😀,” it provides functional Python scripts designed for malicious purposes.

The tool facilitates various stages of an attack, including remote authentication, privilege escalation, backdoor deployment, and data theft. For example, KawaiiGPT can generate convincing spear-phishing emails, such as one mimicking a bank request to “Urgent: Verify Your Account Information,” with links to fake websites designed to harvest credentials. Its code generation capabilities automate network pivots and its use of legitimate libraries allows its outputs to mimic normal network traffic, complicating detection.

KawaiiGPT also creates complete ransomware workflows, including threatening notes claiming files have been encrypted with “military-grade encryption.” These workflows provide instructions to novices for carrying out breaches and extorting victims. Unit 42 has observed KawaiiGPT generating scripts that encrypt PDFs with AES-256, support Tor exfiltration, and guide users through Bitcoin payment steps. Demos also highlight its ability to target Windows EML files, recursively scanning drives to stealthily email attachments.

The emergence of KawaiiGPT demonstrates the dual-use risk of AI, as it shifts threats from skilled actors to a wider audience. Palo Alto Networks’ Unit 42 warns that defenders need to adapt to compressed attack cycles and traditional indicators of compromise, such as poor code quality, may no longer be reliable. They recommend implementing AI-resilient filters, anomaly detection, and prompt monitoring, and also urge ethical AI safeguards and global efforts to disrupt similar malicious services.

To read the complete article see: [KawaiiGPT – New Black-Hat AI Tool Used by Hackers to Launch Cyberattacks](https://cybersecuritynews.com/kawaiigpt-black-hat-ai/)...