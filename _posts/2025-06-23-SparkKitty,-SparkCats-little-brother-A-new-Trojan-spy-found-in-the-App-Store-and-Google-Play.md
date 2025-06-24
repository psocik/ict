---
title: SparkKitty, SparkCat’s little brother A new Trojan spy found in the App Store and Google Play
date: 2025-06-23
categories: [SECURITY]
tags: [MALWARE,TROJAN,IOS,ANDROID,APP STORE,GOOGLE PLAY]
---

**Here are the key facts about this new threat:**

The malware targets both iOS and Android devices, and it is spreading in the wild as well as through the App Store and Google Play. The app is already removed from the latter.

On iOS, the malicious payload is delivered as frameworks (primarily mimicking AFNetworking.framework or Alamofire.framework) or obfuscated libraries disguised as libswiftDarwin.dylib, or it can be embedded directly into the app itself.

The Android-specific Trojan comes in both Java and Kotlin flavors; the Kotlin version is a malicious Xposed module.

While most versions of this malware indiscriminately steal all images, we discovered a related malicious activity cluster that uses OCR to pick specific pictures.

The campaign has been active since at least February 2024.

To read the complete article see: [SecureList](https://securelist.com/sparkkitty-ios-android-malware/116793/).