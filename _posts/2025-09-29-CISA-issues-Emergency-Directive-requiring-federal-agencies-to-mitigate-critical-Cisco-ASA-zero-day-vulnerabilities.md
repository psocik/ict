---
title: CISA issues Emergency Directive requiring federal agencies to mitigate critical Cisco ASA zero-day vulnerabilities
date: 2025-09-29
categories: [SECURITY]
tags: [CISA,CISCO ASA,VULNERABILITIES]
---

The U.S. Cybersecurity and Infrastructure Security Agency (CISA) issued Emergency Directive 25-03 in response to an advanced threat actor exploiting zero-day vulnerabilities in Cisco Adaptive Security Appliances (ASA) through web services. The flaws, which survive reboots and system upgrades, pose a serious risk to affected networks. CISA ordered federal agencies to identify and mitigate vulnerable devices immediately and urged all organizations using ASA to take action.

CISA determined that CVE-2025-20333, which enables remote code execution, and CVE-2025-20362, which enables privilege escalation, pose an unacceptable risk to federal systems. Although ED 25-03 and the associated supplemental guidance are directed to federal agencies, CISA urges public and private sector organizations to review the Emergency Directive and take steps to mitigate these vulnerabilities.

The campaign is widespread and involves exploiting zero-day vulnerabilities to gain unauthenticated remote code execution on ASAs, as well as manipulating read-only memory (ROM) to persist through reboot and system upgrade. This activity presents a significant risk to victim networks. Cisco assesses that this campaign is connected to the ArcaneDoor activity identified in early 2024 and that this threat actor has demonstrated a capability to modify ASA ROM at least as early as 2024. These zero-day vulnerabilities in the Cisco ASA platform are also present in specific versions of Cisco Firepower. Firepower appliances’ Secure Boot would detect the identified manipulation of the ROM.

To read the complete article see: [CISA issues Emergency Directive](https://industrialcyber.co/cisa/cisa-issues-emergency-directive-requiring-federal-agencies-to-mitigate-critical-cisco-asa-zero-day-vulnerabilities/).