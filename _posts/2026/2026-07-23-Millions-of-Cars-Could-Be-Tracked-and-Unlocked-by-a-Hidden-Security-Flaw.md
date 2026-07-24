---
title: Millions of Cars Could Be Tracked and Unlocked by a Hidden Security Flaw
date: 2026-07-23
categories: [SECURITY]
tags: [CARS,SECURITY,VULNERABILITY,TRACKING]
---

## Major Security Flaw in KARR Security System 🚗🔒

A recent investigation has revealed a significant security flaw in the KARR Security System, a Bluetooth-enabled aftermarket alarm installed in millions of vehicles. This vulnerability could allow thieves to track and unlock cars without the owner's knowledge.

The KARR system, primarily found in vehicles from Honda, Toyota, Mazda, Ford, and Jeep, has been installed in approximately 2.2 million American cars. Alarmingly, many owners are unaware that these systems are active, as they may have declined the paid service, assuming the hardware was inactive. However, dormant units can be activated with a simple Bluetooth command, exposing their functionalities.

### The Flaw Explained 🔍

Researchers from the University of California San Diego discovered that every KARR device shares the same authentication key, which is stored in plain text within the KARR smartphone app. This means that once the key is extracted, an attacker can unlock any KARR-equipped vehicle manufactured since 2017. Standing just a few yards away, an attacker can disable the ignition, potentially stranding the driver without any alerts.

### Location Tracking Concerns 📍

In addition to the unlocking issue, KARR units continuously broadcast Bluetooth identifiers, allowing anyone to track their locations over time. This data can be accessed through crowdsourced databases, creating a detailed history of where the vehicle has been parked.

### Delayed Response from Acrisure 🕒

The flaw was disclosed to Acrisure in January 2025, but a firmware fix was only released on July 20, 2026—18 months later. This delay raises concerns about the real-world risks associated with this vulnerability, especially since many car owners may not even know they need to update their systems.

### What Can You Do? 🛠️

To check if your vehicle is equipped with a KARR system, look for a KARR sticker on the driver-side window or a sticker reading "SWDS" for SouthWest Dealer Services. If you find one, download the KARR app and apply the firmware update to secure your vehicle.

For more details, you can read the full article here: [Read full article](https://www.malwarebytes.com/blog/bugs/2026/07/millions-of-cars-could-be-tracked-and-unlocked-by-a-hidden-security-flaw)