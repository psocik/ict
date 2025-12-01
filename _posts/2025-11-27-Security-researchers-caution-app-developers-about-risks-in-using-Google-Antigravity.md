---
title: Security researchers caution app developers about risks in using Google Antigravity
date: 2025-11-27
categories: [SECURITY]
tags: [GOOGLE,ANTIGRAVITY,VULNERABILITIES,APP DEVELOPMENT,SECURITY RESEARCH]
---

Google's Antigravity, an AI agent development tool released on November 18th, is facing scrutiny due to newly discovered vulnerabilities. Security researchers are cautioning app developers about the risks associated with its use. These concerns have prompted Google to update its known issues page and acknowledge the reported problems. 

Mindgard, one of the first to identify the flaws, reports that a malicious actor could exploit Antigravity's rule that AI assistants must strictly follow user-defined rules. This could lead to backdoor attacks via compromised workspaces, allowing attackers to execute arbitrary code on user systems. According to Mindgard's head of research and innovation, Aaron Portnoy, even the most restrictive mode of operation doesn't prevent this exploitation. The attack vector is through the source code repository opened by the developer, eliminating the need for direct user prompting.  

The core issue lies in Antigravity's dependence on trusted workspaces. A compromised workspace can become a persistent backdoor, affecting all subsequent Antigravity usage, even after reinstallation. This cross-workspace risk highlights the need to treat AI development environments as sensitive infrastructure. Another researcher, Adam Swanda, discovered an indirect prompt injection vulnerability, which Google acknowledged as a known issue. Wunderwuzzi blogged about finding five holes, including data exfiltration and remote command execution via indirect prompt injection.  

Swanda recommends assuming all external content is adversarial when building AI agents with tool-calling. He advises using strong input and output guardrails, stripping special syntax, and implementing tool execution safeguards. Explicit user approval should be required for high-risk operations, especially those triggered after handling untrusted content. Relying on prompts for security is discouraged. Portnoy emphasizes the importance of security teams vetting AI-assisted tools, considering their intended use case, data access, and connections to ensure security.  

To read the complete article see: [Csoonline](https://www.csoonline.com/article/4097698/security-researchers-caution-app-developers-about-risks-in-using-google-antigravity.html)