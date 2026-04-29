---
title: New Android Spyware Morpheus Linked to Italian Surveillance Firm
date: 2026-04-28
categories: [CYBERSECURITY]
tags: [ANDROID,SPYWARE,SURVEILLANCE,MALWARE]
---

## New Android Spyware Morpheus Linked to Italian Surveillance Firm

🚨 **Osservatorio Nessuno** has uncovered a new spyware named **Morpheus** that spreads through fake Android apps to steal sensitive data. This alarming discovery highlights the increasing use of covert surveillance tools in our digital age.

The spyware is distributed via deceptive Android apps masquerading as legitimate updates. Attackers employ a common low-cost tactic: disrupt a service and trick victims into installing a fake app to restore it. Victims receive an SMS linking to a site that impersonates an ISP, leading them to download the malicious software.

### How Morpheus Works

1. **Dropper App**: The initial dropper app installs a hidden second-stage payload. It checks for existing installations and deploys the payload with minimal user awareness.
2. **Disguise**: The second stage disguises itself as legitimate system components, using fake icons and names to appear trustworthy. It forces users to grant dangerous permissions, including **Accessibility access**, allowing it to read screens, interact with apps, and capture sensitive data.
3. **Permission Workflow**: After granting permissions, the spyware initiates a Permission Workflow that creates an overlay with a fake update process, effectively disabling user interaction.

### Covert Operations

Morpheus exploits overlay windows and Accessibility features to gain control of the device, bypassing security measures. It uses the powerful **SYSTEM_ALERT_WINDOW** permission to display fake screens while secretly granting itself permissions in the background. This includes enabling **Wireless Debugging** and connecting to ADB to gain elevated privileges.

### Targeting Antivirus Software

In its third phase, Morpheus disables several known antivirus programs, including Google's **SafetyCore**, **Bitdefender**, **Sophos**, and others. This malware does not require root access and persists across reboots, making it challenging to remove.

### Italian Origin

The analysis of the source code suggests an Italian origin for the spyware, with clues pointing to its infrastructure using encrypted configurations and Italian-hosted servers. The report links Morpheus to **IPS Intelligence**, an Italian firm known for lawful interception technologies used by governments.

**Morpheus is extremely invasive**, capable of recording audio and video, silently pairing with WhatsApp devices, and deliberately weakening the security of infected phones.

For more details, read the full article here: [Read full article](https://securityaffairs.com/191398/malware/new-android-spyware-morpheus-linked-to-italian-surveillance-firm.html)