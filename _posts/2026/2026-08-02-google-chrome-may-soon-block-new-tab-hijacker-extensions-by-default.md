---
title: Google Chrome May Soon Block New Tab Hijacker Extensions by Default
date: 2026-08-02
categories: [TECHNOLOGY]
tags: [GOOGLE,CHROME,SECURITY,EXTENSIONS]
---

## Google Chrome May Soon Block New Tab Hijacker Extensions by Default 🚀

Google is preparing a new Chrome security feature that would block policy-installed extensions from hijacking the New Tab page or changing the default search engine. BleepingComputer spotted the protection in a chain of work-in-progress Chromium Gerrit changes. It has not shipped yet, but Google plans to enable it by default once the changes are approved.

Anunoy Ghosh, who works at Google, stated, **"In low-trust environments (unmanaged consumer devices), enterprise policy force-installs and recommendations are abused to lock in search engine or new tab page hijackers."** Ghosh added, **"This CL enables the kBlockDseNtpOverrideExtensionsOnUnmanagedDevices feature flag by default, activating the end-to-end blocking defense on unmanaged Windows and macOS devices."**

### Current Situation
Right now, Chrome allows organizations to use enterprise policies to force-install extensions and control browser settings. While this is not problematic on properly managed work devices, malware has been abusing the same feature on regular consumer PCs. A malicious program can add local Chrome policy keys without your permission and force-install an extension that replaces the New Tab page, changes your search engine, or redirects searches to suspicious websites. Chrome may then believe that the extension was installed by an administrator, preventing you from removing or disabling it. In some cases, Chrome also displays the confusing **"Managed by your organization"** message, even though the PC is not actually owned or managed by an organization. Google describes these consumer PCs as **"low-trust"** environments because Chrome is reading policies stored locally without confirmation from a trusted authority, such as a domain or MDM service.

### Proposed Protection
Under the proposed protection, Chrome would block attempts to install policy-controlled extensions that override the New Tab page or default search engine. The installation would be canceled, and Chrome would save the extension ID in a blocked-extension preference. Chrome would also stop trying to download the same blocked extension during future policy checks, which should prevent repeated installation attempts and unnecessary network activity.

Google is also addressing another trick used by malware: an extension that you installed manually would no longer be converted into a locked, policy-controlled extension. It would remain under your control, allowing you to disable or remove it. If a previously managed device loses its trusted management status but still has local policy keys, Chrome would automatically uninstall affected New Tab and search-engine override extensions. Legitimate administrators would also have access to an escape-hatch policy that disables the protection when a required enterprise extension overrides the New Tab page or search engine.

The Gerrit changes are still under review, so the feature is not available in stable Chrome yet.

[Read full article](https://www.bleepingcomputer.com/news/google/google-chrome-may-soon-block-new-tab-hijacker-extensions-by-default/)