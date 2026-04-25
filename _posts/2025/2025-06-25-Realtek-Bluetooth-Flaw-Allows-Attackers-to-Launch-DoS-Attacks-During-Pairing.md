---
title: Realtek Bluetooth Flaw Allows Attackers to Launch DoS Attacks During Pairing
date: 2025-06-25
categories: [SECURITY]
tags: [DOS,REALTEK,BLUETOOTH,VULNERABILITY]
---

A critical vulnerability in Realtek’s Bluetooth Low Energy (BLE) implementation enables attackers to launch denial-of-service (DoS) attacks during device pairing.

The flaw (CVE-2024-48290) affects Realtek RTL8762E BLE SDK v1.4.0, allowing malicious actors to disrupt connections by exploiting protocol inconsistencies.

Attackers can send a crafted `ll_terminate_ind` packet or inject premature pairing data, crashing the target device’s Bluetooth stack and blocking legitimate connections.

For more details, see the full article: [GB Hackers](https://gbhackers.com/realtek-bluetooth-flaw/) 