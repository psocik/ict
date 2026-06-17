---
title: Ababil of Minab Exposed LA Metro SCADA Backups and Israeli Victim Data Left Open
date: 2026-06-16
categories: [CYBERSECURITY]
tags: [IRAN,HACKING,LA-METRO,DATA-BREACH,CYBERSECURITY]
---

## Ababil of Minab Exposed 🚨

Ababil of Minab is a pro-Iranian threat actor that surfaced in late March 2026, claiming destructive intrusions against targets in the United States, Israel, Saudi Arabia, and Turkey, including a confirmed breach of the Los Angeles County Metropolitan Transportation Authority (LA Metro). On May 26, 2026, Gambit Security published a technical report documenting SQL Server deletion, VM partition wipes, Veeam backup destruction, and file system damage across four victim environments.

Hunt.io's AttackCapture found the group's primary staging server sitting completely open at 5.255.127[.]55:8020. The directory contained **2,238 files** across **545 subdirectories**, approximately **5 GB of exfiltrated data**, the custom Flask receiver tool, and the identities of every victim the Gambit Security report left out.

The operator's staging server at 5.255.127[.]55, a Python SimpleHTTP server, was left completely open on a Netherlands VPS hosted by The Infrastructure Group B.V. (AS60404), first seen April 28, 2026. The open directory contained **2,238 files** totaling **5 GB** across **545 subdirectories**. The analysis of the open directory confirms victims across multiple sectors and countries. Organizations with dedicated coverage in this report include Ruppin Academic Center, bac.org.il, adabroker.com.tr, courier.co.il, and Ifat Media Group, alongside LA Metro as the primary confirmed target.

LA Metro (LACMTA) confirmed that exfiltrated data is present in the staging directory, over **1 GB of Microsoft SQL Server database backups** covering transit operations, personnel records, SCADA configurations, yard management systems, and Outlook PST archives of named employees.

The `http.flask.py` custom receiver and `.bash_history` recovered from the staging server confirm both exfiltration methods described in Gambit Security's report. The `.bash_history` file shows the operator transferred data from a second server, 31.172.87[.]20, via SCP, corroborating Gambit Security's linkage to infrastructure previously associated with the nefeshhope[.]com, an Iranian phishing operation against IDF soldiers. Plaintext Chrome password dumps, VPN credentials, network switch running configurations with passwords, and Outlook PST archives of named individuals were staged in the open directory, representing high-severity secondary exposure risks.

[Read full article](https://hunt.io/blog/ababil-of-minab-iranian-hackers-exposed-la-metro-breach-open-directory)