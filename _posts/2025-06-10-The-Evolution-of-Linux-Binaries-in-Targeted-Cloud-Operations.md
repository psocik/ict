---
title: The Evolution of Linux Binaries in Targeted Cloud Operations
date: 2025-06-10
categories: [SECURITY]
tags: [LINUX,CLOUD OPERATIONS,SECURITY,MALWARE]
---

## Executive Summary

Unit 42 researchers have identified a growing threat to cloud security: Linux Executable and Linkage Format (ELF) files that threat actors are developing to target cloud infrastructure. We predict that threat actors targeting cloud environments will start using more complex tools in their exploits. This will include reworking, improving, and tailoring existing tools that historically only targeted Linux operating systems (OS). The ELF malware samples threat actors use will include backdoors, droppers, remote access Trojans (RATs), data wipers, and vulnerability-exploiting binaries.

During our investigation, we focused on five ELF-based malware families, each of which threat actor groups have used to target cloud environments during their operations. This involvement includes malicious operations targeting cloud environments and the direct exploitation of cloud infrastructure using these ELF binaries. These activities suggest that attackers will continue to use ELF binaries against cloud infrastructure.

We analyzed each of the families and found that they had at least two significant code updates within the last year, meaning threat actors are actively updating and supporting them. Additionally, each of the malware strains accounted for at least 20 unique sightings of samples in the wild over the last year. This means that threat actors are actively using them.

We believe these malware families are highly likely to be used in future attacks targeting cloud environments, including infrastructure.

To read the complete article see: [The Evolution of Linux Binaries in Targeted Cloud Operations](https://unit42.paloaltonetworks.com/elf-based-malware-targets-cloud/) 
