---
title: Exposing AdFection How Discover-Tech Turned Targeted Ads Into a Pipeline for Zero-Click Mercenary Spyware
date: 2026-10-15
categories: [CYBERSECURITY]
tags: [SPYWARE,ADVERTISING,MALWARE,RESEARCH]
---

## Exposing AdFection: How Discover-Tech Turned Targeted Ads Into a Pipeline for Zero-Click Mercenary Spyware

Our research indicates that the online advertising ecosystem is abused to facilitate the delivery of zero-click targeted spyware, and that the simple display of a targeted ad is enough for infection. This report exposes zero-click spyware delivered via targeted ads, which we call **AdFection**, and is the first technical demonstration that mercenary spyware is being distributed via targeted advertisements. 🚨

The advertising ecosystem collects a lot of data and enables individual-level targeting, allowing malicious parties to exploit this infrastructure to target certain individuals based on user data included in ad auctions. Advertisers or DSPs may run HTML and JavaScript code when an ad is shown to the user. That code retrieves additional JavaScript code, which may, in turn, load further code, such as a browser exploit to install spyware. Since the code can contain identifiers for the user or their device, arbitrary JavaScript code can be sent precisely to a single user's device.

We present technical evidence that the Israel-based company **Discover-Tech**, while purporting to be a legitimate advertising company, appears to be a front for large-scale ad espionage abuse, including the automatic delivery of mercenary spyware when ads are displayed to a target and the mass profiling and deanonymization of users. The company serves as a bridge between ad vendors and the mercenary spyware ecosystem. Its platform, **Controlium**, allows malicious actors to precisely profile and de-anonymize millions of individuals, fingerprint their devices, and target them with a form of zero-click hacking, where their devices can be automatically infected when an ad is displayed to them. 

Discover-Tech operates a platform called **MyDSP**, which interfaces with online ad vendors including Google, Yandex, Vungle (Liftoff), and Sunteng, and also purchases ads via the ad vendors Eskimi and Comcast-owned Beeswax (Freewheel).

A large number of ads placed by Discover-Tech contain a script tag pointing back to what the company refers to as a "NOAS server". This tag causes the ad, when rendered, to connect back to Discover-Tech, submit advertising identifiers for the user (either a cookie ID or a mobile ad ID), and automatically execute any JavaScript code returned. The NOAS server decides, apparently based on a combination of the source IP address and the advertising identifiers, whether the target is eligible to receive any JavaScript. Discover-Tech ads are used to infect and profile on behalf of mercenary spyware vendor **Candiru**. We also detail connections between Discover-Tech and another mercenary hacking company, **Bindecy**, as well as connections with **Intelos**, a mercenary ADINT firm. We show how Candiru works with Discover-Tech to conduct AdFection attacks, and describe one such attack: the targeting and infection of devices at the international media network **Al Jazeera** with Candiru's mercenary spyware.

Discover-Tech appeared on several lists of "certified" and "approved" ad vendors maintained by Google and the advertising industry association **IAB Europe** from the year 2020 until 2026. This helped make Discover-Tech appear to be a legitimate ad vendor and facilitate its participation in the digital advertising ecosystem at scale. As a result of this investigation, both Google and IAB Europe removed Discover-Tech from their ad vendor registries in early October 2026. Google, which collaborated in the investigation, terminated Discover-Tech's access to its ad exchange platforms. Beeswax removed Discover-Tech from its ad buying platform, Vungle (Liftoff) paused Discover-Tech's access while conducting a review, and Eskimi blocked Discover-Tech's accounts and domains.

To read the complete article see:
[Read full article](https://citizenlab.ca/research/how-discover-tech-turned-targeted-ads-into-a-pipeline-for-spyware/) 
