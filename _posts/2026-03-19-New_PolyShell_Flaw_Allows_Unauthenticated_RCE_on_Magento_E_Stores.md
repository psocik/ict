---
title: New 'PolyShell' Flaw Allows Unauthenticated RCE on Magento E-Stores
date: 2026-03-19
categories: [SECURITY]
tags: [MAGENTO,VULNERABILITY,RCE,SECURITY]
---

## New 'PolyShell' Flaw Allows Unauthenticated RCE on Magento E-Stores 🚨

A newly disclosed vulnerability dubbed **'PolyShell'** affects all Magento Open Source and Adobe Commerce stable version 2 installations, allowing unauthenticated code execution and account takeover. There are no signs of the issue being actively exploited in the wild, but eCommerce security company **Sansec** warns that "the exploit method is circulating already" and expects automated attacks to start soon. Depending on the web server configuration, the flaw can enable remote code execution (RCE) or account takeover via stored XSS, impacting most of the stores Sansec analyzed.

In a report this week, Sansec says that the security problem is rooted in Magento's REST API accepting file uploads as part of the custom options for the cart item. "When a product option has type 'file', Magento processes an embedded file_info object containing base64-encoded file data, a MIME type, and a filename. The file is written to pub/media/custom_options/quote/ on the server," the researchers explain. Sansec says **'PolyShell'** is named after its use of a polyglot file that can behave as both an image and a script. Sansec investigated all known Magento and Adobe Commerce stores and found that many stores expose files in the upload directory.

Adobe has released a fix, but it is only available in the second alpha release for version 2.4.9, leaving production versions vulnerable. Sansec says that Adobe offers a "sample web server configuration that would largely limit the fallout," but most stores rely on a setup from their hosting provider. Until Adobe releases the patch to production versions, store administrators are recommended to take the following actions:
- Restrict access to pub/media/custom_options/
- Verify that nginx or Apache rules actually prevent access there
- Scan stores for uploaded shells, backdoors, or other malware

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/new-polyshell-flaw-allows-unauthenticated-rce-on-magento-e-stores/)