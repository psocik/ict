---
title: GitHub Ends Automatic Install Script Execution for npm
date: 2026-06-10
categories: [TECHNOLOGY]
tags: [GITHUB,NPM,SECURITY,SOFTWARE,DEVELOPMENT]
---

## GitHub Ends Automatic Install Script Execution for npm 🚀

GitHub is set to end the ability for attackers to leverage automatic install script execution in npm when expected changes arrive in July. While coders will still have the option to enable this function, the default setting will block it. In version 12, default settings are changing, with GitHub stating, **"it turns an npm install behavior that runs automatically today into one you explicitly opt into."**

### Key Changes 🔑
- **allowScripts defaults to off:** npm install will no longer execute preinstall, install, or postinstall scripts from dependencies unless explicitly allowed in your project.
- This includes native node-gyp builds; a package with a binding.gyp and no explicit install script will still be blocked.
- Prepare scripts from git, file, and link dependencies are also blocked in the same manner.

Analysts and users have generally applauded this change, noting that while it narrows the exposure to supply chain attacks, it does not eliminate it entirely. Sonu Kapoor, maintainer for CVE Lite CLI in the OWASP Incubator Project, remarked, **"This does not eliminate npm supply chain risk; it removes a major automatic execution path."**

### Industry Reactions 💬
Zach Steindler, a GitHub principal engineer, highlighted that attackers have targeted these capabilities to propagate attacks quickly from one compromised package to many. Sanchit Vir Gogia, chief analyst at Greyhound Research, pointed out that GitHub was the last major repository to make this default change, as rivals like Yarn, pnpm, and Bun have already blocked third-party install scripts by default.

Kapoor emphasized the importance of this change, stating, **"install-time execution often happens in privileged environments with access to tokens, secrets, internal registries, build artifacts, or deployment paths."** This shift represents a move from implicit trust to explicit trust in package management.

### Conclusion 🎉
When npm changes its defaults, it alters the security posture of practically every enterprise development environment globally. This significant update is a step towards enhancing security in the software development lifecycle.

For more details, [Read full article](https://www.csoonline.com/article/4183859/github-finally-pulls-the-plug-on-automatic-install-script-execution-for-npm-2.html)