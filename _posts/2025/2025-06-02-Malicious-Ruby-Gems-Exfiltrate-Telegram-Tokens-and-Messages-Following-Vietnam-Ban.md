---
title: Malicious Ruby Gems Exfiltrate Telegram Tokens and Messages Following Vietnam Ban
date: 2025-06-02
categories: [RESEARCH]
tags: [RUBYGEMS,TELEGRAM,MALWARE,CYBERSECURITY]
---

Socket’s Threat Research Team has uncovered an ongoing supply chain attack targeting the RubyGems ecosystem. A threat actor using the aliases Bùi nam, buidanhnam, and si_mobile published two malicious gems, fastlane-plugin-telegram-proxy and fastlane-plugin-proxy_teleram, designed to impersonate legitimate Fastlane plugins. These gems silently exfiltrate all data sent to the Telegram API by redirecting traffic through a command and control (C2) server controlled by the threat actor. This includes bot tokens, chat IDs, message content, and attached files.

The timing is notable: the gems appeared just days after Vietnam ordered nationwide blocking of Telegram on May 21, 2025. Marketed as “proxy” plugins, they exploit the increased demand for Telegram workarounds. The branding and timing indicate that developers affected by the ban were the intended targets.

Because Fastlane runs inside CI/CD pipelines that handle sensitive assets like signing keys, release binaries, and environment secrets, the impact reaches deep into software build and release workflows.

At the time of publication, both gems remain live on RubyGems. We have petitioned for their removal. To read the complete article see: [Socket Blog](https://socket.dev/blog/malicious-ruby-gems-exfiltrate-telegram-tokens-and-messages-following-vietnam-ban).