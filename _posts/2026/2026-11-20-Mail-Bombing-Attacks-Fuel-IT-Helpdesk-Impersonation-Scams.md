---
title: Mail Bombing Attacks Fuel IT Helpdesk Impersonation Scams
date: 2026-11-20
categories: [CYBERSECURITY]
tags: [MAIL BOMBING,IMPERSONATION SCAMS,CYBERSECURITY,PHISHING]
---

## Mail Bombing Attacks Fuel IT Helpdesk Impersonation Scams 🚨

Cybercriminals are conducting large-scale **mail bombing attacks**, followed by IT helpdesk impersonation to compromise user accounts. Fortra Intelligence and Research Experts (FIRE) are tracking this campaign, which involves inboxes being deliberately flooded with emails.

In an update on the campaign published by FIRE on November 19, the researchers noted that mail bombing does not require access to a target mailbox. Instead, a target's inbox is flooded with subscriptions after an attacker submits a target email address to newsletter, registration, and other signup forms across unrelated websites. This email flood can disrupt activities like customer service and routine correspondence, obscuring account alerts, payment notifications, and other important messages that may require attention.

FIRE indicated that these attacks are likely an **AI Agent setup**, where the agent is instructed to crawl every webpage available for newsletter subscription boxes. Mailchimp and its transactional service, Mandrill, were the most frequently observed delivery services, followed by Amazon SES and SendGrid. "In the attacks observed so far by the FIRE team, the average email delivery of a mail bombing attack peaks at 10k messages per active campaign, around 1k emails per day," Fortra stated.

Additionally, FIRE has detected phishing attempts during these mail-bombing waves, which are harder to identify among the flood of otherwise legitimate emails. The mail bombing campaign has been followed by **vishing calls**, where threat actors contact victims through Teams, claiming to be representatives from Internal IT. They provide users with verbal and email instructions that they claim will stop the flood, but in reality, they aim to compromise the user account or system.

Fortra emphasized that these mail bombing campaigns can be difficult to detect because individual subscription emails can appear entirely normal and may not contain malicious links. Allowlist exceptions can complicate containment when they cover delivery platforms carrying the flood. Fortra recommends that security teams monitor email volume per recipient against the normal baseline and investigate bursts involving many unrelated senders, subscription wording, and mailing-list headers. During FIRE's investigation, Mailchimp advised that senders could request temporary subscription blocking for a specified recipient. Mailchimp also documents a separate automatic control that restricts an address from joining additional audiences for 24 hours after rapid repeat.

[Read full article](https://www.infosecurity-magazine.com/news/mail-bombing-attacks-it-helpdesk/)  
