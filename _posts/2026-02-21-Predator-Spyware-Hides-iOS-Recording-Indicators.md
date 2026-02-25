---
title: Predator Spyware Hides iOS Recording Indicators
date: 2026-02-21
categories: [SECURITY]
tags: [PREDATOR,SPYWARE,IOS,SECURITY,MALWARE]
---

## Predator Spyware Hooks iOS SpringBoard to Hide Mic and Camera Activity 🚨

Intellexa’s **Predator spyware** can hide iOS recording indicators while secretly streaming camera and microphone feeds to its operators. This malware does not exploit any iOS vulnerability but leverages previously obtained kernel-level access to hijack system indicators that would otherwise expose its surveillance operation. Apple introduced recording indicators on the status bar in iOS 14 to alert users when the camera or microphone is in use, displaying a green or an orange dot, respectively.

### How It Works 🔍

Researchers at mobile device management company **Jamf** analyzed Predator samples and documented the process of hiding the privacy-related indicators. According to Jamf, Predator hides all recording indicators on iOS 14 by using a single hook function (`HiddenDot::setupHook()`) inside SpringBoard, invoking the method whenever sensor activity changes (upon camera or microphone activation). By intercepting it, Predator prevents sensor activity updates from ever reaching the UI layer, so the green or red dot never lights up.

Jamf researchers explain: “The target method _handleNewDomainData: is called by iOS whenever sensor activity changes - camera turns on, microphone activates, etc.” They further state, “By hooking this single method, Predator intercepts ALL sensor status updates before they reach the indicator display system.”

### Stealth Mechanism 🕵️‍♂️

The hook works by nullifying the object responsible for sensor updates (SBSensorActivityDataProvider in SpringBoard). In Objective-C, calls to a null object are silently ignored, so SpringBoard never processes the camera or microphone activation, and no indicator appears. Because SBSensorActivityDataProvider aggregates all sensor activity, this single hook disables both the camera and the microphone indicators.

### Conclusion 🔒

Without indicators lighting up on the status bar, the spyware activity remains completely hidden from the regular user. Jamf notes that technical analysis reveals signs of the malicious processes, such as unexpected memory mappings or exception ports in SpringBoard and mediaserverd, breakpoint-based hooks, and audio files written by mediaserverd to unusual paths.

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/predator-spyware-hooks-ios-springboard-to-hide-mic-camera-activity/)