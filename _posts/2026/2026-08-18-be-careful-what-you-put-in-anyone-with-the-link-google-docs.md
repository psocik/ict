---
title: Be Careful What You Put in 'Anyone with the Link' Google Docs
date: 2026-08-18
categories: [SECURITY]
tags: [GOOGLE,DOCS,SECURITY,BREACH,SENSITIVE INFORMATION]
---

## Be Careful What You Put in 'Anyone with the Link' Google Docs

The next time you type something sensitive into a Google Doc—or any other online tool with a sharing feature—be careful about the permissions you grant. Siim Kostabi, founder of QR generation service Pageloot, recalled how a contractor working for the company accidentally exposed login details for its staging environment—credentials that were never meant to leave an internal testing setup. The developer stored the login details in a Google Doc and then set it to "anyone with the link can view." It turns out Google Search can index Google Docs with that setting if the link becomes discoverable on the public web. What we do know is that it did: The credentials file ended up in Google Search. Google Search was surfacing information from a document that had been shared too widely.  

To its credit, Pageloot moved quickly. It cut the contractor's access and changed every affected credential. It also banned password storage in Google Docs, Slack, Notion, and any other shared workspace. If nobody had spotted it, the credentials could have remained exposed.  

Pageloot isn't alone in dealing with this problem. Ateam, a Japanese Android game developer, left a Google Drive instance set to "Anyone on the internet with the link can view" from March 2017 until November 2023. That single misconfiguration exposed 1,369 files and personal data for 935,779 people. Ateam said it had seen no evidence anything was taken, though seven years of open access is hardly reassuring. Scale AI, the data-labeling company central to Meta's AI ambitions, also left 85 Google Docs with training material for Meta, Google, and xAI editable to anyone with a link.  

This is a trend. Three years ago, AI security company Metomic scanned approximately 6.5 million Google Drive files and found that 40.2% contained sensitive information. Just over a third were shared externally, while 0.5% were fully public. That 0.5% might not sound like a lot, but across 6.5 million files, it still represents thousands of publicly accessible files. This isn't just a Google problem, though. People accidentally share sensitive information through other tools too, like the Trello project management system. Making a Trello board public makes it viewable to everyone, which was unfortunate for government users when they exposed passwords and security plans that way in 2018. Verizon's 2025 Data Breach Investigations Report attributes around 60% of breaches to human factors including misconfiguration and misuse of valid credentials.  

Consumers can take a few simple precautions too. Don't store passwords or other highly sensitive information in ordinary shared documents. Use a password manager for passwords, and before hitting Share in any online service, check exactly who will be able to access what you're sharing. Kostabi learned his lesson, which is to keep an eye on who has access to what.  

[Read full article](https://www.malwarebytes.com/blog/news/2026/08/be-careful-what-you-put-in-anyone-with-the-link-google-docs)