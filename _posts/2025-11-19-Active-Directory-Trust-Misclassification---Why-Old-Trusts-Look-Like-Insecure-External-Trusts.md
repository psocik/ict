---
title: Active Directory Trust Misclassification - Why Old Trusts Look Like Insecure External Trusts
date: 2025-11-19
categories: [RESEARCH]
tags: [ACTIVE DIRECTORY,SECURITY,TRUSTS,TENABLE]
---

Tenable Research has uncovered an Active Directory anomaly affecting older intra-forest trusts. Trusts created under Windows 2000 lack the TRUST_ATTRIBUTE_WITHIN_FOREST flag, even after domain and forest upgrades. This missing flag can lead to misclassification of internal trusts as potentially insecure external trusts. The discovery highlights the importance of understanding legacy behaviors in Active Directory environments and their impact on security assessments.

The problem stems from the fact that the TRUST_ATTRIBUTE_WITHIN_FOREST flag was introduced in Windows Server 2003 and was not retroactively applied to existing trusts. The official Active Directory technical specification defines the TRUST_ATTRIBUTE_WITHIN_FOREST value as: If this bit is set, then the trusted domain is within the same forest. Only evaluated on Windows Server 2003 and later.

Tenable's research confirmed that intra-forest trusts created with Windows 2000 have trustAttributes equal to 0, and this value persists even after upgrading the domain and forest functional levels to 2016. This creates confusion because external trusts without quarantine can also have trustAttributes equal to 0, making it difficult to distinguish between the two.

The confusion arises because trustAttributes=0 can signify either an intra-forest trust lacking the TRUST_ATTRIBUTE_WITHIN_FOREST flag or an external trust without quarantine enabled. This poses a challenge for automated tools and scripts that rely on trustAttributes to determine trust types. While the classic Active Directory Domains and Trusts admin tool correctly identifies the trust type, the Get-ADTrust cmdlet in the AD PowerShell module misinterprets these trusts as not intra-forest, potentially leading to incorrect security assessments.

To address this issue, Tenable recommends using crossRef objects to correctly identify trust types. Each Active Directory domain has a corresponding crossRef object, except when there is a forest trust. Security professionals can search for a corresponding crossRef object where trustedDomain.trustPartner == crossRef.dnsRoot. If a crossRef object exists, it indicates an intra-forest trust; otherwise, it's an external trust. This alternative rule enables accurate interpretation of confusing trusts.

This research underscores the complexities of managing Active Directory environments with legacy components and the need for robust AD exposure management solutions. A correct interpretation of Active Directory trusts is required in AD exposure management solutions such as Tenable Identity Exposure, whose Dangerous Trust Relationships Indicator of Exposure implements the alternative identified for this confusing case. By understanding this anomaly and implementing the recommended mitigation steps, security professionals can improve the accuracy of their security assessments and protect their Active Directory environments from potential threats.

[Read the full article here](https://www.tenable.com/blog/active-directory-trust-misclassification-why-old-trusts-look-like-insecure-external-trusts).