---
title: A Rigged Game ScarCruft Compromises Gaming Platform
date: 2026-05-05
categories: [CYBERSECURITY]
tags: [SCARCRUFT,GAMING,CYBERATTACK,ESPIONAGE]
---

## A Rigged Game: ScarCruft Compromises Gaming Platform

ESET researchers uncovered a multiplatform supply-chain attack by the North Korea-aligned APT group ScarCruft, targeting the Yanbian region in China - home to ethnic Koreans and a crossing point for North Korean refugees and defectors. In this ongoing attack, ScarCruft compromised Windows and Android components of a video game platform dedicated to Yanbian-themed games, trojanizing them with a backdoor named **BirdCall**. 

The backdoor, originally known to target Windows only, has now been discovered on Android as part of this supply-chain attack. The goal of the campaign is espionage, with the backdoor capable of collecting personal data and documents, taking screenshots, and making voice recordings. This attack likely aims to gather information on individuals based in or originating from the Yanbian region, particularly refugees or defectors deemed of interest to the North Korean regime. 

Our investigation began with a suspicious APK file found on VirusTotal. This APK turned out to be a trojanized card game called **延边红十** (machine translation: Yanbian Red Ten), which we traced back to its official website, [sqgame](https://www.sqgame[.]net). Sqgame is a gaming platform tailored for the people of Yanbian, hosting traditional Yanbian games for Windows, Android, and iOS. The APK available for download on the official website is the same as the APK we initially found on VirusTotal. 

Moreover, a second Android game **新画图** (machine translation: New Drawing) available for download from sqgame was also trojanized with the same backdoor. Further analysis revealed that the backdoor is an Android port of the ScarCruft group's BirdCall backdoor. While the Windows desktop client available on the sqgame website did not contain malicious code when we analyzed it, we later identified a trojanized mono.dll library originating from an update package of the desktop client hosted at [this URL](http://xiazai.sqgame.com[.]cn/dating/20240429.zip). ESET telemetry shows that this update package had been malicious since at least November 2024. 

BirdCall is a Windows backdoor written in C++ that we discovered in 2021 and attributed to ScarCruft. It has a wide range of spying capabilities, including taking screenshots, logging keystrokes, stealing credentials, and executing shell commands. The Android version of BirdCall implements a subset of the commands and capabilities of the Windows backdoor. 

Based on our research, Android BirdCall was actively developed over several months, with seven versions identified, ranging from version 1.0 (created approximately in October 2024) to version 2.0 (created approximately in June 2025). For the Windows compromise, ScarCruft took a clean mono library and patched it with extra code and data, containing a downloader. This downloader subsequently installs the BirdCall backdoor on victimized machines. 

For more details, read the complete article [here](https://www.welivesecurity.com/en/eset-research/rigged-game-scarcruft-compromises-gaming-platform-supply-chain-attack/).