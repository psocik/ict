---
title: High-Severity Flaw in Open WebUI Affects AI Connections
date: 2026-01-06
categories: [SECURITY]
tags: [CVE-2025-64496,OPEN WEBUI,AI CONNECTIONS,VULNERABILITY]
---

A high-severity security vulnerability affecting Open WebUI has been uncovered, potentially exposing users to account takeover (ATO) and, in some cases, full server compromise. The flaw, tracked as CVE-2025-64496 and discovered by Cato Networks researchers, impacts Open WebUI versions 0.6.34 and older when the Direct Connections feature is enabled. The issue carries a severity rating of 7.3 out of 10.

The vulnerability sits within Direct Connections, a feature that allows users to link Open WebUI to external, OpenAI-compatible model servers. While designed to support flexibility and self-hosted AI workflows, the feature can be abused if a user is persuaded to connect to a malicious server posing as a legitimate AI endpoint. At its core, the flaw stems from a trust failure between untrusted model servers and the user’s browser session. A hostile server can send a crafted server-sent events message that triggers the execution of JavaScript code in the browser. This allows an attacker to steal authentication tokens stored in localStorage. Once obtained, those tokens grant full access to the victim’s Open WebUI account. Chats, uploaded documents, and API keys can all be exposed. The Open WebUI backend itself remains secure unless the compromised user holds elevated permissions.

The consequences vary depending on user privileges. These include theft of JSON web tokens, session hijacking, full account compromise (including access to chat history and uploaded files), and exposure of sensitive credentials shared in conversations. Remote code execution (RCE) is also possible if the user has workspace.tools permissions enabled.

The issue was reported to Open WebUI maintainers in October 2025 and publicly disclosed on November 7, 2025, following patch validation and CVE assignment. Open WebUI versions 0.6.35 and later block the malicious execute events, addressing the user-facing risk. Cato Networks stated, "Open WebUI’s patch is effective for v0.6.35 or newer versions, which closes the user-facing Direct Connections vulnerability." Additionally, Cato Networks stressed the importance for organizations to strengthen authentication, sandbox extensibility, and restrict access to specific resources.

For the complete article, visit [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/flaw-open-webui-affects-ai/).