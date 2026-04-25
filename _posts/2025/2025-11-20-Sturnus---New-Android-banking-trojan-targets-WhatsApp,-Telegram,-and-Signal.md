---
title: Sturnus - New Android banking trojan targets WhatsApp, Telegram, and Signal
date: 2025-11-20
categories: [SECURITY]
tags: [ANDROID,BANKING TROJAN,MALWARE,WHATSAPP,TELEGRAM,SIGNAL]
---

Sturnus is a new Android banking trojan with full device-takeover abilities. It bypasses encrypted messaging by capturing on-screen content and can steal banking credentials, remotely control the device, and hide fraudulent actions from the user.

Sturnus steals data through two linked mechanisms: HTML overlays and accessibility-based keylogging. It stores phishing templates for targeted banking apps and displays them via a WebView that captures all input and sends it to the C2. After exfiltration, it disables the used overlay to avoid detection. A full-screen block overlay can hide its activity.

“Because it relies on Accessibility Service logging rather than network interception, the malware can read everything that appears on screen—including contacts, full conversation threads, and the content of incoming and outgoing messages—in real time.” continues the report. “This makes the capability particularly dangerous: it completely sidesteps end-to-end encryption by accessing messages after they are decrypted by the legitimate app, giving the attacker a direct view into supposedly private conversations. 

Sturnus enables full remote control of infected devices using two complementary capture methods: real-time screen mirroring through Android’s display-capture framework and a fallback system that builds screenshots from Accessibility events when standard capture fails. A native library then manages the session through the VNC RFB protocol. The malware also sends a structured map of all on-screen elements, tracking clicks, text input, scrolling, and app launches without using images. This method uses less bandwidth, avoids screen-capture alerts, and works even on hidden or protected elements.

For more information, you can read the complete article [here](https://securityaffairs.com/184878/cyber-crime/sturnus-new-android-banking-trojan-targets-whatsapp-telegram-and-signal.html).