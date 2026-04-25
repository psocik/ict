---
title: Android 17 Enhances Privacy with New Contact Picker
date: 2026-04-21
categories: [TECHNOLOGY]
tags: [ANDROID,PRIVACY,CONTACTS,PERMISSIONS]
---

## Android 17 Enhances Privacy with New Contact Picker 🚀

Android 17 (currently in preview) is introducing a new **Contact Picker** that allows users to grant apps access to specific contacts instead of the entire list. Previously, any app that needed just one phone number had to request `READ_CONTACTS`, which provided access to every name, email, and number in your contact list. This broad access could enable apps to map your social network and potentially share that data with third parties.

From Android 17 onward, apps will need to be more specific about the contact data they access. Google's updated Play policy will require apps to utilize the Contact Picker or the Android Sharesheet as the primary method for accessing contacts. The `READ_CONTACTS` permission will be reserved for apps that genuinely cannot function without it.

Additionally, location permissions are also set to become more granular and privacy-friendly in Android 17. Previously, apps could ask for your precise or general location, and you could allow it just once, any time you're using the app, or not at all. The new button adds nuance by allowing app developers to request your location in real-time, tied to specific actions, such as finding a local cafe. A persistent indicator will also inform you when an app is using your location, similar to alerts for camera or microphone access.

The tighter permissions management in Android 17 is a significant advancement for privacy advocates, as overly broad access is how data brokers build detailed profiles about users. These profiles can be exploited for aggressive or invasive advertising, including scams. Google has timed these privacy announcements alongside its latest Ad Safety report, which states it blocked 8.3 billion policy-violating ads and suspended 24.9 million advertiser accounts in the last year. This figure marks an increase from 2024, when Google blocked 5.1 billion ads. In 2024, Google blocked 415 million scam-related ads, and that number grew to 602 million in 2025. While Google claims it caught over 99% of violations before users ever saw them, even 1% of a massive number is still substantial. The ads that slip through can be damaging.

In December, we reported on sponsored search results leading to malicious AI chats that instructed users to install infostealer malware.

For more details, [Read full article](https://www.malwarebytes.com/blog/mobile/2026/04/android-17-ends-all-or-nothing-access-to-your-contacts).