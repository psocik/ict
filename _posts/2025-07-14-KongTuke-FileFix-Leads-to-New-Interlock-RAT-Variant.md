---
title: KongTuke FileFix Leads to New Interlock RAT Variant
date: 2025-07-14
categories: [MALWARE]
tags: [INTERLOCK,RAT,KONGTUKE,CYBERSECURITY]
---

Researchers from The DFIR Report, in partnership with Proofpoint, have identified a new and resilient variant of the Interlock ransomware group’s remote access trojan (RAT). This new malware, a shift from the previously identified JavaScript-based Interlock RAT (aka NodeSnake), uses PHP and is being used in a widespread campaign.

Since May 2025, activity related to the Interlock RAT has been observed in connection with the LandUpdate808 (aka KongTuke) web-inject threat clusters. The campaign begins with compromised websites injected with a single-line script hidden in the page’s HTML, often unbeknownst to site owners or visitors.

The linked JavaScript employs heavy IP filtering to serve the payload, which first prompts the user to click a captcha to “Verify you are human” followed by “Verification steps” to open a run command and paste in from the clipboard. If pasted into the run command, it will execute a PowerShell script which eventually leads to Interlock RAT.

Proofpoint researchers have observed both Interlock RAT Node.js and Interlock RAT PHP based variants. The Interlock RAT PHP based variant was first spotted in June 2025 campaigns.

[Read the complete article here.](https://thedfirreport.com/2025/07/14/kongtuke-filefix-leads-to-new-interlock-rat-variant/) 

📅 Date: 2025-07-14
🔖 Tags: Interlock, RAT, KongTuke, Cybersecurity