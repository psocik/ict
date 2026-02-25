---
title: Keenadu The Tablet Conqueror and Major Android Botnets
date: 2026-02-17
categories: [CYBERSECURITY]
tags: [KEENADU,ANDROID,MALWARE,BOTNETS,SECURITY]
---

## Keenadu: The Tablet Conqueror and Major Android Botnets 🚀

Our investigation uncovered a new backdoor, dubbed **Keenadu**, which mirrored Triada’s behavior by embedding itself into the firmware to compromise every app launched on the device. Keenadu proved to have a significant footprint; following its initial detection, we saw a surge in support requests from our users seeking further information about the threat.

### Key Findings 🔍
- We discovered a new backdoor in the firmware of devices belonging to several brands.
- The infection occurred during the firmware build phase, where a malicious static library was linked with `libandroid_runtime.so`.
- Once active on the device, the malware injected itself into the **Zygote** process, similarly to Triada.

### How Keenadu Operates 🛡️
A copy of the backdoor is loaded into the address space of every app upon launch. The malware is a multi-stage loader granting its operators the unrestricted ability to control the victim’s device remotely. We successfully intercepted the payloads retrieved by Keenadu. Depending on the targeted app, these modules hijack the search engine in the browser, monetize new app installs, and stealthily interact with ad elements.

### Integration with Android Botnets 🔗
Our investigation established a link between some of the most prolific Android botnets: Triada, BADBOX, Vo1d, and Keenadu. The malware operates within the context of every app on the device, thereby gaining access to all their data and rendering the system’s intended app sandboxing meaningless.

### Conclusion 📝
Keenadu represents yet another case where key Android security principles are compromised. It provides interfaces for bypassing permissions, allowing attackers to gain virtually unrestricted control over the victim’s device.

For more detailed information, you can read the complete article [here](https://securelist.com/keenadu-android-backdoor/118913/).