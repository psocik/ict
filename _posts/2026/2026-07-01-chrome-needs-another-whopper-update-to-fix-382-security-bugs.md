---
title: Chrome Needs Another Whopper Update to Fix 382 Security Bugs
date: 2026-07-01
categories: [SECURITY]
tags: [CHROME,SECURITY,UPDATE,VULNERABILITIES]
---

## Chrome Needs Another Whopper Update to Fix 382 Security Bugs 🚀

Yesterday, on the last day of June, Google published an update that includes a whopping **382 security fixes** for Chrome. The stable channel has been updated to **150.0.7871.46/.47** for Windows and Mac, **150.0.7871.46** for Linux, and **150.0.7871.63** for Android. The update will roll out over the coming days and weeks. To update manually, click the More menu (three dots), then go to **Settings > About Chrome**. If an update is available, Chrome will start downloading it automatically. Restart Chrome to complete the update, and you'll be protected against these vulnerabilities.

Among the 382 security fixes, **358** were found by Google itself, with **15** of those rated as **Critical**. Google rates them as Critical severity because they could allow an attacker to run arbitrary code outside the browser's sandbox, which makes it the highest tier on its rating scale. Google uses internal code sanitizer tools and fuzzing techniques to find these vulnerabilities.

One vulnerability rated as High stands out. It's a flaw tracked as **CVE-2026-13789**. The official description is: "Use after free in GPU in Google Chrome prior to 150.0.7871.47 allowed a remote attacker who had compromised the renderer process to potentially perform a sandbox escape via a crafted HTML page." Vulnerabilities that allow an attacker to escape the sandbox are dangerous because they can impact the whole device.

Use-after-free is a class of vulnerability caused by incorrect use of dynamic memory during a program's operation. If, after freeing a memory location, a program does not clear the pointer to that memory, an attacker can exploit that mistake. In Chromium/Chrome architecture, the term GPU usually denotes the dedicated GPU process that handles hardware-accelerated rendering, compositing, WebGL, video decode, and related graphics operations. So, again, update as soon as you can! Users of other Chromium browsers, keep an eye out for your next update.

[Read full article](https://www.malwarebytes.com/blog/bugs/2026/07/chrome-needs-another-whopper-update-to-fix-382-security-fixes)