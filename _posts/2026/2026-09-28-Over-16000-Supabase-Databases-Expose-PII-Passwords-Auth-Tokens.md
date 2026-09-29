---
title: Over 16,000 Supabase Databases Expose PII, Passwords, Auth Tokens
date: 2026-09-28
categories: [SECURITY]
tags: [SUPABASE,DATA-EXPOSURE,SECURITY,PRIVACY]
---

## Over 16,000 Supabase Databases Expose PII, Passwords, Auth Tokens 🚨

Researchers have discovered that over 16,000 misconfigured Supabase databases are exposing readable tables containing personally identifiable information (PII), passwords, and authentication tokens. Supabase, an open-source development platform built around PostgreSQL, offers developers a range of backend services to accelerate app and website development.

### Key Findings 🔍
- **Exposed Information:** A small subset of the exposed data includes credit card information.
- **Popularity Among Developers:** The platform has gained traction, especially among developers utilizing AI tools, with AI-assisted development accounting for over 60% of newly created databases.
- **Diverse Impact:** The exposures have affected various services, including:
  - A U.S. valet service with over 100,000 customer records, including contact details and license plates.
  - A Canadian immigration service with nearly 5,000 user records, including 884 plaintext passwords.
  - An India-based adult creator platform revealing sensitive identity and payment accounts, along with over 100,000 private messages.
  - A Philippines-based OTP service exposing data on over 2,000 users and 100,000 SMS messages.
  - An African government consulate with records of 25,000 individuals, including addresses and emergency housing locations.

### Causes of Exposure ⚠️
The researchers attribute these exposures to poor application security configurations, such as ineffective row-level security policies and misuse of public keys. They emphasize that the security issues are not confined to specific business types, as the common thread is the lack of understanding of database configurations by developers, particularly those using AI coding agents.

Despite the increased risk associated with AI-assisted app development, the researchers clarified that their scans do not confirm that every affected site was built using AI coding agents. UpGuard has notified application owners when significant exposures were identified.

For more details, [Read full article](https://www.bleepingcomputer.com/news/security/misconfigured-supabase-apps-expose-data-in-over-16-000-databases/).