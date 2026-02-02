---
title: Phishing kits adapt to the script of callers
date: 2026-01-30
categories: [SECURITY]
tags: [PHISHING,CYBERSECURITY,VISHING,MFA]
---

Okta Threat Intelligence has detected and dissected multiple custom phishing kits that have evolved to meet the specific needs of voice-based social engineers (“callers”) in vishing campaigns. These kits are available as a service and are used by various intrusion actors targeting major platforms such as Google, Microsoft, and Okta, as well as numerous cryptocurrency providers. 

The kits can intercept user credentials while also providing the necessary context for users to approve multi-factor authentication (MFA) challenges, or to take other actions beneficial to the attacker. Notably, they can be adjusted in real-time by callers to manage what pages are shown in a user’s browser, synchronizing with the caller's script and MFA prompts presented to users.

Key features include client-side scripts that enable threat actors to control the authentication flow on the victim's browser dynamically, responding to verbal feedback. This orchestration is crucial in persuading users to approve push notifications or submit one-time passcodes (OTP) necessary to bypass MFA controls. As stated by Moussa Diallo, a threat researcher at Okta, using these kits allows an attacker to control what a user sees in their browser during a phone call, which can outpace many forms of MFA that aren't phishing-resistant.

The attack sequence typically involves:
1. The attacker performing reconnaissance on the target, gathering user names, applications used, and IT support phone numbers.
2. Setting a tailored phishing page live, then spoofing the company or its support hotline while calling the target.
3. Convincing the user to navigate to the phishing site under the guise of IT support requirements.
4. The targeted user entering their credentials, which are immediately sent to the attacker’s Telegram channel.
5. The attacker logging into the valid portal with the victim's credentials and obtaining any displayed MFA challenges.
6. Updating the phishing site to ask the victim for an OTP, push notification acceptance, or other challenges in real-time.

Diallo noted that the demand for expertise in vishing is growing, which is becoming increasingly commercialized like these kits. Users employing phishing-resistant methods, such as Okta FastPass or FIDO passkeys, are shielded from these attacks. Working environments should enforce phishing-resistance protocols to safeguard resource access. Diallo advises ensuring that network access is restricted only to legitimate requests.