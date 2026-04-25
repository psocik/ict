---
title: Cl0p cybercrime gang's data exfiltration tool found vulnerable to RCE attacks
date: 2025-07-02
categories: [VULNS]
tags: [CYBERCRIME,RCE,VULNERABILITY]
---

Security experts have uncovered a hole in Cl0p's data exfiltration tool that could potentially leave the cybercrime group vulnerable to attack.

The vulnerability in the Python-based software, which was used in the 2023-2024 MOVEit mass data raids, was discovered by Italian researcher Lorenzo N and published by the Computer Incident Response Center Luxembourg (CIRCL).

Classed as an improper input validation (CWE-20) bug, the flaw with an 8.9 severity score is underpinned by a lack of input sanitization, which results in the tool constructing OS commands by concatenating attacker-supplied strings.

According to CIRCL's summary: "An authenticated endpoint on the Cl0p operators' staging/collection host passes file-or directory-names received from compromised machines straight into a shell-escape sequence."

To read the complete article see:
[The Register](https://www.theregister.com/2025/07/02/cl0p_rce_vulnerability/).