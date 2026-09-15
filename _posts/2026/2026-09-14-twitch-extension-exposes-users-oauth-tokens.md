---
title: Twitch Extension Exposes Users' OAuth Tokens
date: 2026-09-14
categories: [SECURITY]
tags: [TWITCH,OAUTH,SECURITY,MALWARE]
---

## Twitch Extension Exposes Users' OAuth Tokens 🚨

A browser extension called **Twitch Enhanced Viewer | JeetBot**, available in the official Chrome and Firefox stores, has been found to send users' Twitch OAuth session tokens to a commercial bot service. This extension boasts over **30,000 installs** and is marketed as a legitimate third-party tool for Twitch, claiming to block ads, enforce 1080p (full HD) playback, bypass region restrictions, and enable channel-point collection.

However, an analysis by application security company **Socket** reveals that the extension captures the authorization header used by the Twitch web client, extracts the user's OAuth token, and transmits these credentials through proxy servers operated by JeetBot, a commercial Russian-language streaming and chatbot service.

### How It Works 🔍

In the current versions of the extension, the token is appended directly to redirected proxy requests as an `auth=` URL parameter, which ends up in the proxy server's request logs, making it easily retrievable by the software vendor. 

> "When the extension redirects Twitch's video playlist request (to usher.ttvnw[.]net) through that proxy, it appends the token as an &auth= query parameter," Socket explains. "Because the token is placed in the URL query string, it is written in cleartext into the proxy server's request logs." This issue occurs for every Twitch channel the user watches, except for a set of ten Russian-language channels hardcoded into the extension's code.

### Previous Security Risks ⚠️

Socket also highlights that earlier versions of the extension included more explicit credential-theft mechanisms. The developer provided a disclaimer in the Firefox Add-ons store, stating: "Previous versions of the extension transmit your OAuth-twitch token to our server. This is necessary for the stream to run in 1080/1440p." However, the data privacy disclosure for the Chrome variant claims that the developer "disclosed that it will not collect or use your data."

At the time of publishing, the extension was still available in both the Chrome Web Store and the Firefox Add-Ons store. Socket researchers recommend that users **remove the extension** from their browsers, **disconnect all sessions in Twitch**, and then **re-authenticate** to invalidate any tokens that may have been compromised.

For more details, check out the full article: [Read full article](https://www.bleepingcomputer.com/news/security/twitch-extension-with-30k-installs-exposes-users-oauth-tokens/) 
