---
title: Export to PDF allows local file inclusion/path traversal in Microsoft 365
date: 2025-07-08
categories: [RESEARCH]
tags: [MICROSOFT 365,SECURITY,PDF,VULNERABILITY]
---

Some months ago, while analyzing a client’s web application, I came across a file conversion feature that transformed documents in any format into PDF and published them on the company’s SharePoint through a convenient graphical interface.

This functionality, managed by the client’s internal application, had an issue that allowed reading local system files when converting HTML documents to PDF. Obviously, I reported this problem as a high-impact finding, complete with PoC and evidence. During the final presentation call with the client, the project lead thanked me for identifying the issue and candidly informed me that the web.config file shown in the screenshots I had provided was not from one of their systems, as they were only using a wrapper of the official Microsoft’s APIs, and he suggested to report the bug directly to Microsoft. 🤯

After finishing the call, I rushed into our Microsoft 365 SharePoint instance to figure out how to trigger and replicate the issue. I then spent my Friday night submitting the bug to MSRC, and 4 months later I have been rewarded with a $3000 bounty for this issue (Severity: Important). 🎉 Hereafter, the details of the finding that now has been (obviously) remediated by Microsoft.

To read the complete article see:

[Export to PDF allows local file inclusion/path traversal in Microsoft 365](https://security.humanativaspa.it/export-to-pdf-allows-local-file-inclusion-path-traversal-in-microsoft-365/) 

---