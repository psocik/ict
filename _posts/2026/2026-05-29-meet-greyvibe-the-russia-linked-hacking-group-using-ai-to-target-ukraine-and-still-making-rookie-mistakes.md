---
title: Meet GREYVIBE, the Russia-Linked Hacking Group Using AI to Target Ukraine and Still Making Rookie Mistakes
date: 2026-05-29
categories: [CYBERSECURITY]
tags: [GREYVIBE,HACKING,AI,UKRAINE,CYBERSECURITY]
---

## Meet GREYVIBE: A New Threat to Ukraine

🚨 **Security firm WithSecure** has been tracking a previously unknown Russian-linked APT group called **GREYVIBE** since at least August 2025. This group targets Ukraine and Ukrainian-related organizations across military, government, civilian, and business sectors. While the group is not particularly sophisticated, it is persistent and uses AI to compensate for skill gaps. However, researchers note that GREYVIBE keeps making mistakes that provide insights into their operations.

### AI in Action

WithSecure found evidence of AI assistance across multiple parts of the operation:
- **Image generation** via Ideogram AI
- **Code development** with ChatGPT and Google Gemini
- **Obfuscation scripts**
- **Backend infrastructure**
- **Post-compromise command generation**

The use of AI is not incidental; it is structural to their operations.

### Attack Vectors

The group has leveraged multiple attack vectors, including:
- **Spear-phishing emails**
- **Fake CAPTCHA pages**
- **Fraudulent Ukrainian adult club websites**

These methods deliver malware to a diverse set of victims, including military, government, civilian, and business-related entities. The researchers documented five distinct attack chains employed by the group, each with its own lure and payload:
1. **PhantomMail**: Spear-phishing emails with links to malicious archives on Google Drive and 4sync, delivering JavaScript-based loaders and a PowerShell remote access trojan called **PhantomRelay**.
2. **PhantomClick**: Fake CAPTCHA pages impersonating Zoom and LAPAS, tricking victims into running commands that install the same PhantomRelay implant.
3. **PrincessClub**: Fake Ukrainian adult-club websites that deliver Android spyware called **FallSpy**, or Windows-based RATs depending on the victim's device.
4. **DroneLink**: Websites posing as charitable foundations supporting the Ukrainian military to deliver WireGuard VPN software alongside a lightweight RAT called **LegionRelay**.
5. **Nebo**: A campaign using a FallSpy sample designed to mimic a Russian military login screen.

### Operational Insights

The group's operations align with Russian state interests but do not consistently exhibit the operational maturity associated with more seasoned adversaries. Indicators suggest ties to the broader cybercrime ecosystem. Interestingly, the AI assistance has backfired at times, leading to design flaws that exposed backend functionality to researchers. 

Development artifacts included internet slang like "letsrollboyos," "totallyunsus," and "cuteuwu." One campaign even deployed an XMRig cryptocurrency miner on a small number of infected machines, which is atypical for a disciplined intelligence operation.

### Conclusion

WithSecure found connections between GREYVIBE's tooling and both the **TrickBot gang** and **UAC-0098**, a group previously linked to Russian cybercriminal networks. PhantomRelay variants appeared in a Microsoft Teams voice-phishing campaign and a separate ClickFix delivery chain between February and March 2026, seemingly unrelated to the Ukrainian targeting. 

Taken together, researchers assess with moderate confidence that the group has ties to the broader cybercrime ecosystem, and with low-to-moderate confidence that it involves current or former cybercriminal members.

[Read full article](https://securityaffairs.com/192877/apt/meet-greyvibe-the-russian-linked-hacking-group-using-ai-to-target-ukraine-and-still-making-rookie-mistakes.html)