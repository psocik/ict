---
title: Signal Bug Could Let Someone Keep Listening After You Hang Up
date: 2026-10-21
categories: [SECURITY]
tags: [SIGNAL,BUG,VULNERABILITY,SECURITY,MALWAREBYTES]
---

## Signal Bug Could Let Someone Keep Listening After You Hang Up 🚨

A recently disclosed flaw in Signal's calling software could allow another participant to keep hearing you after you hang up. This critical vulnerability, tracked as **CVE-2026-113380** (CVSS score 9.3 out of 10), affects RingRTC versions earlier than 2.72.0. RingRTC is the open-source library behind Signal's voice and video calling functionality, providing calling components for its mobile and desktop applications.

The flaw specifically concerns how Signal's calling library shuts down a call. Importantly, it does not affect how it encrypts conversations. According to the published vulnerability description, another participant could overwhelm a call's internal event queue and interfere with the steps that should disconnect it when you end the call.

### User Concerns 🤔
The primary concern for users is unwanted listening after someone believes a conversation has ended. If a malicious call participant successfully triggered the flaw, they could potentially continue hearing audio that the other person no longer intended to share. This could include an offhand remark, a conversation with someone nearby, or other private background sounds. The vulnerability description also mentions that video might remain active, but does not confirm that behavior or explain what affected users would see on screen. Furthermore, it doesn't specify how long any continued transmission might last.

### Current Status 🔍
Currently, there are no known reports of exploitation in the wild. It is important to note that the vulnerability concerns only how a call is shut down. It does not involve stolen passwords, compromised accounts, or exposed message histories that would call for a password reset.

### Recommended Actions ⚠️
In response, the developers have updated the code to make shutdown more resilient when a call's internal queue is full or another termination step fails. Users are strongly advised to install any available Signal updates on their devices. While the fix is available in the underlying RingRTC library, the affected and first-fixed Signal app versions have not yet been confirmed publicly in the sources reviewed.

[Read full article](https://www.malwarebytes.com/blog/bugs/2026/10/signal-bug-could-let-someone-keep-listening-after-you-hang-up)