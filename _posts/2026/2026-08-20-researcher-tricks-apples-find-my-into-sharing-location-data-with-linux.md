---
title: Researcher Tricks Apple's Find My into Sharing Location Data with Linux
date: 2026-08-20
categories: [TECHNOLOGY]
tags: [APPLE,LINUX,SECURITY,LOCATION,RESEARCH]
---

## Researcher Tricks Apple's Find My into Sharing Location Data with Linux 🚀

A young security researcher, known as **Zerotistic**, has ingeniously figured out how to enroll a Linux device into Apple's Find My network and access live location data. This 22-year-old innovator has successfully tricked Apple into sharing the location data that is typically reserved for Apple devices only.

It's crucial to clarify that this is not an exploit that allows arbitrary retrieval of any Apple user's location. Instead, it involves registering a non-Apple device to the Find My network and retrieving location data from individuals who have already chosen to share their locations with the Apple account owner.

### How It Works 🔍

To retrieve people-location data, Apple must trust that the machine in use belongs to its network and can receive the data sent over Apple's Push Notification service (APNs). The first step involved linking the Linux machine to the researcher's Apple account. Zerotistic navigated through Apple's standard GrandSlam authentication protocol to obtain an identity delegate. This delegate was then used to create a custom certificate signing request (CSR) in PKCS#10 format, signed with a 2048-bit RSA key using SHA-1, which Apple subsequently signed, providing an IDS certificate.

Further efforts were necessary to convince Apple that the Linux device could run Find My. Zerotistic discovered that a Find My registration request required the device to subscribe to six different subservices, define supported encryption types, and provide public keys for Apple's device-to-device messaging format. Additionally, it had to be signed using both an IDS certificate and an APNs certificate obtained during the initial network setup.

The researcher successfully enrolled the Linux machine in an Apple account and convinced Find My that it could receive location data via a persistent binary TLS connection to Apple's private APNs servers. By issuing a SubscribeAndFetch request, the device belonging to the researcher's friend was able to push an encrypted location key to the newly registered Linux device.

### The Final Challenge 🛠️

The last hurdle was reading the location data fetched from Apple's SearchParty service. This required a Linux script to unwrap Apple's messaging envelope, extract the shared location key, and decrypt the Find My location data, which includes coordinates, timestamps, and accuracy information. Remarkably, it took Zerotistic less than a week of tinkering to develop this Find My-busting technique.

The Register reached out to Apple to inquire if they were aware of the researcher's work, but there was no immediate response.

[Read full article](https://www.theregister.com/security/2026/08/20/researcher-tricks-apples-find-my-into-sharing-location-data-with-linux/5290496)