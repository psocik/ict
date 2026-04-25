---
title: Global analysis of Adversary-in-the-Middle phishing threats
date: 2025-06-11
categories: [RESEARCH]
tags: [PHISHING,CYBERSECURITY,AITM,MICROSOFT 365,GOOGLE ACCOUNTS]
---

## Introduction
In recent years, organisations have increasingly encountered massive and more sophisticated phishing attacks that primarily target Microsoft 365 and Google accounts using Adversary-in-the-Middle (AitM) technique. This growing trend has been amplified by the proliferation of Phishing-as-a-Service (PhaaS) offerings in the cybercrime ecosystem. These services provide access to advanced phishing kits for a wide range of cybercriminals, including those with limited technical skills, at a lower cost.

AitM phishing kits mainly aim to harvest session cookies from targeted services to bypass the Multi Factor Authentication (MFA) process during subsequent logins. To achieve this, AitM phishing servers relay user inputs, including usernames, passwords and MFA codes, to the legitimate authentication API while intercepting the returned session cookie. With that cookie, an attacker can replay the session and access the victim’s account without needing to perform any further authentication. Such compromises frequently lead to significant financial losses via Business Email Compromise (BEC) operations, financial fraud, or even Big Game Hunting ransomware attacks.

The Sekoia Threat Detection & Research (TDR) team closely monitors AitM phishing attacks and regularly provides technical reports on emerging kits that we uncover through our daily threat hunting routine. This global report delves into the threat posed by AitM phishing, offering both contextual and operational insights. Using our telemetry data and research findings, this report explores current trends in the AitM phishing landscape and the prevalence of leading kits.

[Read the complete article here](https://blog.sekoia.io/global-analysis-of-adversary-in-the-middle-phishing-threats/) 
