---
title: Telegram Desktop Flaw Lets Hidden JavaScript Exfiltrate Messages From HTML Exports
date: 2026-09-14
categories: [SECURITY]
tags: [TELEGRAM,JAVASCRIPT,SECURITY,VULNERABILITY]
---

## Telegram Desktop Flaw 🚨

A flaw in Telegram Desktop allowed a bot's message to plant hidden JavaScript inside chats that users exported to HTML files, according to security researchers at ExPatch. This issue was detailed in a writeup published on September 12.

In Telegram, the message appeared ordinary, featuring a link button. However, the script executed when someone opened the export file in a web browser. This vulnerability could enable the script to copy every message in that file to an attacker-controlled server or alter what the page displayed.

Telegram issued a fix in July, but the app update does not affect files exported with earlier versions, meaning old HTML exports may still harbor the malicious script.

### How It Works 🔍

Telegram Desktop, which is available for Windows, macOS, and Linux, allows users to save individual chats or entire accounts as HTML pages. Bots can attach rows of buttons under their messages, known as inline keyboards, with the bot determining the text displayed on each button. Before the fix, the export code inserted button text directly into the HTML page without proper escaping, allowing a bot to embed a script tag in a button's text, disguised with invisible characters.

The bot does not need to be present in the targeted chat. If a message containing only web link buttons is forwarded, the script travels with it, as discovered by the researchers.

When an export file containing the message was opened, the script executed automatically, gathering every message in that file, including sender names, timestamps, chat details, and the local file path, sending this information to the attacker's server. The script could also modify the page, as demonstrated by the researchers, who showed it could replace the entire export with a fake Telegram "verification" form.

### Recommendations ✅

The researchers rated the flaw 8.2 out of 10 on the CVSS 3.1 scale. To mitigate this risk, users are advised to:
- Update Telegram Desktop to version 7.0.1 or later, or to version 6.9.4 or later on the beta channel.
- Re-export any chats that were saved as HTML before the fix.
- Open old files only with JavaScript disabled.
- Treat any HTML exports made prior to the fix as untrusted.

As of September 14, Telegram had not provided guidance for users with older exports.

[Read full article](https://thehackernews.com/2026/09/telegram-desktop-flaw-lets-hidden.html)