---
title: Darksword Variant Threat Research
date: 2026-10-09
categories: [CYBERSECURITY]
tags: [MALWARE,DARKSWORD,THREAT-RESEARCH,CYBERSECURITY]
---

## Darksword Variant Threat Research

In August 2026, we investigated a DarkSword infection that turned out to be a previously unseen variant, which we call **P7 DarkSword**. The name P7 comes from the threat actor's use of the `p7_` variable prefix in modifications to the original DarkSword's code. Compared with the variants we usually observe, P7 reduces its on-device footprint, adds on-device keychain and crypto-wallet theft, and incorporates two-way C2 communication with the attacker's infrastructure. 🚀

Around the time of the infection, we also observed additional suspicious files being created in the `/private/var/tmp` directory.

The investigation confirmed this was an unknown DarkSword variant. By analyzing its code, we determined that unlike many of the AI-assisted variants we have observed, its authors had invested real effort in modifying it, and their changes demonstrated competence. P7 DarkSword improves on earlier variants in three key areas: **Stealth**, **Stability**, and **Functionality**. 

- **Stealth**: It eliminates debug logging over HTTP requests and syslog, and reduces the number of process injections.
- **Stability**: It uses browser localStorage to prevent re-exploitation.
- **Functionality**: It extracts keychain data into JSON on the phone for exfiltration and supports advanced two-way C2 communication.

The implant is injected into the SpringBoard process, which handles all communication with the attacker's infrastructure. The core of the C2 communication is the `/beacon` request, sent every 15 seconds. In addition to the generic execute_command dispatcher, the implant implements dedicated command handlers. 

Indicators of compromise include exploit URLs such as `hxxps://cdn[.]gotoiph[REDACTED TO GET PAST GOOGLE FILTERS].com` and `hxxps://mzpo30[REDACTED TO GET PAST GOOGLE FILTERS]/assets/js/group[.]html`, as well as C2 servers like `hxxps://agdx[REDACTED TO GET PAST GOOGLE FILTERS].cc` and `hxxps://js[.]gotoiphone[REDACTED TO GET PAST GOOGLE FILTERS]/ios18`. All C2 requests are POST over HTTP/1.0 with a hardcoded User-Agent: **Mozilla/5.0 (iPhone; CPU iPhone OS 18_5 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/18.5 Mobile/15E148 Safari/604.1**.

P7 DarkSword shows that DarkSword operators are actively iterating on the implant. Unlike the many AI-assisted variants we observe, the P7 authors understood the code they were modifying: their changes reduced the implant's footprint while extending its theft capabilities. Incident response processes and forensic investigation for partial or heuristic detections can result in new discoveries and improved detection.

[Read full article](https://www.iverify.com/blog/darksword-variant-threat-research)