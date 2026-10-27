---
title: Unveiling Sirius Backdoor A Multistage Fileless Campaign Disguised as FedEx Invoices
date: 2026-10-26
categories: [CYBERSECURITY]
tags: [MALWARE,SIRIUS,FEDEX,PHISHING,CYBERATTACK]
---

## Unveiling Sirius Backdoor: A Multistage Fileless Campaign Disguised as FedEx Invoices

🚨 During a recent priority customer escalation, our **Trellix Threat Response Team** investigated a suspicious alert involving the unexpected execution of a PDF document. What initially appeared to be a routine phishing attempt quickly unfolded into a sophisticated, multistage campaign delivering a previously undocumented variant of the **Sirius Backdoor**. 

While the initial delivery via an email containing a ZIP archive with a PDF seemed routine, the execution flow stood out due to its heavy use of **living-off-the-land (LotL)** techniques. Analysis revealed that the PDF abuses `/OpenAction` and `/Launch` objects to trigger an embedded Base64-encoded PowerShell command upon opening. The final payload is a new backdoor, which we named **SIRIUS BACKDOOR** based on the `SIRIUS_STUB_CONFIG` config and a few related patterns; it's a modern Microsoft Visual C++ based backdoor with extended remote access capabilities. 

### Attack Overview

This campaign utilizes a sophisticated **"Matryoshka doll"** execution model, where each stage exists solely to decrypt and reflectively load the next, ensuring the final payload never touches the disk in an unencrypted state. The attack starts with a geo-targeted spear-phishing email (in Korean) masquerading as a **FedEx Tax Invoice**. To evade email gateway security, the malicious payload is tucked inside a ZIP (`Fedex_tax_receipt.zip`) archive containing a weaponized PDF (`Fedex_tax_receipt.pdf`). The email is designed to mimic legitimate FedEx Billing Online automated notifications, including specific details such as a convincing invoice number (724156148) and a pending payment deadline, pressuring the recipient into opening the attachment. The use of the Korean language and South Korean currency (KRW) suggests a geo-targeted campaign, specifically aimed at corporate users or accounting departments within the region. 

### Execution Details

When a user opens `Fedex_tax_receipt.pdf`, they see a blank page, which is by design. The `/Launch` action specifically targets the Windows operating system and executes `powershell.exe` with stealth arguments: `-W h`, `-nop`, `-NOni`, `-ep BYPaSS`, and an `-EncodedCommand`. This Base64-encoded command processes an encrypted blob entirely within the PowerShell process memory, instead of downloading an .exe file, designed to bypass static file scanners. The script initializes an **AES-256** decryption engine in cipher block chaining (CBC) mode with Key: `LfBqaGHMQsA85Ha3pbu7Vg==` and IV: `+9aAse9v9VKdKbioQxwNxg==`, then uses the `IO.Compression.GZipStream` class for decompression. The decrypted/decompressed byte array is then loaded reflectively into memory as a .NET executable assembly, making it **"fileless"** since it is loaded from an array rather than a file path. 

### Bypass Techniques

This reflective loading contributes to antivirus bypass, as most traditional AV products scan files written to disk, and the script stays in memory. It also impacts **AMSI (antimalware scan interface)** detection, as the use of encryption and GZip requires AMSI to catch the payload at the exact moment of the Load call, presenting a very narrow window of detection. The Stage 2 Injector proactively patches **ETW (Event Tracing for Windows)** and **HotPatching** to "blind" EDR/AV sensors. It then downloads the final payload (`zeus.dat`) and uses **Early Bird APC Injection** to hide the Sirius Backdoor inside legitimate Windows processes like `msbuild.exe` or `svchost.exe`. 

To read the complete article see: [Read full article](https://www.trellix.com/en/blogs/research/sirius-backdoor-fileless-campaign-fedex-invoices/) 