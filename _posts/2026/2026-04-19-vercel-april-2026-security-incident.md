---
title: Vercel April 2026 Security Incident
date: 2026-04-19
categories: [SECURITY]
tags: [VERCEL,SECURITY,INCIDENT,GOOGLE,WORKSPACE]
---

## Vercel April 2026 Security Incident 🚨

Vercel has identified a security incident that involved unauthorized access to certain internal Vercel systems. The company is actively investigating and has engaged incident response experts to help investigate and remediate. Vercel has notified law enforcement and will update its status page as the investigation progresses. At this time, a limited subset of customers have been identified as impacted, and Vercel is engaging with them directly. Vercel services remain operational, and the company is taking actions to protect Vercel systems and customers. The investigation is ongoing.

### Origin of the Incident 🔍

The investigation has revealed that the incident originated from a small, third-party AI tool whose Google Workspace OAuth app was the subject of a broader compromise, potentially affecting its hundreds of users across many organizations. To support the wider community in the investigation and vetting of potential malicious activity in their environments, Vercel is publishing the following Indicator of Compromise (IOC). Vercel recommends that Google Workspace Administrators and Google Account owners check for usage of this app immediately. The specific OAuth App identified is: `110671459871-30f1spbu0hptbs60cb4vsmv79i7bbvqj.apps.googleusercontent.com`.

### Best Practices for Users 🛡️

In the meantime, Vercel suggests several best practices for peace of mind. Users should review the activity log for their account and environments for suspicious activity, which can be done in the dashboard or via the CLI. It is also critical to review and rotate environment variables. Environment variables marked as "sensitive" in Vercel are stored in a manner that prevents them from being read, and Vercel currently does not have evidence that those values were accessed. However, if any of your environment variables contain secrets (API keys, tokens, database credentials, signing keys) that were not marked as sensitive, those values should be treated as potentially exposed and rotated as a priority. Vercel further recommends taking advantage of the sensitive environment variables feature going forward, so that secret values are protected from being read in the future.

[Read full article](https://vercel.com/kb/bulletin/vercel-april-2026-security-incident)