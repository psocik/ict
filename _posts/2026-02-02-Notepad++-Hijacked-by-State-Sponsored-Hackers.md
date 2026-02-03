---
title: Notepad++ Hijacked by State-Sponsored Hackers
date: 2026-02-02
categories: [SECURITY]
tags: [NOTEPAD++,SECURITY,HACKERS,CYBERSECURITY]
---

According to the analysis provided by the security experts, the attack involved infrastructure-level compromise that allowed malicious actors to intercept and redirect update traffic destined for notepad-plus-plus.org. The exact technical mechanism remains under investigation, though the compromise occurred at the hosting provider level rather than through vulnerabilities in Notepad++ code itself. Traffic from certain targeted users was selectively redirected to attacker-controlled servers with malicious update manifests. The incident began in June 2025 and continued until September 2, 2025, when a scheduled maintenance update occurred. After this date, no similar patterns in logs could be identified, indicating that the bad actors had lost access to the server. However, they maintained credentials for internal services until December 2, 2025, which allowed them to redirect traffic intended for https://notepad-plus-plus.org/getDownloadUrl.php to their own servers.  The malicious actors specifically aimed to intercept traffic on the Notepad++ domain, likely knowing about existing vulnerabilities related to insufficient update verification controls. 

After concluding research, no further vulnerabilities were observed after December 2, 2025. Notepad++ has since migrated to a new hosting provider with improved security practices. Enhancements to the updater, including stronger verification methods, are implemented to prevent future threats. 

For more detailed information, read the complete article [here](https://notepad-plus-plus.org/news/hijacked-incident-info-update/).