---
title: Threat Researcher's Notebook How Attackers Redirect Crypto Payments
date: 2026-10-30
categories: [CYBERSECURITY]
tags: [MALWARE,CRYPTO,PAYMENTS,SECURITY]
---

## Threat Researcher's Notebook: How Attackers Redirect Crypto Payments

Attackers have developed specialized malware to redirect normal transactions to wallets they control, a tactic known as **"Clipbankers"**. Due to the nature of cryptocurrency, these transactions are irreversible, making them particularly appealing to hackers. 🚨

ReversingLabs has investigated two malware families of this nature, delving into their operations. This blog will refer to this group of malware as **Clipbankers**. More sophisticated variations of this malware can match the replacement address to a similar attack-controlled one, reducing the chance of detection. While Clipbankers are primarily known for replacing intended wallet addresses with those controlled by attackers, they often come with additional malicious features, such as monitoring and exfiltrating clipboard data. 📊

### Why Are Clipbankers Effective?
Three factors contribute to the effectiveness of this type of malware:
1. **Trust in the Clipboard:** Users inherently trust the clipboard, making it easier for attackers to exploit this trust.
2. **Complexity of Crypto Wallet Addresses:** Crypto wallet addresses are long strings of random characters, making them difficult to scan for discrepancies.
3. **Irreversibility of Transactions:** Crypto transactions cannot be reversed, leaving victims with little recourse for misplaced payments. 💔

Recently, ReversingLabs has focused on two malware families: **AnimateClipper** and **Efimer**. AnimateClipper, also known as ZigClipper, is the newer variant, while Efimer is older and notable for its specific methods of matching intended recipient addresses with attacker-controlled ones. Both families became inactive shortly after ReversingLabs completed their research, but they serve as valuable examples of ClipBanker malware. 

Most activity for these families occurred throughout July, with a plateau in August. AnimateClipper showed minimal activity aside from the end of August, while Efimer was slightly more active during that month, experiencing a sudden spike between August 17th and 21st. 📈

To read the complete article see: [Read full article](https://www.reversinglabs.com/blog/threat-researchers-notebook-how-attackers-redirect-crypto-payments)