---
title: FBI Accessed Windows Laptops After Microsoft Shared BitLocker Recovery Keys
date: 2026-01-24
categories: [POLICY]
tags: [FBI,MICROSOFT,PRIVACY,BITLOCKER,SECURITY]
---

A recent legal case has revealed a surprising gap in computer privacy that many people likely didn’t know existed. It turns out Microsoft can unlock personal computers for the government, and they recently did exactly that during a major investigation. The story began in Guam, where federal agents were investigating a massive scheme to steal roughly $2 million from a COVID-19 relief program. Prosecutors describe the case as a large-scale conspiracy involving Kathleen Peredo and Marleen Pinaula, two staff members at the Guam Department of Labour with high-level access to internal systems. 

According to the Department of Justice’s press release, both are accused of manipulating applications with Charissa Tenorio, Frankie Rosalin, and several others, and allegedly submitting fraudulent claims or aiding the conspiracy to steal taxpayer funds.

After seizing three laptops during the raid, the FBI hit a technological dead end because the devices were protected by BitLocker, a tool in Windows that scrambles your files so they cannot be read without a 48-digit code. While government experts once called this security "impenetrable," the FBI didn’t need to break the code in this case; they simply asked Microsoft for it. When you set up a new Windows PC, the system often asks if you want to back up your recovery key to your online Microsoft account. While this is very convenient if you ever forget your password, it also means Microsoft keeps a copy of that key on its servers.

Once the FBI obtained a search warrant, Microsoft handed over the keys on February 10, 2025. This allowed investigators to gain immediate entry to files belonging to defendant Charissa Tenorio. By providing these codes, Microsoft effectively sidestepped the encryption, making the security irrelevant. Microsoft confirmed they provide these keys when presented with a valid legal order. Spokesperson Charles Chamberlayne explained that while the system offers convenience, it carries a "risk of unwanted access." He noted that Microsoft receives about 20 such requests annually, but they can only assist if the user has chosen to store their key in the cloud.

This level of cooperation stands in contrast to other tech giants. As Hackread.com reported, Apple famously fought a similar order in 2016 involving the San Bernardino shooting. Apple refused to bypass its security, arguing it would endanger all users, forcing the FBI to hire a contractor to hack the device instead. To ensure your computer is truly private, experts suggest checking your Microsoft account online. You can choose to move your keys to a physical USB drive or print them out and keep them in a safe place. That way, you are the only one who holds the power to unlock your data.

To read the complete article see: [Hackread Article](https://hackread.com/fbi-windows-laptops-microsoft-bitlocker-recovery-keys/) .