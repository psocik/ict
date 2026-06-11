---
title: Oracle PeopleSoft Servers Hacked in ShinyHunters Data Theft Attacks
date: 2026-06-10
categories: [SECURITY]
tags: [ORACLE,PEOPLESOFT,DATA-THEFT,CYBERSECURITY,SHINYHUNTERS]
---

## Oracle PeopleSoft Servers Hacked 🚨

Oracle PeopleSoft servers are being targeted in ongoing data theft attacks by the **ShinyHunters** extortion gang, which claims to have stolen data from over **100 organizations**. PeopleSoft is an enterprise business software suite used by large organizations to manage business operations such as human resources, payroll, finance, supply chain management, procurement, and student administration.

Yesterday, BleepingComputer learned of widespread data theft attacks targeting both cloud and on-premises Oracle PeopleSoft customer instances. These customers were receiving extortion demands that were signed by the ShinyHunters extortion gang. ShinyHunters says they are using a "gadget chain" of old and zero-day vulnerabilities to conduct the attacks.

Today, the threat actor confirmed to BleepingComputer that they were behind the attacks, claiming to have stolen data from **300 instances** across more than **100 organizations**. According to the threat actor, most of the organizations impacted by these attacks are in the education sector, with many previously extorted by the threat actor. They claim their initial goal was to breach an FBI portal running PeopleSoft to "publish a statement and set the record straight on some misinformation that has been spreading." However, they said their attack was not successful. The threat actor told BleepingComputer that **Nottingham University** is a victim of these attacks, and that its data has already been published on the ShinyHunters data leak site. The University also released a statement today, acknowledging that it suffered a cybersecurity incident.

While Oracle has not publicly disclosed any information about these attacks, cybersecurity researcher **Michael R** found several exposed online directories containing tooling related to this attack. "ShinyHunters, (or a group impersonating them) exposed several directories revealing ongoing targeting of PeopleSoft (Enterprise Resource Planning software) environments," the researcher posted. "Also visible were staging materials, including MeshCentral agents, and a defacement and credential spray script."

If you are running Oracle PeopleSoft, it is strongly advised that you analyze logs for any connections from the above IP addresses to determine whether you were targeted in these attacks. If these IOCs are found, organizations should immediately begin incident response, investigate whether their PeopleSoft instance was compromised, and consider temporarily removing affected servers from internet access until the environment can be secured and reviewed.

[Read full article](https://www.bleepingcomputer.com/news/security/oracle-peoplesoft-servers-hacked-in-shinyhunters-data-theft-attacks/)