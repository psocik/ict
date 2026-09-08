---
title: Hackers Drain $320M in Bitcoin from Liquid Network, Claim They're the Good Guys
date: 2026-09-07
categories: [CYBERSECURITY]
tags: [BITCOIN,HACKERS,LIQUID-NETWORK,SECURITY-RESEARCH]
---

## Hackers Drain $320M in Bitcoin from Liquid Network, Claim They're the Good Guys 🚨

Hackers have drained roughly **$320 million** in Bitcoin from the federation wallet backing the **Liquid Network**, while claiming to be the good guys. Liquid, a Bitcoin sidechain developed by Blockstream and used by exchanges and other financial institutions, said in a post on X on Sunday that around **4,000 BTC** had been withdrawn from its federation wallet by what it cautiously described as "purported white-hat hackers." The wallet held about **4,200 BTC** before the incident, meaning whoever was behind the exploit removed roughly **95 percent** of its holdings. Liquid disabled its bridge nodes while federation members investigate and asked exchanges to suspend L-BTC deposits and withdrawals.

The people behind the withdrawal appear keen to establish that this isn't your standard crypto heist. In a message embedded in a Bitcoin transaction, they identified themselves as **"whitehats"** and asked Blockstream to get in touch. Blockstream responded on-chain with contact details for its security team, and Liquid said the parties subsequently moved their communications to encrypted channels. Those responsible said they would return **"most"** of the Bitcoin once the vulnerability was fixed and Liquid's nodes had been updated. **"Please fix the bug first,"** the on-chain message said. **"The chain is under risk at latest commit right now. Make sure every node is patched. Then we will transfer the money back safely after confirming the fix."

Exactly how they managed to move almost the entire federation wallet remains under investigation. Liquid said the BTC was withdrawn through **SideSwap** using its **Peg-out Authorization Key**, or **PAK**, but that neither SideSwap's key nor any other PAK appeared to have been compromised. PAKs allow federation functionaries to recognize destinations authorized to receive peg-outs; the functionaries collectively release the corresponding Bitcoin. That leaves the rather important question of how an apparently authorized SideSwap peg-out came to empty almost the entire federation wallet without the relevant PAK being compromised. Other assets issued on Liquid, including stablecoins, do not appear to have been directly affected, and the Bitcoin network itself was untouched. Liquid is a federated sidechain whose members collectively manage the Bitcoin backing L-BTC, rather than relying on Bitcoin's miners to secure those funds. For now, those funds appear to be in the hands of people who insist they're conducting security research.

[Read full article](https://www.theregister.com/security/2026/09/07/hackers-drain-320m-in-bitcoin-from-liquid-network-claim-theyre-the-good-guys/5294770)