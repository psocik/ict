---
title: Popa Botnet Linked to Publicly-Traded Israeli Firm
date: 2026-06-18
categories: [CYBERSECURITY]
tags: [POPA,BOTNET,MALWARE,ISRAEL,NETNUT]
---

## Popa Botnet Linked to Publicly-Traded Israeli Firm

🚨 For the past four years, a sprawling Android-based botnet called **Popa** has forced millions of consumer TV boxes to relay Internet traffic linked to advertising fraud, account takeovers, and mass data-scraping efforts. This week, researchers from multiple security firms concluded that the Popa botnet is linked to **NetNut**, a "residential proxy" provider operated by the publicly-traded Israeli firm **Alarum Technologies Ltd** [NASDAQ: ALAR].

Popa is a massive botnet, but by all accounts, it is unlike traditional botnets that enlist compromised systems in destructive activities, such as coordinating huge distributed denial-of-service attacks. Rather, Popa appears designed with a singular purpose: implementing a persistent communications layer capable of registering a device, maintaining long-lived encrypted connections, and opening communication tunnels on demand.

### Insights from Experts

Experts say Popa is a plugin component associated with the **Vo1d** botnet, a large-scale malware campaign targeting unofficial Android-based TV boxes. These streaming boxes typically bundle or come pre-installed with software that turns the user's TV into a "residential proxy."

The first clues about Popa's origins came in a 2025 report from the Chinese security company **XLAB**. In a report released today, the security firm **Qurium** described how it stumbled on some of those same domains while investigating a series of disruptive and expensive data scraping events targeting the company's hosted organizations in May 2026, in which the scraping activity was scattered evenly across more than 1.4 million Internet addresses.

Qurium said it found several dozen domains used to control Popa, including [REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]. Qurium's report notes that most of the domains long used to control the Popa botnet were seized or dismantled in July 2025, after Google, HUMAN Security, and Trend Micro teamed up to disrupt **Badbox 2.0**. Immediately after that disruption, several dozen new domains were registered to serve as controllers for the Popa botnet, but one control domain was not new: [REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].

### Company Background

**Ninjatech** is a company founded by **Moishi Kramer**, whose LinkedIn profile says he is vice president of research and development at NetNut. That resume credits Kramer for helping NetNut to build from the "ground up," "designing the architecture," and "scaling the NetNut" before the company was acquired by Alarum Technologies.

Responding via email, Mr. Kramer said Ninjatech ceased operations approximately five years ago when the company sold a software development kit (SDK) called Popa that was designed to use a small portion of a device's bandwidth and to run only after the host application obtained user consent. "That code was sold and licensed to third parties including resellers years ago," Kramer said. "Once software is distributed that way, the original developer has no control over how others later modify, rebrand, or deploy it." Kramer also stated, "I have no control over, or visibility into, that infrastructure. I can only tell you it isn't operated by me or by NetNut."

### Recent Findings

However, in a separate Popa research report released today, the proxy-tracking company **Synthient** said a recent analysis of the Popa SDK revealed outbound traffic clearly associated with NetNut. "The research team assesses with high confidence that devices running Popa forward traffic from Netnut clients," Synthient wrote. "This proves without a shadow of a doubt that Popa actively continues to be used by NetNut as part of their proxy pool."

**Alarum Technologies**, NetNut's parent company, said the reports by Synthient and Qurium contained "demonstrably inaccurate assertions and flawed deductions rather than verified facts." Alarum shared a statement saying they reject the basic characterization of the SDKs and technologies discussed in the reports as a "botnet." "The SDKs at issue are designed to facilitate bandwidth-sharing functionality and do not transform user devices into malware-controlled systems or otherwise compromise the devices on which they operate," the statement reads.

To read the complete article see: [Read full article](https://krebsonsecurity.com/2026/06/popa-botnet-linked-to-publicly-traded-israeli-firm/)