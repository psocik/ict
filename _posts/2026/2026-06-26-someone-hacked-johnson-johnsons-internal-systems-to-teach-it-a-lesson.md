---
title: Someone Hacked Johnson & Johnson's Internal Systems to Teach It a Lesson
date: 2026-06-26
categories: [CYBERSECURITY]
tags: [HACKING,CYBERSECURITY,VULNERABILITIES,JOHNSON-AND-JOHNSON]
---

## Cybersecurity Incident 🚨

A cybersecurity researcher, known as Eaton, has uncovered serious vulnerabilities in Johnson & Johnson's (J&J) internal systems. This breach allowed access to sensitive recruiter tools, employee records, and even an internal audit management system used across various J&J businesses.

### Vulnerabilities Disclosed 🔍

Eaton disclosed two separate vulnerabilities affecting J&J's campus recruiting platform and the Audit Tracking Management System (ATMS). Both systems suffered from a critical flaw where authentication was primarily enforced on the frontend, while backend systems failed to verify user logins properly.

- **Campus Recruiting Platform:** Eaton found that by modifying Microsoft's Authentication Library (MSAL), he could unlock the recruiter interface. This access enabled him to create recruiting events, manage applicants, and view information on nearly 1,000 students, including recruiter notes and interview ratings. Eaton remarked, "The MSAL token was not actually used anywhere."

- **Audit Tracking Management System:** More alarmingly, Eaton accessed J&J's ATMS, which is crucial for managing compliance audits across about 20 companies within J&J's portfolio. Despite appearing secure behind Microsoft's SSO, Eaton discovered numerous exposed API endpoints. A request to an API named "getAllUsers" revealed information on approximately 13,600 J&J employees without requiring authentication. Eaton stated, "That was huge because it indicated all the APIs were unauthenticated."

### Disclosure and Response 📅

Eaton privately disclosed these vulnerabilities to J&J in October 2025 through their vulnerability reporting program. While the recruiting platform was fixed by the end of that month, the auditing system remained vulnerable for an extended period. After several follow-ups without updates, Eaton reached out to a journalist in April 2026, prompting J&J to finally address the issue. Eaton expressed his frustration, stating, "It was perplexing that it took press involvement to address what I believed was a serious internal data breach waiting to happen."

For more details, check out the full article here: [Read full article](https://cybernews.com/security/johnson-johnson-internal-system-hack/)