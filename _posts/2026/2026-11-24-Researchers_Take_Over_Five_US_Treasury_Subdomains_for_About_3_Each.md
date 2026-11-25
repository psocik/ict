---
title: Researchers Take Over Five US Treasury Subdomains for About $3 Each
date: 2026-11-24
categories: [CYBERSECURITY]
tags: [CYBERSECURITY,US TREASURY,DNS RECORDS,AWS,PHISHING]
---

## Researchers Take Over Five US Treasury Subdomains for About $3 Each

Cybersecurity researchers at Intruder have taken control of five US Treasury subdomains for just about $3 each by claiming Amazon Web Services (AWS) IP addresses that the subdomains still pointed to. The researchers demonstrated their ability to publish their own content on the affected addresses. Importantly, Intruder did not report any access to Treasury's internal systems or theft of government data. 🚨

When an organization retires a cloud server, its DNS records can still direct visitors to the server's old IP address. If the cloud provider assigns that address to another customer, the new holder can serve content under the original subdomain. This leftover entry is known as a **dangling DNS record**. In its research report, Intruder tested whether AWS Elastic IP addresses matched live DNS records. Over 48 hours, the researchers checked about 450,000 unique IP addresses and found 28 matches, with nearly half belonging to government organizations. The five US Treasury subdomains that pointed to addresses controlled by Intruder are:
- ftp.treasury.gov
- pcp.treasury.gov
- ww5.treasury.gov
- rdgw.treasury.gov
- irssearch.treasury.gov

Someone who gains control of a government subdomain could host a **phishing page** on a genuine .gov address and obtain a valid HTTPS certificate. Intruder also warned that older automated systems could still send credentials to a retired address, and that cookies configured to be shared with subdomains could be exposed. The report described these as risks but did not document any credential or cookie theft. ⚠️

AWS blocked Intruder's account from claiming or using Elastic IP addresses after 48 hours of testing. According to Intruder, AWS stated on November 17 that it had no plans to make changes and maintained that customers are responsible for removing obsolete DNS records. Intruder notified the organizations affected by all 28 findings, and the DNS records were subsequently fixed. For organizations retiring cloud services, the practical step is to remove or update the DNS records before releasing the addresses they point to.

[Read full article](https://hackread.com/researchers-take-over-5-us-treasury-subdomains/) 