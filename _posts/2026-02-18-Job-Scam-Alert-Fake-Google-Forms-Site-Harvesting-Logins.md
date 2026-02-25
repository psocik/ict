---
title: Job Scam Alert Fake Google Forms Site Harvesting Logins
date: 2026-02-18
categories: [SECURITY]
tags: [JOB SCAM,PHISHING,GOOGLE FORMS,CYBERSECURITY]
---

## Job Scam Alert 🚨

A recent investigation by **Malwarebytes Labs** has uncovered a job-themed phishing campaign that utilizes a fake Google Forms site to harvest Google logins. The suspicious URLs resemble legitimate Google Forms, but they are designed to deceive users.

### What We Found 🔍

The URLs in question include `https://forms.google.ss-o[.]com/forms/d/e/{unique_id}/viewform?form=opportunitysec&promo=`. The subdomain `forms.google.ss-o[.]com` is a clear attempt to impersonate the legitimate `forms.google.com`. The “ss-o” is likely a trick to mimic “single sign-on,” which allows users to log in securely across multiple platforms.

When researchers attempted to visit these URLs, they were redirected to a local Google search page, a common tactic used by phishers to prevent sharing of personalized links.

### The Phishing Mechanism 🛠️

Further investigation revealed a file named `generation_form.php` on the same domain, which was used to create personalized links for victims. The landing page promised a job opportunity for a **Customer Support Executive (International Process)**, asking for personal details like Full Name and Email address.

Clicking the “Sign in” button directed users to `https://id-v4[.]com/generation.php`, which has since been taken down. This domain has been linked to several phishing campaigns over the past year.

### Stay Safe! 🛡️

To protect yourself from such scams, avoid clicking on links in unsolicited job offers. Consider using a password manager to prevent auto-filling credentials on fake websites. Additionally, ensure you have an up-to-date anti-malware solution with web protection.

### Indicators of Compromise (IOCs) 📊

- `id-v4[.]com`
- `forms.google.ss-o[.]com`

For more detailed information, you can read the complete article here: [Read full article](https://www.malwarebytes.com/blog/scams/2026/02/job-scam-uses-fake-google-forms-site-to-harvest-google-logins)