---
title: How to Examine Polyglot Files with Spectra Analyze
date: 2026-03-17
categories: [CYBERSECURITY]
tags: [POLYGLOT,FILES,MALWARE,ANALYSIS,SECURITY]
---

## How to Examine Polyglot Files with Spectra Analyze

Polyglot files combine elements from multiple file formats, concealing executable code in overlooked sections such as metadata or comments within images or documents. These files remain valid and can be processed or executed. Polyglot files can enter your environment in several ways:

- **Phishing**: Attackers send emails containing polyglot files disguised as legitimate invoices, documents (e.g., PDFs or DOCs), or image files (e.g., JPGs).
- **Drive-by Downloads**: Users may unknowingly download polyglot files from compromised websites that appear legitimate.
- **File-Upload and Web Interfaces**: Attackers upload polyglot files to web services, such as chat or document-sharing platforms, that verify only file types and fail to detect hidden malicious code.
- **Cloud Content Delivery Networks (CDNs)**: Attackers may host malicious files on trusted platforms such as Discord or other CDNs, exploiting user trust in these domains.
- **Removable Media**: Attackers use these devices to introduce polyglot files into air-gapped or secure networks.

Submitting the hash for analysis provides immediate, detailed indicators of polyglot behavior in the Report Summary. Key details include “File Type,” “File Format,” and “The Threat Actor / Name.” The “Sample Description” also offers context that requires further analysis. Using the graph visualization feature in the Report Summary, I first review the layers of extracted files. These layers eventually reveal the presence of the “overlay” sub-file, at which point I see a malicious verdict.

This file presents itself as a valid GIF89a image, a large overlay section and contains the embedded PHP payload. The File Type was identified as Image / GIF (GIF89a) with a File Size of 9.09 KB. The PHP overlay serves as the malicious payload for a Dirtelti-family backdoor web shell. It includes hardcoded HTTP references to an external domain that acts as a decoy cursor resource. This extracted file, named “overlay,” was identified as a Text / PHP Script with a File Size of 9.1 KB.

Two URLs embedded in the PHP script reference domains that are likely used as live connectivity checks. Both URLs are categorized under “entertainment” and “software_downloads,” consistent with a legitimate resource site being used as cover traffic or a dead-drop indicator. In the Static Analysis section, the Indicators detected a Macro and tagged it as “contains-script,” which means the file includes one or more script files. Additional tags include antivirus, image-corrupt, image-segment-unknown and overlay. Dynamic analysis provides additional behavioral insights beyond static analysis, including changes to the file system, registry, network connections, and process activity. In this case, we identified 36 signatures, 70 TCP, UDP, DNS, and URL events, 1 behavioral indicator with multiple findings, 18 dropped files, 15 MITRE ATT@CK mappings, and 2 YARA matches. After behavioral detections in Dynamic Analysis, two YARA findings were identified. One notable finding, related to Polyglot files, is described as “Finds image files w/ PHP code in images.”

A specific rule for Polyglot Image PHP Trojan Detection detects PHP polyglot files that masquerade as GIF images. These files start with the GIF89a magic bytes, making them appear valid to content-type checkers and basic validators. They also contain embedded PHP code `<?php`, which a PHP interpreter will execute if the file is served or included. The rule fires when both of the following conditions are met: The file begins with the GIF89a magic header at offset 0, indicating it presents itself as a GIF image, and the string `<?php` appears anywhere within the file, indicating the presence of embedded PHP code.

[Read full article](https://www.reversinglabs.com/blog/examine-polyglot-files-spectra-analyze)