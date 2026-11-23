---
title: Major African Stock Exchange Targeted in AI-Assisted Attack
date: 2026-11-20
categories: [CYBERSECURITY]
tags: [AI,CYBERSECURITY,STOCK-EXCHANGE,ATTACK]
---

## Major African Stock Exchange Targeted in AI-Assisted Attack

🚨 **Security Alert!** Symantec's Threat Hunter Team has uncovered a sophisticated toolkit on a stock exchange in Africa, believed to be developed or assisted by an AI model. 

On **September 20, 2026**, 41 PowerShell modules were executed under a web shell for just over three minutes, each hunting for credentials and secrets to test against the exchange's financial systems. This toolkit represents one of the most advanced examples of suspected machine-written attack tooling observed to date. 

### Key Findings:
- Each module shared a common structure, with a unique DNS exfiltration loop copied across all scripts.
- Six persistence implants linked to the China-associated espionage group **Witchetty** were found on the same server, although the AI-authored toolkit has not been attributed to any specific group.
- The toolkit's earliest signs of malicious activity date back to **April 2026**, indicating a potentially longer presence of the attackers.

### Attack Details:
- The toolkit searched for secrets in shared policy folders and application directories, targeting cloud keys and database connection strings.
- It mapped cloud and database infrastructures, enumerated SharePoint, System Center Configuration Manager (SCCM), and Team Foundation Server (TFS) servers, and tested access to the exchange's investment API and securities depository gateway.
- The attack appears financially motivated, with attempts to access the investment API and test API keys against banking software.

### Conclusion:
This incident highlights the evolving landscape of cyber threats, where AI is increasingly being utilized to enhance the sophistication of attacks. The implications for financial institutions are significant, necessitating heightened vigilance and advanced security measures.

For more details, check out the full article: [Read full article](https://www.security.com/threat-intelligence/african-stock-exchange-ai-assisted-attack)