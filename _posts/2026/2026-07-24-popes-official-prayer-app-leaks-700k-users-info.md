---
title: Pope's Official Prayer App Leaks 700K+ Users' Info
date: 2026-07-24
categories: [SECURITY]
tags: [POPE,PRAYER APP,SECURITY,DATA BREACH]
---

## Major Data Breach Alert! 🚨

**Click To Pray**, a prayer app endorsed by the Pope, has committed a cardinal sin by leaking the personal information of over **700,000 users**! 😱 This alarming revelation comes from an ethical hacker who discovered the security vulnerability and reported it six months ago, but unfortunately, no action has been taken.

The app, which is available in **seven languages** and on various platforms including iOS and Android, is the official app of the Pope's Worldwide Prayer Network. As of July 2026, it boasts **719,517 registered accounts**. The hacker, known as **BobDaHacker**, revealed that the vulnerability is still active, stating, "Nobody has ever responded."

### What Went Wrong? 🤔

This security flaw stems from an **Insecure Direct Object Reference (IDOR)** bug, a common issue that allows unauthorized access to user data. BobDaHacker explained, "You ask for your own data, the server gives it to you. You ask for someone else's data, the server gives you that too."

When users sign up for Click To Pray, they are assigned a sequential numeric user ID. The API endpoint can return user data for any account as long as a valid user ID is provided, without any authorization checks. This means that an attacker could easily enumerate every single account on the platform with minimal effort.

### The Risks 🚨

The leaked data includes users' email addresses, names, countries, dates of birth, and account statuses. Many of these users are likely older individuals who may not be tech-savvy, making them prime targets for phishing attacks. Imagine receiving an email that says, "The Holy Father requests your urgent attention"—many would click on it without a second thought! 😟

Additionally, the signup endpoint exposes the account's validation hash, allowing anyone to sign up using any email address and verify the account before the confirmation message reaches the inbox. This further complicates the security landscape, as attackers could easily spoof emails that appear legitimate.

### Conclusion 📜

The Register reached out to the Pope's Worldwide Prayer Network but did not receive a response. This incident highlights the critical need for robust security measures in applications handling sensitive user data.

For more details, [Read full article](https://www.theregister.com/security/2026/07/24/popes-official-prayer-app-commits-cardinal-sin-leaks-700k-users-info/5278603)