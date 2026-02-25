---
title: Microsoft Store Outlook Add-in Hijacked to Steal 4,000 Accounts
date: 2026-02-11
categories: [SECURITY]
tags: [MICROSOFT,OUTLOOK,PHISHING,SECURITY]
---

## Microsoft Store Outlook Add-in Hijacked 🚨

The **AgreeTo add-in** for Outlook has been hijacked and transformed into a phishing kit that has stolen over **4,000 Microsoft account credentials**. Originally a legitimate meeting scheduling tool, this add-in was developed by an independent publisher and has been available on the Microsoft Office Add-in Store since **December 2022**.

### How It Happened

Office add-ins are essentially URLs that load content into Microsoft products from the developer's server. In this case, the developer used a Vercel-hosted URL but abandoned the project. Despite this, the add-in remained listed on Microsoft's store, allowing a threat actor to claim the orphaned URL and deploy a phishing kit.

When users opened the malicious AgreeTo add-in in Outlook, they were presented with a fake Microsoft login page instead of the expected scheduling interface. Any credentials entered were exfiltrated via a **Telegram bot API** to the attackers, who then redirected victims to the real Microsoft login page to avoid suspicion.

### The Discovery

Researchers from Koi Security discovered the compromise and accessed the attacker's exfiltration channel, revealing that over **4,000 Microsoft account credentials** had been stolen, along with credit card numbers and banking security answers. The add-in was only removed from the store today, but Koi researchers noted that the threat actor was actively testing the stolen credentials during their investigation.

### What You Should Do

If you still have the AgreeTo add-in installed on Outlook, it is highly recommended that you remove it immediately and reset your passwords to protect your accounts. 

For more details, check out the full article here: [Read full article](https://www.bleepingcomputer.com/news/security/microsoft-store-outlook-add-in-hijacked-to-steal-4-000-microsoft-accounts/)