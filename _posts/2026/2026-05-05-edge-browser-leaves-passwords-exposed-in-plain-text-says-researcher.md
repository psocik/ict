---
title: Edge Browser Leaves Passwords Exposed in Plain Text, Says Researcher
date: 2026-05-05
categories: [CYBERSECURITY]
tags: [EDGE,PASSWORDS,SECURITY,MICROSOFT]
---

## Edge Browser Vulnerability 🚨

A Norwegian researcher has identified a serious issue with Microsoft Edge's Password Manager that could pose significant risks for businesses. Tom Jøran Sønstebyseter Rønning discovered that passwords are being saved in plain text within the browser. This means that any PC, especially shared machines, within an organization could be at risk.

In a post on X, Rønning explained that when users save passwords in Edge, the browser decrypts every credential at startup and keeps it in process memory, regardless of whether the user visits the site. This finding was confirmed by German IT publication Heise.de, which demonstrated that even after closing and reopening the browser, saved passwords could still be found in plain text.

Microsoft's response to this discovery has been rather nonchalant. According to the Norwegian website Itavisen.no, Rønning reported the issue to Microsoft, who stated that this behavior is 'by design.' David Shipley, CEO of Beauceron Security, criticized Microsoft's response, saying, "No, it's not a feature. That's an easy way to cop out of responsibility."

Shipley further emphasized that this vulnerability is an open invitation to cyber criminals, stating, "It's waving the white flag at cybercriminals and turning that white flag into a blank check for info stealers." Other browsers, like Google Chrome, utilize App Bound Encryption to secure browser data, ensuring it is not stored in process memory in plain text.

If Google can secure its browser effectively, there is no reason Microsoft cannot do the same with Edge. Given Microsoft's attitude, users may want to consider alternative password managers that offer better security. Additionally, Rønning plans to publish a simple tool on GitHub that will allow users to verify for themselves that passwords are stored in plain text in memory.

For more details, check out the full article: [Read full article](https://www.csoonline.com/article/4167437/edge-browser-leaves-passwords-exposed-in-plain-text-says-researcher-2.html)