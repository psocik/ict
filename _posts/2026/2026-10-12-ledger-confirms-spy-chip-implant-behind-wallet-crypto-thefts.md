---
title: Ledger Confirms Spy Chip Implant Behind Wallet Crypto Thefts
date: 2026-10-12
categories: [SECURITY]
tags: [LEDGER,CRYPTO,THEFT,SECURITY,HARDWARE]
---

## Ledger Confirms Spy Chip Implant Behind Wallet Crypto Thefts 🚨

Ledger has confirmed that some of its devices distributed through Southeast Asian reseller CryptoBilis were compromised with a hardware implant that drained users' cryptocurrency wallets. On **October 9**, Ledger launched an investigation into user reports of cryptocurrency losses and asked CryptoBilis to stop selling and shipping Ledger devices. The next day, Ledger confirmed hardware tampering on at least one device. 

**"Ledger can confirm that one of the impacted users' devices contained an unauthorized hardware implant,"** Ledger stated. They recommend users who purchased a Ledger device from this reseller to **not initiate setup** if they have not yet done so. If you have set up your Ledger device, consider moving assets to a new Ledger signer (with a new seed). Additionally, Ledger confirmed that all user reports of unexpected fund drains were linked to devices sold through CryptoBilis and described the affected volume as **limited**.

While the company did not disclose the type of devices compromised in this supply-chain attack, reports online talk about a spy implant in Ledger X devices that blends with the legitimate hardware. Mark Karpelès, currently leading Karpeles Lab Inc. and CTO at Shells.com, showed a picture of the new implant in Ledger X, saying that it was **"quite an evolution"** from previous versions featuring manually soldered wires. According to Karpelès, the malicious hardware captured the device's display output and button presses to identify the seed phrase, then transmitted it to the attacker over an LTE connection using an eSIM. **"Ledger Nano X are used to store crypto. The spy implants are used to steal whatever crypto you store in those Ledger Nano X,"** Karpelès explained.

Tibane Labs, a cryptocurrency research and development studio, confirmed Karpelès' finding, adding that there were two implant versions for Ledger X. In a report over the weekend, Tibane Labs notes that the threat actor made room for the malicious circuitry by replacing the original battery with a smaller one, which powers both the implant and the Ledger X. **"Under the battery and antenna sits an ST STM32G431KBU6 (Arm Cortex‑M4, 128 KB flash, UFQFPN‑32),"** the researchers found inside one of the devices. For connectivity, the actor used **"a tiny eSIM, an 8‑pad package just 2×2 mm, next to the MCU, and a shielded LTE module that sends the words out."** The second variant, which appears to be the same one that Karpelès described, is more advanced. It ran on the original battery and fit into the space normally occupied by the foam padding under the OLED display. In both cases, the telltale was the antenna wire, which ran along the top edge in the case of the second implant. In the first implant, the antenna is taped across the top of the battery and the shielded LTE module. The researchers warned that the specimen above used **"a designed, panelised flex PCB, the kind ordered from a board house, not a hand-built one-off."**

Ledger provides a **'Genuine Check'** mechanism to determine the authenticity of the device; however, it explicitly warns that it cannot detect added implants when the device's original Secure Element remains intact. At this time, there's no indication that any other Ledger resellers are shipping compromised wallets; however, the community's trust in the resellers' network has been compromised, with many now calling for its dismantling.

[Read full article](https://www.bleepingcomputer.com/news/security/ledger-confirms-hardware-wallet-spy-implant-behind-crypto-thefts/) 