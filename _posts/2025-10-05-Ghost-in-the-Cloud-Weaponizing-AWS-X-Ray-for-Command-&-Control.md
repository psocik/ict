---
title: Ghost in the Cloud Weaponizing AWS X-Ray for Command & Control
date: 2025-10-05
categories: [SECURITY]
tags: [AWS,SECURITY,CYBERSECURITY]
---

Attackers can weaponize AWS X-Ray as a covert bidirectional C2 channel, abusing legitimate cloud tracing infrastructure for C2.\n\nAWS X-Ray was designed to help developers to understand application performance by collecting traces. However, X-Ray annotations can store arbitrary key-value data, and the service provides APIs to both write and query this data.\n\nRandom beacon interval happens between 30–60 seconds. The implant implements custom AWS SigV4 authentication manually. In addition to this API request to X-Ray must be signed using HMAC-SHA256 with the access key and secret, following Amazon’s specific canonical request format which creates legitimate AWS API traffic that would gel up with regular network logs.\n\nTo read the complete article see: [Security Affairs](https://securityaffairs.com/182968/hacking/ghost-in-the-cloud-weaponizing-aws-x-ray-for-command-control.html)\n