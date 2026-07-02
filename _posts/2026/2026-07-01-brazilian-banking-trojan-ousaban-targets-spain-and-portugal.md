---
title: Brazilian Banking Trojan Ousaban Targets Spain and Portugal
date: 2026-07-01
categories: [CYBERSECURITY]
tags: [BANKING,MALWARE,CYBERSECURITY,PHISHING]
---

## Brazilian Banking Trojan Ousaban Targets Spain and Portugal

A banking trojan long used against victims in Brazil has been retooled to target banking customers in Spain and Portugal, using phishing PDFs, steganography, and geofencing to stay hidden. In a new analysis, Fortinet's FortiGuard Labs said the malware, known as Ousaban, has been active against the two countries since May 2026. This banking trojan, from the same Latin American family as Casbaneiro, now comes wrapped in extra layers of evasion designed to keep it in front of intended victims and away from researchers.

The attack starts with a phishing PDF disguised as a broken file, which nudges the victim to click an **Update** button that opens a malicious webpage. Posing as a government tax portal, the page profiles each visitor and only continues the attack for users who appear to be in Spain or Portugal. That server-side check inspects language, time zone, and IP data, blocks VPN connections, and screens out sandboxes, hiding the criteria from analysts. Visitors who pass receive a script that pulls down an image resembling a PDF icon, using steganography to conceal an appended archive holding the Ousaban payload. According to Li Zhao, a consultant at application security firm Black Duck, **"Ousaban is not a fundamentally new type of attack, but rather a highly optimized evolution of traditional, decade-old Latin American banking trojan strategies,"** noting it is written in Delphi and reuses a 2008-era encryption scheme.

Once running, Ousaban watches for the victim to open one of dozens of targeted banking services, including Santander, BBVA, CaixaBank, Revolut, and Caixa Geral de Depósitos. When it spots one, its toolkit includes screenshots, keylogging, clipboard injection, and remote control, and it displays fake bank screens to trick users into handing over their details. For its command server, Ousaban leans on evasion rather than a fixed address. FortiGuard said it resolves a domain that changes daily, derived from a hash of the current date pulled from a Google error page, while a decoy Pastebin link points analysts to a dead-end private IP. Jason Soroko, a senior fellow at certificate-management firm Sectigo, stated, **"Geofenced malware can look absent from outside the target region,"** urging teams to correlate endpoint, mail, DNS, and proxy logs rather than trust sandbox results. Fortinet, drawing on its own telemetry, said the campaign remains live, with the credential theft aimed squarely at bank fraud.

For more details, check out the full article here: [Read full article](https://www.infosecurity-magazine.com/news/ousaban-banking-trojan-spain/)