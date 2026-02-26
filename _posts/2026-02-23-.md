---
title: Another Day, Another Malicious JPEG
date: 2026-02-23
categories: [CYBERSECURITY]
tags: [MALWARE,JPEG,CYBERSECURITY,EMAIL,THREAT]
---

## Another Day, Another Malicious JPEG 🚨

**Source:** SANS Internet Storm Center  
**Published on:** February 23, 2026  

Xavier discussed recent malware campaigns that download JPEG files with embedded malicious payloads. Last week, another campaign using the same technique was discovered in malware samples caught by email proxies. This newly identified campaign employed JScript as the first stage, unlike a batch downloader used in an earlier campaign, prompting a detailed look at its initial infection chain.

The email had a spoofed sender address to make it look like it came from a legitimate Czech company, with its body containing the organization's logo. However, the message failed DMARC/SPF checks, which would likely lead to it being quarantined by most email servers. The attachment was a JScript file, weighing 1.17 MB. This large file size was caused by a first layer of obfuscation, where 17,188 of its 17,222 lines were identical. After removal, only 34 lines remained, and the file size shrank to 31 kB. The first 10 lines attempt elementary persistence by copying the JScript file to the startup folder. The script constructs a PowerShell command line and then leverages WMI’s Win32_Process.Create method to spawn a hidden PowerShell instance. That instance decodes Base64-encoded contents of a variable using UTF-8 and executes the resulting script via Invoke-Expression.

A final layer of obfuscation from a key variable revealed ~2kB of Base64 encoded PowerShell. This code contained a URL for the next payload stage: [hxxps://ia600603.us.archive.org/13/items/msi-pro-with-b-64_202602/MSI_PRO_with_b64.png](hxxps://ia600603.us.archive.org/13/items/msi-pro-with-b-64_202602/MSI_PRO_with_b64.png). At the time of writing, this URL was no longer live. However, VirusTotal information indicates the file would have been a JPEG (with a PNG extension), also distributed as optimized_msi.png, a file name observed in a previous diary. A Base64-encoded string would then be parsed from the downloaded image and loaded using reflection, with its Main method called using specific arguments.

Further analysis of the arguments revealed another obfuscated string, obfuscated by reversing characters and Base64 encoding. Decoding this string yielded the URL: [hxxps://hotelseneca.ro/ConvertedFileNew.txt](hxxps://hotelseneca.ro/ConvertedFileNew.txt). This URL was still active at the time of writing. The TXT file contained a reversed, Base64 encoded EXE file, which – according to VirusTotal information for its hash – turned out to be a sample of Remcos RAT. This malware was likely its intended final stage.

### Key Indicators of Compromise (IoCs):  
**URLs:**  
- [hxxps://ia600603.us.archive.org/13/items/msi-pro-with-b-64_202602/MSI_PRO_with_b64.png](hxxps://ia600603.us.archive.org/13/items/msi-pro-with-b-64_202602/MSI_PRO_with_b64.png)  
- [hxxps://hotelseneca.ro/ConvertedFileNew.txt](hxxps://hotelseneca.ro/ConvertedFileNew.txt)  

**SHA-256 Hashes:**  
- 1st stage JScript file: `edc04c2ab377741ef50b5ecbfc90645870ed753db8a43aa4d0ddcd26205ca2a4`  
- Decoded Remcos RAT EXE file: `1158ef7830d20d6b811df3f6e4d21d41c4242455e964bde888cd5d891e2844da`  

For more details, [read the full article here](https://isc.sans.edu/forums/diary/Another%20day,%20another%20malicious%20JPEG/32738/).