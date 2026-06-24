---
title: Meta Pauses Controversial Employee-Tracking Program After Security Review
date: 2026-06-23
categories: [TECHNOLOGY]
tags: [META,EMPLOYEE TRACKING,SECURITY,PRIVACY]
---

## Meta Pauses Controversial Employee-Tracking Program 🚫

Meta has paused a controversial employee-tracking program after an internal security review revealed that highly granular keystroke and screen-capture data from staff laptops was far more widely accessible within the company than intended. This program was part of Meta's Model Capability Initiative (MCI), which collected mouse movements, click locations, keystrokes, and screen content from employees' work laptops to help train internal AI systems.

According to reports based on internal documents and employee accounts, the data wasn't just collected; it was left accessible across thousands of internal data tables, including AI prompts, transcriptions, private conversations, and performance-related information. Following coverage of this exposure, Meta scaled back and ultimately paused the initiative amid sustained internal backlash and questions about whether privacy protections were ever more than a reassurance in a memo.

From Meta's perspective, the Model Capability Initiative was an efficiency play. The goal was to provide AI models with "real examples of how people actually use computers" by passively logging how employees navigate everyday tools like Gmail, GChat, Metamate, and VS Code. Keystroke and mouse-tracking software was pushed to US workers' laptops, with no option to opt out on company devices, as confirmed internally by Meta's CTO. The software captured inputs plus associated screen content, creating a behavioral dataset: what you type, where you click, and what is on your screen while you do it.

The program prompted significant internal criticism, with an engineer's internal post protesting "laptop surveillance" and screen monitoring going viral inside Meta, sparking a petition to kill the program entirely.

Collecting highly sensitive employee activity data introduces an obvious risk, and keeping it properly secured is another challenge. Keystroke and screenshot data is high-risk by design. That type of data is content-rich, behavioral, and often contains secrets. Collecting it at scale creates a security burden. Every new data point adds obligations around access control, minimization, retention, and audit that the organization must actively manage for as long as the data exists. Access controls must be precise and regularly audited, because a simple misconfiguration can have big consequences. Data minimization and retention limits are essential since long-term storage multiplies the impact of a potential breach. Any future data leak—internal or external—could expose not just emails, but the exact sequences employees type, including authentication flows and draft content. In the wrong hands, this kind of information could expose the company to compromise. This episode serves as a reminder that every new dataset creates new responsibilities. The more detailed and sensitive the information, the greater the consequences when access controls fail.

[Read full article](https://www.malwarebytes.com/blog/news/2026/06/meta-pauses-controversial-employee-tracking-program-after-security-review)