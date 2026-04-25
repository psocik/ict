---
title: Researchers Say Fiverr Left User Files Open to Google Search
date: 2026-04-16
categories: [CYBERSECURITY]
tags: [FIVERR,DATA BREACH,CYBERSECURITY,PRIVACY,CLOUDINARY]
---

## Researchers Say Fiverr Left User Files Open to Google Search

A security researcher named **Morpheuskafka** has found that thousands of private files from the Tel Aviv-based gig-work website **Fiverr** were left open for anyone to view online. The leaked data allegedly includes very sensitive items like tax forms, photos of driving licenses, and work contracts. These documents were not stored on a private, restricted server but were actually indexed and appeared in Google search results. 🚨

Fiverr uses a third-party service called **Cloudinary** to manage and store the images and PDFs that users send to each other. Instead of using signed or expiring URLs that only authorized users could open, the platform used public URLs. Since some of these links were placed on public pages, search engines were able to crawl and list them, which is why a simple search could bring up a user's personally identifiable information (PII). The types of data found include:
- Official ID cards and driving licenses
- Private work deliverables and contracts
- Passwords and API keys used for software
- Tax records and invoices containing physical addresses

Morpheuskafka first spotted the problem and notified Fiverr's security team via email around 40 days before making the news public, but the company didn't reply. Fiverr has categorically denied the claim, stating that this is not a cyberattack or a security incident because users gave their permission for these files to be shared as part of their work. A spokesperson for the firm said: "Fiverr does not proactively expose users' private information. The content in question was shared by users in the normal course of marketplace activity to showcase work samples, under agreements and approvals between buyers and sellers." However, cybersecurity experts disagree with this view, arguing that even if a user agrees to share a file with one client, it does not mean they want it to be public for everyone to find. Experts suggest that anyone who has shared their ID or tax forms on the site should monitor their accounts for signs of identity theft. It is also a good idea to change any login credentials that were sent through the platform's messaging system. 🔒

David Stuart, Cybersecurity Evangelist at **Sentra**, explained that this situation is a classic example of how sensitive data can spread and be handled incorrectly. He stated: "Fiverr's incident is a textbook case of sensitive data sprawl and misconfigured third-party infrastructure: highly sensitive documents (including tax returns, IDs, health records, and even admin credentials) were stored on Cloudinary behind unauthenticated, non-expiring URLs, then surfaced via public HTML so Google could index them, remaining accessible for weeks after initial disclosure and hours after public reporting." According to Stuart, the issue was not a complex hack but a simple failure to use the right safety settings. He added that security teams must be able to: 
- Identify when business workflows push regulated content into the wrong systems
- Prioritize remediation before search engines or adversaries find it
- Demonstrate that these risks are being monitored continuously as data environments expand. 📊

To read the complete article see: [Read full article](https://hackread.com/fiverr-left-user-files-open-to-google-search/)