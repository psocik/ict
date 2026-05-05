---
title: Wiz ZeroDay.Cloud Event Reveals 20-Year-Old PostgreSQL Vulnerabilities
date: 2026-05-04
categories: [CYBERSECURITY]
tags: [POSTGRESQL,VULNERABILITIES,CYBERSECURITY,HACKERS,CLOUD]
---

## Wiz ZeroDay.Cloud Event Reveals 20-Year-Old PostgreSQL Vulnerabilities 🚀

Cybersecurity researchers participating in Wiz's ZeroDay.Cloud hacking event in London, England, exploited two critical vulnerabilities in PostgreSQL, the database that runs behind countless enterprise applications. The event took place in December 2025, but details were only released on May 4, 2026. These vulnerabilities, tracked as CVE-2026-2005 and CVE-2026-2006, date back to 2005 and remained unnoticed in the pgcrypto extension, a standard tool for encryption tasks that's considered safe by default.

Wiz ran the numbers after the findings and saw PostgreSQL in 80% of cloud environments they scanned, with 45% of those instances open to the public internet. That setup turns a database login into direct access.

According to Wiz's technical blog post shared with Hackread.com, addressing the CVE-2026-2005 vulnerability explained that it hits a function called `pgp_parse_pubenc_sesskey` during public-key decryption in pgcrypto. Attackers send it a crafted PGP message that tricks the code into copying too many bytes into a fixed-size buffer, spilling over into heap memory. From there, a user with basic create privileges loads the extension and chains leaks, writes, and privilege jumps to run commands as the database owner.

The second report on CVE-2026-2006 describes a similar flaw in symmetric decryption via `pgp_sym_decrypt`. Without proper checks, malformed UTF-8 slips through PostgreSQL's string handlers like `pg_mblen` and `pg_utf_mblen`, leading to out-of-bounds reads or writes. Attackers can use this to corrupt memory and gain control over execution, including hijacking settings like `search_path` to trigger system calls. Additionally, Team Xint Code spotted a third issue in MariaDB, assigned CVE-2026-32710. This heap buffer overflow in the `JSON_SCHEMA_VALID` function lets any logged-in user hit it with one SQL query and potentially run code or crash the server.

PostgreSQL patched both flaws across its main branches, from 14.21 up to 18.2, with commits in early February and releases by the 12th. MariaDB fixed the issue in the 11.4.10 and 11.8.6 versions on February 4, 2026. Database administrators should apply updates immediately, restrict extension creation, and audit logs for suspicious pgp or JSON activity.

[Read full article](https://hackread.com/wiz-zeroday-cloud-event-postgresql-vulnerabilities/)