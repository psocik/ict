---
title: TARmageddon Flaw in Popular Rust Library Leads to RCE
date: 2025-10-22
categories: [SECURITY]
tags: [CVE-2025-62518,RCE,RUST LIBRARY,SECURITY VULNERABILITY]
---

Tracked as CVE-2025-62518 (CVSS score of 8.1) and dubbed **TARmageddon**, the security defect is described as a desynchronization issue that occurs during the processing of nested TAR files with a specific mismatch between PAX and ustar headers.

If a file entry has both headers and the ustar header incorrectly specifies a zero size, an inconsistency in the parser’s data boundaries determination logic results in the parser advancing the stream position based on the ustar size, even if the PAX header correctly specifies the file size.

“By advancing 0 bytes, the parser fails to skip over the actual file data (which is a nested TAR archive) and immediately encounters the next valid TAR header located at the start of the nested archive. It then incorrectly interprets the inner archive’s headers as legitimate entries belonging to the outer archive,” explains **Edera**, the company that reported the flaw in August.

The bug could lead to remote code execution, as its successful exploitation results in file overwrites, allowing attackers to replace configuration files. It could also be exploited in supply chain attacks, hijacking build backends, the security firm says.

To read the complete article see: [SecurityWeek](https://www.securityweek.com/tarmageddon-flaw-in-popular-rust-library-leads-to-rce/).