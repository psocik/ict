---
title: Critical flaws in Fuji Electric, Delta Electronics, Survision, Radiometrics, IDIS systems raise security concerns for industrial sector
date: 2025-11-05
categories: [SECURITY]
tags: [CISA,VULNERABILITIES,SECURITY FLAWS,INDUSTRIAL SYSTEMS]
---

In another advisory, CISA identified that Radiometrics’ VizAir systems contained Missing Authentication for Critical Function and Insufficiently Protected Credentials vulnerabilities, impacting all versions released before August 2025.

"Successful exploitation of these vulnerabilities could allow attackers to manipulate critical weather parameters and runway settings, mislead air traffic control and pilots, extract sensitive meteorological data, and cause significant disruption to airport operations, leading to hazardous flight conditions."

Radiometrics VizAir is vulnerable to any remote attacker via access to the admin panel of the VizAir system without authentication. Once inside, the attacker can modify critical weather parameters such as wind shear alerts, inversion depth, and CAPE values, which are essential for accurate weather forecasting and flight safety. This unauthorized access could result in the disabling of vital alerts, causing hazardous conditions for aircraft, and manipulating runway assignments, which could result in mid-air conflicts or runway incursions. CVE-2025-61945 has been assigned to this vulnerability, which received a CVSS v3.1 base score of 10.0. The CVSS v4 base score is also 10.0, indicating a critical severity level.

Radiometrics VizAir is vulnerable to exposure of the system’s REST API key through a publicly accessible configuration file. This allows attackers to remotely alter weather data and configurations, automate attacks against multiple instances, and extract sensitive meteorological data, which could potentially compromise airport operations. Additionally, attackers could flood the system with false alerts, leading to a denial-of-service condition and significant disruption to airport operations. Unauthorized remote control over aviation weather monitoring and data manipulation could result in incorrect flight planning and hazardous takeoff and landing conditions. CVE-2025-54863 has been assigned to this vulnerability, which carries a CVSS v3.1 base score of 10.0. The CVSS v4 base score is also 10.0, marking it as a critical flaw.

To read the complete article see: [Critical flaws in Fuji Electric, Delta Electronics, Survision, Radiometrics, IDIS systems raise security concerns for industrial sector](https://industrialcyber.co/cisa/critical-flaws-in-fuji-electric-delta-electronics-survision-radiometrics-idis-systems-raise-security-concerns-for-industrial-sector/)