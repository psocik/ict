---
title: Android Spyware Alert! Fake government app targeting Android users in India!
date: 2025-06-05
categories: [SECURITY]
tags: [ANDROID,SPYWARE,MALWARE,SECURITY ALERT]
---

Recently, we came across a detection in our telemetry report named “PM KISAN YOJNA”, masquerading as the official government application that has gained our attention. This latest Android malware is a dropper that delivers a stealer to collect sensitive user information.

Let’s move to the technical part…

To evade security measures, some samples were deliberately malformed, and the malware uses a multi-stage dropper technique. The malware author intentionally crafted these dropper payloads to bypass static analysis, APK analysis tools such as Apktool and Jadx were unable to decompile them, complicating the analysis.

Here, I have used a tool apkinspector to decode AndroidManifest.xml from an APK, shown in Fig.1. It requests permissions such as QUERY_ALL_PACKAGES and REQUEST_INSTALL_PACKAGES to gain access to install apps without user knowledge.

**To read the complete article see:**
[https://labs.k7computing.com/index.php/android-spyware-alert-fake-government-app-targeting-android-users-in-india/](https://labs.k7computing.com/index.php/android-spyware-alert-fake-government-app-targeting-android-users-in-india/) 
