---
title: Robinhood Account Creation Flaw Abused to Send Phishing Emails
date: 2026-04-27
categories: [SECURITY]
tags: [ROBINHOOD,PHISHING,SECURITY,EMAIL]
---

## Robinhood Account Creation Flaw Abused to Send Phishing Emails 🚨

Online trading platform **Robinhood**'s account creation process was exploited by threat actors to inject phishing messages into legitimate emails, tricking users into believing their accounts had suspicious activity. Starting last night, Robinhood customers began receiving emails stating that an "Unrecognized Device Linked to Your Account" was detected, containing unusual IP addresses and partial phone numbers.

> "We detected a login attempt from a device that is not recognized," reads the phishing email. "If this was not you, please review your account activity immediately to secure your account."

Included in the email was a button titled **Review Activity Now**, which led to a phishing site at robinhood[.]casevaultreview[.]com. Screenshots on Reddit indicate that the site was likely used to try to steal Robinhood credentials.

### How the Attack Worked 🔍

Attackers abused Robinhood to generate phishing emails by exploiting a flaw in the company's onboarding process that allowed them to inject arbitrary HTML into its account confirmation emails. BleepingComputer confirmed that when a new Robinhood account is registered, the company automatically sends a **Your recent login to Robinhood** email to the associated address, containing the registration time, IP address, device information, and approximate location.

To inject the phishing message, threat actors modified their device metadata fields to include embedded HTML, which Robinhood did not properly sanitize. This HTML was then injected into the Device: field of the account creation email, causing it to render as a fake **Unrecognized Device Linked to Your Account** message.

### Customer Impact 📉

To target Robinhood customers, attackers likely used lists of known customer email addresses from previous data breaches. In November 2021, Robinhood suffered a data breach impacting 7 million customers, with the data later offered for sale on a hacking forum. The attackers also used Gmail's dot aliasing behavior, where adding periods to an address does not change its destination, allowing them to register accounts using variations of real email addresses while still delivering the messages to the intended recipients.

### Robinhood's Response 🛡️

Robinhood confirmed the incident in a statement posted to X. "On Sunday evening, some customers received a falsified email from noreply@robinhood.com with the subject line 'Your recent login to Robinhood.'" The company stated: "This phishing attempt was made possible by an abuse of the account creation flow. It was not a breach of our systems or customer accounts, and personal information and funds were not impacted."

BleepingComputer has confirmed that Robinhood has fixed this flaw by removing the Device: field that was previously abused from their account creation emails. Robinhood advises users who received the message to delete it and avoid clicking any links.

[Read full article](https://www.bleepingcomputer.com/news/security/robinhood-account-creation-flaw-abused-to-send-phishing-emails/)