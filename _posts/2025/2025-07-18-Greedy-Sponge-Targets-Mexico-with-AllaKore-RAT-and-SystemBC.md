---
title: Greedy Sponge Targets Mexico with AllaKore RAT and SystemBC
date: 2025-07-18
categories: [RESEARCH]
tags: [ALLAKORE RAT,SYSTEMBC,CYBERSECURITY,THREAT ACTOR]
---

A financially-motivated threat actor, active since early 2021, has been targeting Mexican organizations with custom packaged installers that deliver a modified version of AllaKore RAT. Arctic Wolf documented 2022 and 2023 campaign samples from this unidentified threat actor in a previous report. We are now referring to this group as Greedy Sponge, due to its financial focus and prior use of a popular “SpongeBob” meme on its C2.

There have been a number of notable changes since we last reported on this threat group. The AllaKore RAT payload has been heavily modified to enable the threat actors to send select banking credentials and unique authentication information back to their command-and-control (C2) server, for the purpose of conducting financial fraud.

AllaKore has also recently been seen delivering a secondary infection of SystemBC, a multi-platform malware proxy tool written in C that can be used to download and execute additional malware.

Since the middle of 2024, the installation and post-exploitation processes the group uses were updated to include better geofencing and more potent secondary infections. Historically, geofencing to the Mexican region took place in the first stage, via a .NET downloader included in the trojanized Microsoft software installer (MSI) file. This has now been moved server-side to restrict access to the final payload, thus hampering detection efforts by defenders.

To read the complete article see:
[Greedy Sponge Targets Mexico with AllaKore RAT and SystemBC](https://arcticwolf.com/resources/blog/greedy-sponge-targets-mexico-with-allakore-rat-and-systembc/) 