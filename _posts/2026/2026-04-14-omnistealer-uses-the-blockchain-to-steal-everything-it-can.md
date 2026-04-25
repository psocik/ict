---
title: Omnistealer Uses the Blockchain to Steal Everything It Can
date: 2026-04-14
categories: [CYBERSECURITY]
tags: [MALWARE,BLOCKCHAIN,CYBERSECURITY,INFOSTEALER]
---

## Omnistealer: A New Threat in Cybersecurity 🚨

A new infostealer dubbed **Omnistealer** is turning the blockchain into a permanent malware hosting platform, which is bad news for both companies and everyday users. While it's common for malware to store its payload on public platforms that can be taken down, Omnistealer gets around this by storing its staging code inside transactions on public blockchains like **TRON**, **Aptos**, and **Binance Smart Chain**. Some blockchain transactions allow small bits of arbitrary data, and instead of something harmless, attackers insert encrypted text, encoded commands, and pieces of malware code. Because blockchains are append-only, those malicious snippets are effectively undeletable once they're mined into a block. This turns public ledgers into a resilient, censorship-resistant command and control infrastructure that defenders can't simply take down.

Despite the obvious connection to cryptocurrency, Omnistealer is not solely about robbing crypto-investors. Once Omnistealer lands on a system, it goes after more than **10 password managers**, including cloud-synced consumer tools such as **LastPass**. It also targets major browsers like **Chrome** and **Firefox**, scraping saved logins and session data, and cloud storage accounts, including **Google Drive** credentials. Furthermore, over **60 browser-based crypto wallets**, including popular extensions like **MetaMask** and **Coinbase Wallet**, are targeted. It's designed to be a one-stop data vacuum that investigators say will "literally steal everything."

The attack typically starts with a "simple" coding gig: a contractor gets a **LinkedIn** or **Upwork** offer, pulls a **GitHub** repository, and runs what looks like normal project code. Behind the scenes, that code reaches out to the blockchain, reads transaction data, and uses it as a pointer to fetch and decrypt the final payload. Researchers estimate that roughly **300,000 credentials** have already been compromised, spanning everything from adult-industry platforms and food delivery to financial compliance firms, defense suppliers, and US government entities.

While you can't delete malware from the blockchain, you can make it much harder for campaigns like this to affect you. Recommendations include:
- Treating "dream job" and unsolicited contract offers as suspicious by default, especially if they move quickly to off-platform chats (Telegram, Discord) or ask you to run code from a private repository.
- Lock down your passwords with a reputable password manager and turn on multi-factor authentication (preferring app or key over SMS) for any important or sensitive account.
- Use an up-to-date, real-time anti-malware solution to block, detect, and remove threats like Omnistealer.
- Don't use your everyday user profile or main workstation as a test bench for random GitHub projects or side gigs; use a virtual machine or separate system instead.
- Finally, watch your crypto and banking accounts for unexplained logins or withdrawals, and move funds to new wallets if you suspect compromise.

For more details, check out the full article: [Read full article](https://www.malwarebytes.com/blog/news/2026/04/omnistealer-uses-the-blockchain-to-steal-everything-it-can)