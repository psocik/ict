---
title: How Often Are Redirects Used in Phishing in 2026?
date: 2026-04-06
categories: [CYBERSECURITY]
tags: [PHISHING,REDIRECTS,CYBERSECURITY,VULNERABILITIES]
---

## How Often Are Redirects Used in Phishing in 2026?

**Published on:** April 6, 2026  
**Source:** SANS ISC  

Although open redirects are not generally considered a high-impact vulnerability on their own, they can have multiple negative implications. One significant misuse case is phishing. The reason is straightforward: links pointing to legitimate domains (like [google.com](https://www.google.com)) included in phishing messages may appear benign to recipients and can evade simpler email scanners and other detection mechanisms. 

Even though open redirects have not been listed in the OWASP Top 10 for quite some time, it is clear that attackers have never stopped looking for and using them. Hardly a month goes by without attempts to identify potentially vulnerable endpoints. We continue to see open redirects used in phishing campaigns. Last year, I wrote about a campaign using a "half-open" (i.e., easily abusable) redirect mechanism on Google, and similar cases still appear regularly. 

To find out how often redirects are used, I reviewed phishing emails collected through my own filters and spam traps, as well as samples sent to us here at the ISC over the first quarter of this year. Although the total sample consisted of slightly more than 350 individual messages (and is therefore far from statistically representative), it still provided quite interesting results. Redirect-based phishing accounted for a little over **21%** of all analyzed messages sent out over the first 3 months of 2026 - specifically **32%** in January, **18%** in February, and **16.5%** in March. 

It should be noted that if a message contained multiple malicious links and at least one of them used a redirect, the entire message was counted exclusively as a redirect sample. Not all redirect cases were classic "open redirects." In fact, the abused redirect mechanisms varied widely. Some behaved similarly to the aforementioned Google-style "half-open" redirects, while others were fully open. In some cases, the redirectors were part of tracking or advertising systems, while in others, they were implemented as logout endpoints or similar mechanisms. URL shorteners were also counted as redirectors. 

The Google-style redirects are not fully open. They do require a specific valid token to work; however, since these tokens are typically reusable, have a very long lifetime, and are not tied to any specific context (such as IP address or session), they can be - and are - readily reused in phishing campaigns. Similar redirect mechanisms on other platforms (e.g., Bing) are also being abused in the same way. 

As we can see, although open redirects are commonly considered more of a nuisance issue than an actual high-risk vulnerability these days, it doesn't prevent malicious actors from misusing them quite heavily. At the very least, it is worth ensuring that our own applications do not expose endpoints that can be misused in this way. Where any redirection functionality is strictly required, it should be monitored for abuse and restricted as necessary. 

[Read full article](https://isc.sans.edu/forums/diary/How%20often%20are%20redirects%20used%20in%20phishing%20in%202026%3F/32870/)