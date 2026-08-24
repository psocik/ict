---
title: The Invisible Passenger in Your Car
date: 2026-08-21
categories: [CYBERSECURITY]
tags: [ANDROID,MALWARE,CYBERSECURITY,AD-FRAUD]
---

## The Invisible Passenger in Your Car 🚗

While monitoring Android threats in June 2026, we discovered a new piece of Android malware. What struck us as unusual was that it installed like an ordinary user app yet made no attempt to disguise itself as legitimate software: it had no user interface at all. This led us to suspect the app might be reaching users' devices without their knowledge. Further investigation confirmed that hypothesis and allowed us to reconstruct the entire infection chain.

We identified new Android malware: a multi-stage downloader whose ultimate purpose is **ad fraud** and the creation of a **proxy botnet**. The malware spread through the built-in updaters of Android-based automotive head unit firmware. This is the first documented case of malware found on a car head unit with an infection chain specific to that type of device. We attribute this activity, with high confidence, to the **MoYu Group**, an actor linked to the **BADBOX** botnet.

Kaspersky solutions detect the threats described below under the following detection names: HEUR:Trojan-Dropper.AndroidOS.Agent.vu, HEUR:Trojan-Downloader.AndroidOS.Agent.ov, HEUR:Trojan-Proxy.AndroidOS.Zhima.*, HEUR:Trojan.AndroidOS.Vo1d.* The design of firmware for DoFun head units enabled attackers to distribute malware. We notified the vendor about the distribution scheme, and they subsequently reported fixing the security issues.

The infection chain began with the **TWCore app**, a legitimate system application responsible for collecting analytics data and updating the head unit software. An MQTT message broker sends a message containing information about the APK files that need to be downloaded and installed on the head unit. Notably, the object describing this message includes an `installNotExists` field, a Boolean flag that allows TWCore to install apps that weren't originally present on the device.

Our telemetry revealed previously unknown malware at these file paths. Our data indicates that in every observed case, the malware was installed by an app with the package name `com.tw.core`, which matches the TWCore package name. The first stage, the **JarService dropper**, is a small app with no UI that decrypts data stored as encrypted blocks within the Trojan's code. This decrypted data contains serialized information about the payload version and entry point, such as the `wa` method of the `com.c.j.qbh` class, for further loading.

In the third stage, the malware sends a POST request to `/cpc/api/task` every 90 minutes by default, containing information about the infected device and the Trojan's configuration version. If the configuration is outdated, the C2 server returns an updated configuration. The functionality of these commands suggests that the malware can be used to display ads, commit ad fraud (serving as a clicker), and download additional malicious code. At the time of publishing this report, the attackers were using the `loadlib2` and `http` commands.

While analyzing the complete infection chain, we noticed that the stage 2 loader created a thread with the meaningful name `mosdk-host-loader`. This led us to a malicious app installed on various TV set-top boxes with the package name `com.abc.nexus`. The service containing the launch code for the JarService-like dropper is named `AdmoyuService`. In light of this and the name of the malicious thread found in the payload code, we concluded that `moyu` in the service name referred to MoYu Group, one of the actors linked to the BADBOX malware platform.

For further details, you can read the complete article here: [Read full article](https://securelist.com/android-head-unit-malware/121106/)