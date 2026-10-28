---
title: Attackers Take Control of Dahua Cameras and Video Recorders Via Easy4IP
date: 2026-10-27
categories: [CYBERSECURITY]
tags: [DAHUA,CAMERAS,SECURITY,VULNERABILITIES]
---

## Attackers Take Control of Dahua Cameras and Video Recorders Via Easy4IP 🚨

Ukraine warns that attackers can remotely access Dahua cameras and recorders via Easy4IP, allowing them to view video feeds and change settings. Ukraine's cyber incident response team, CERT-UA, has issued a warning regarding unauthorized remote access to IP cameras and video recorders made by Dahua. In its alert dated **October 23, 2026**, it reports that attackers have been able to watch live video, modify device settings, and create their own accounts.

The attackers exploited Easy4IP, Dahua's cloud feature that enables users to access devices remotely. When this feature is enabled, the camera or recorder connects to Dahua's cloud and registers using its serial number. Anyone who knows the serial number may gain access to the device through the cloud, bypassing the protection typically provided by a router's firewall. This means that a camera not directly exposed to the internet may still be at risk. CERT-UA warns that devices with Easy4IP enabled may be vulnerable even when they cannot be accessed directly from the internet.

### Key Points from CERT-UA's Report:
- The main vector for attacks is the P2P/cloud access function (Easy4IP).
- The device initiates an outgoing connection to the manufacturer's cloud infrastructure and registers by serial number.
- Access is established via the cloud, bypassing NAT and firewall protections.

Serial numbers follow predictable patterns, allowing attackers to guess them automatically and check which devices are registered in the cloud. Simply keeping a serial number private is not enough to ensure security. Once attackers connect to a device, they may attempt to bypass its login using common or weak passwords or exploit security flaws in outdated firmware, particularly vulnerabilities CVE-2021-33044 and CVE-2021-33045, which allow attackers to bypass authentication without a password.

### Signs of Compromise:
1. Look for accounts you don't recognize.
2. Check for changed settings, including text added over the video image.
3. Review audit logs for logins using Dahua's DVRIP protocol from the local address 127.0.0.1, indicating access through the cloud service.

### Recommendations from CERT-UA:
- Turn off P2P and cloud access if not in use.
- Keep cameras off the internet.
- For remote access, use a VPN and allow only authorized IP addresses.
- Regularly check the account list for unknown accounts and disconnect any unknown cloud accounts.
- Update the software manually to the latest version and establish a regular update routine.

CERT-UA advises organizations that detect signs of unauthorized access to report them to [email protected] ⚠️

All devices with active P2P functionality are at risk. 

[Read full article](https://securityaffairs.com/201827/hacking/attackers-take-control-of-dahua-cameras-and-video-recorders-via-easy4ip.html) 
