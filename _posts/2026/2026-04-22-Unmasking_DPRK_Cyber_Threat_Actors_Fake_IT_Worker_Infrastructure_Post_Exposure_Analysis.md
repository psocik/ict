---
title: Unmasking DPRK Cyber Threat Actors Fake IT Worker Infrastructure & Post-Exposure Analysis
date: 2026-04-22
categories: [CYBERSECURITY]
tags: [DPRK,CYBERSECURITY,VPN,THREAT-ACTORS,INFRASTRUCTURE]
---

## Unmasking DPRK Cyber Threat Actors: Fake IT Worker Infrastructure & Post-Exposure Analysis

This investigation was initiated after reporting by cryptocurrency security researcher **ZachXBT**, who identified the domain luckyguys[.]site as being linked to payments associated with DPRK-linked fake IT workers. At the time of analysis, the domain resolved to [IP REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS], and this report examines 30 days of network activity associated with that infrastructure. ZachXBT has an established track record of uncovering illicit financial activity within the cryptocurrency ecosystem, with prior disclosures frequently correlating with subsequent law enforcement action. As such, infrastructure identified in his reporting warrants heightened scrutiny. 🚨

### Key Findings
- Analysis of VPN-related connections to the identified IP revealed a highly concentrated usage pattern: **Astrill VPN** at 37.5%, **Mullvad** at 32.25%, and **Proton VPN** at 6.25%. The prominence of Astrill VPN is notable, as it has been repeatedly associated with DPRK IT worker activity in prior reporting by organizations such as GitLab and Flare.io.
- Temporal analysis further showed that traffic to the IP dropped off sharply following public exposure on April 8. This pattern is consistent with known threat actor behavior, where infrastructure is rapidly abandoned once publicly attributed.

### Observations
American and Latvian residential IP addresses were observed communicating with the infrastructure during the analysis period. Netflow analysis of these IPs revealed frequent use of Astrill VPN and connectivity to cloud services associated with **Gmail**, **ChatGPT**, and **Workana**. The use of ChatGPT aligns with recent findings from Group-IB, which reported DPRK-linked IT workers leveraging AI tools to assist with development tasks and communication. Workana, a freelance platform focused on remote talent, appears prominently in the observed network activity. This observation is further supported by prior research from Nisos, which documented DPRK-affiliated operators maintaining freelancer profiles on platforms like Workana to obtain remote employment under false identities.

### Conclusion
Additionally, analysis of other X509 certificates with the name [REDACTED ALSO - sorry!] found a second IP, [IP ALSO REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS], that was not part of any previous reporting. This IP also demonstrated a significant drop in traffic after the publication of the report by ZachXBT and aligned with the threat actor abandoning infrastructure post-attribution. The combined network telemetry, VPN usage patterns, and residential IP distribution strongly suggest a distributed network of remote IT workers or facilitators, likely use of home-based systems or "laptop farms," active participation in sanctions evasion workflows, and operational overlap with known DPRK fake IT worker tradecraft. The rapid cessation of activity following public exposure reinforces attribution confidence and indicates adversary sensitivity to visibility. 🔍

### Recommendations
Organizations should take the following into account:
- Residential IP addresses are not inherently trustworthy and may be part of proxy or laundering networks.
- VPN overlap—particularly with providers previously linked to DPRK activity—should be treated as a risk signal.
- Freelance hiring pipelines (especially via global platforms) represent a key infiltration vector.
- Monitoring for behavioral patterns, not just indicators, is critical for detection.
- Identify any network traffic connecting (including corporate machines) connecting to the IP's [IP REDACTED] and [IP REDACTED]. Special caution should be applied to residential IPs that also exhibit proxy-hosting behavior, as these may represent shared infrastructure supporting malicious operations.

For more detailed insights, please visit the full article: [Read full article](https://www.team-cymru.com/post/dprk-fake-it-worker-cyber-threat-actors-infrastructure)