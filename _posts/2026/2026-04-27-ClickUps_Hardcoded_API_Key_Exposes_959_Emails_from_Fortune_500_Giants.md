---
title: ClickUp's Hardcoded API Key Exposes 959 Emails from Fortune 500 Giants
date: 2026-04-27
categories: [CYBERSECURITY]
tags: [CLICKUP,API,SECURITY,DATA_BREACH,EMAILS]
---

## ClickUp's Hardcoded API Key Exposes 959 Emails from Fortune 500 Giants 🚨

A publicly accessible JavaScript file on ClickUp's homepage has been silently leaking nearly a thousand corporate and government email addresses, including employees from **Fortinet**, **Home Depot**, **Tenable**, **Mayo Clinic**, and U.S. state government workers. This exposure is due to a hardcoded third-party API key that was first reported in January 2025 and remains unrotated as of April 2026.

The vulnerability was uncovered by a security researcher who inspected the page source and found a hardcoded API key embedded directly in a JavaScript file, which loads before any user authentication takes place. A single unauthenticated GET request using the key returned **959 email addresses** and **3,165 internal feature flags**, requiring no credentials, no bypass, and no sophisticated tooling whatsoever.

The leaked data spans an alarming cross-section of the enterprise and government landscape, including employees from **Home Depot**, **Fortinet**, **Autodesk**, **Tenable**, **Rakuten**, **Mayo Clinic**, **Permira**, and law firm **Akin Gump**, alongside government workers from **Wyoming**, **Arkansas**, **North Carolina**, **Montana**, **Queensland (Australia)**, and **New Zealand**, plus a Microsoft contractor and **71 ClickUp employees**. This exposure creates a direct attack surface for targeted phishing, credential stuffing, and social engineering campaigns against the very companies tasked with defending others.

The **3,165 internal feature flags** leaked alongside the emails are equally concerning, revealing internal product development signals, beta features, and A/B testing configurations that could aid competitive intelligence or facilitate targeted platform abuse. The vulnerability was first reported to ClickUp via HackerOne on **January 17, 2025**. As of late April 2026, more than **15 months later**, the API key had not been rotated. The researcher confirmed the data was still live, having pulled the full response minutes before the disclosure went public.

This is not a zero-day; it is an unpatched known vulnerability sitting in production, quietly harvesting enterprise PII for over a year. Hardcoded secrets in client-side JavaScript remain one of the most well-documented and preventable vulnerability classes in modern web development, making this lapse all the more difficult to justify at ClickUp's scale and security posture expectations. ClickUp has not publicly acknowledged the ongoing exposure at the time of publication.

[Read full article](https://cybersecuritynews.com/clickup-hardcoded-api-key-expose/)