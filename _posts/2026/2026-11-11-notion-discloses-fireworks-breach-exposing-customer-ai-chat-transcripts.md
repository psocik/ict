---
title: Notion Discloses Fireworks Breach Exposing Customer AI Chat Transcripts
date: 2026-11-11
categories: [SECURITY]
tags: [NOTION,FIREWORKS,BREACH,SECURITY,AI]
---

## Notion Discloses Fireworks Breach Exposing Customer AI Chat Transcripts

Notion, the digital workspace platform, has revealed that a security breach at its AI infrastructure provider, Fireworks AI, has exposed customer AI chat transcripts in a small number of workspaces. 🚨 This disclosure follows Fireworks AI's confirmation that an attacker accessed its development environment via a third-party cloud provider on October 23, compromising resource metadata, billing information, model weights, and datasets for some customers.

Fireworks AI faced another breach in early October, when hackers accessed environment variables containing API keys and tokens stored as secrets for a limited number of accounts. 🔒 Notion learned about the exposed chat transcripts after receiving an alert from Fireworks on November 2 regarding an exposed dataset that contained only synthetic test data. In response, Notion acted swiftly by cutting off traffic to Fireworks, deleting all data from the vendor's systems, and halting training runs by November 3. However, Fireworks confirmed on November 8 that customer data had indeed been accessed, including that of Notion users.

Fireworks AI enables Notion to run some of the open-weight models available through Notion AI and analyze stored conversations for Insights, a feature that provides workspace administrators visibility into how their teams use AI. The exposed transcripts originated from the Insights dataset, which has now been disabled. Notion stated in an update, "Upon analysis of the dataset Fireworks AI provided us on November 8, we discovered that it included Notion AI chat transcripts used for the Insights feature, which for the vast majority of impacted workspaces were unattributable." This means the chats weren't labeled with who wrote them or which workspace they came from, and the transcripts did not contain tool call results.

Notion has also published a FAQ page about the incident, emphasizing that Fireworks had contractually committed to zero data retention for Notion data. 📄 According to the company, less than 1% of its users are impacted by the incident. Affected workspace owners should review the data through the Security incident review in Notion's desktop web interface and share a link with members that allows them to download their own transcripts. Notion advises affected users to rotate any passwords, API keys, or other credentials entered into affected chats. If neither a user nor their workspace owner has received a notice, Notion states that no action is needed for now, and they are most likely not part of the impacted subset.

[Read full article](https://www.bleepingcomputer.com/news/security/notion-says-fireworks-breach-exposed-customer-ai-chat-transcripts/)\n