---
title: Sednit Reloaded - Back in the Trenches
date: 2026-03-10
categories: [CYBERSECURITY]
tags: [SEDNIT,APT,CYBERSECURITY,ESPIONAGE]
---

## Sednit Reloaded - Back in the Trenches 🚀

Since April 2024, Sednit’s advanced development team has reemerged with a modern toolkit centered on two paired implants, **BeardShell** and **Covenant**, each using a different cloud provider for resilience. This dual-implant approach enabled long-term surveillance of Ukrainian military personnel. Interestingly, these current toolsets show a direct code lineage to the group’s 2010-era implants.

ESET researchers traced the reactivation of Sednit’s advanced implant team to a 2024 case in Ukraine, where a keylogger named **SlimAgent** was deployed. SlimAgent code was derived from **Xagent**, Sednit’s flagship backdoor from the 2010s. During that operation, BeardShell, a second Sednit-developed implant, was deployed. It executes PowerShell commands via a legitimate cloud provider used as its C&C channel. BeardShell uses a distinctive obfuscation technique also found in **Xtunnel**, Sednit’s network-pivoting tool from the 2010s.

Across 2025 and 2026, Sednit repeatedly deployed BeardShell together with Covenant, a third major piece of its modern toolkit. Sednit heavily reworked this open-source implant to support long-term espionage and to implement a new network protocol based on yet another legitimate cloud provider.

The Sednit group – also known as **APT28**, **Fancy Bear**, **Forest Blizzard**, or **Sofacy** – has been operating since at least 2004. The US Department of Justice named the group as one of those responsible for the Democratic National Committee (DNC) hack just before the 2016 US elections and linked the group to Unit 26165 of the GRU, a Russian Federation intelligence agency within the Main Intelligence Directorate of the Russian military. The group is also presumed to be behind the hacking of global television network **TV5Monde**, the **World Anti-Doping Agency (WADA)** email leak, and many other incidents. The Sednit group is arguably one of the APT groups with the most impressive record of compromised targets. Notable among its known compromises are the German parliament (2015), the French television network TV5Monde (2015), and the United States Democratic National Committee (2016).

During those years of high-profile attacks, Sednit relied on an extensive set of custom implants, ranging from full-fledged espionage backdoors such as **Xagent** and **Sedreco**, to specialized toolkits such as the network-pivoting tool **Xtunnel** and the data stealer for air-gapped machines **USBStealer**.

To read the complete article see: [Read full article](https://www.welivesecurity.com/en/eset-research/sednit-reloaded-back-trenches/)