---
title: Android 17 Introduces Granular Contact Access
date: 2026-04-21
categories: [TECHNOLOGY]
tags: [ANDROID,PRIVACY,CONTACTS,PERMISSIONS]
---

## Android 17 Introduces Granular Contact Access 🚀

Android 17 (currently in preview) is introducing a new **Contact Picker** that allows users to grant apps access to specific contacts rather than the entire list. Previously, any app that needed a single phone number had to request `READ_CONTACTS`, which handed over every name, email, and number. An app that can harvest your entire contact list can map your social network, identify your family members, and potentially hand that data to whoever's buying.

From Android 17 onward, apps will need to be more specific about what contact data they access. Google's updated Play policy will require apps to use the Contact Picker or the Android Sharesheet as the main way to access contacts. `READ_CONTACTS` will be reserved for apps that genuinely can't function without it.

Additionally, location permissions are also set to become more granular and privacy-friendly in Android 17. Previously, apps could ask for your precise or general location, and you could allow it just once, any time you're using the app, or not at all. The new button adds nuance by letting app developers ask for your location in the moment, tied to a specific action, like finding a local cafe. There will also be a persistent indicator to let you know when an app is using your location, similar to the alerts for camera or microphone access.

The tighter permissions management in Android 17 is a big deal for privacy advocates, because overly broad access is how data brokers build detailed profiles about you. Those profiles can then be used for aggressive or invasive advertising, including scams. Google timed these privacy announcements alongside its latest Ad Safety report, which says it blocked **8.3 billion** policy-violating ads and suspended **24.9 million** advertiser accounts in the last year. The **8.3 billion** figure is up from 2024, when Google blocked **5.1 billion** ads. In 2024, Google blocked **415 million** scam-related ads. In 2025, that number grew to **602 million**. While Google says it caught over **99%** of violations before users ever saw them, **1%** of an insanely large number is still insanely large. The ads that still get through are damaging. In December, we reported on sponsored search results pointing to malicious AI chats that instructed people to install infostealer malware.

[Read full article](https://www.malwarebytes.com/blog/mobile/2026/04/android-17-ends-all-or-nothing-access-to-your-contacts)