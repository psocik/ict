---
title: JaredFromSubway MEV Bot Hacked in $15 Million Crypto Theft
date: 2026-06-22
categories: [SECURITY]
tags: [CRYPTO,HACKING,ETHEREUM,MEV,SECURITY]
---

## 🚨 JaredFromSubway MEV Bot Hacked in $15 Million Crypto Theft

The **JaredFromSubway Ethereum MEV (Maximal Extractable Value) bot** suffered a staggering **$15 million loss** after an attacker manipulated its opportunity-detection logic by creating fake cryptocurrency trading opportunities. The breach was detected on Saturday by blockchain security firm **Blockaid**, and today, JaredFromSubway confirmed that the attacker used fake pools and tokens to trick the bot into approving helper contracts.

According to Blockaid, the attacker deployed contracts designed to appear as profitable MEV opportunities to JaredFromSubway's automated execution system. The bot automatically analyzed routes and trade opportunities that seemed financially rewarding, generating the transactions needed to execute them and granting ERC-20 token approvals to contracts controlled by the attacker.

It appears that the attacker planned the heist meticulously, as early transactions served as harmless tests to confirm the bot's action routines. Later, the threat actor changed the route so that the allowance was not consumed or revoked after the bot granted approvals. The attacker accumulated valid spending permissions without immediately using them, reaching up to **92.1614 WETH** approved to an attacker-controlled helper contract. Ultimately, the attacker used the open approvals to withdraw **WETH, USDC, and USDT** from the JaredFromSubway MEV bot contract via the transferFrom function.

MEV bots are ultra-fast automated trading systems that scan Ethereum and other blockchains for opportunities to make money by exploiting the order and timing of transactions before they are included in a block. JaredFromSubway is a private MEV operation with no publicly available code, known as one of Ethereum's most aggressive and visible "sandwich"-bot operations. In a sandwich attack, the bot detects a user's pending trade, places a buy order immediately before it, and then sells immediately afterward, profiting from the price movement caused by the victim's transaction. This practice is controversial as it often results in worse prices for regular traders while generating profits for the bot operator.

Initially, JaredFromSubway offered a **$3 million bounty** to the attacker for the full return of the stolen funds, promising no further action would be taken. After receiving no response, JaredFromSubway increased the bounty to **$7.5 million** for the return of just 50% of the stolen amount, with **$1 million** to be given to the community. JaredFromSubway is also negotiating with "a white-hat hacking group" regarding the stolen **$15 million**, but there is no confirmation of a deal yet.

[Read full article](https://www.bleepingcomputer.com/news/security/jaredfromsubway-mev-bot-hacked-in-15-million-crypto-theft/)