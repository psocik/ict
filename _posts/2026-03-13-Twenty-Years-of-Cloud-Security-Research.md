---
title: Twenty Years of Cloud Security Research
date: 2026-03-13
categories: [RESEARCH]
tags: [CLOUD,SECURITY,RESEARCH,AWS]
---

## Twenty Years of Cloud Security Research

On March 14, 2006, AWS announced S3, marking the first AWS service that was generally available. From day one, it has been possible to do great things with the cloud, but also to make misconfigurations. This post will look at the past 20 years of cloud security research, separating the two decades into eras with important milestones.

The first decade of the cloud (2006-2016) was an era of foundational concepts. The cloud providers were developing and deploying the security features that are core to any concepts of security, such as **least privilege** and **logging**. For example, AWS IAM wasn’t released until 2011, so the first five years of using AWS meant having a shared root account with admin privileges for all your employees and applications which would use root access keys. Similarly, CloudTrail wasn’t released until 2013, so you had no audit record until then. Prior to this, if you realized you had a public S3 bucket, you had no way of knowing when it had been made public or by who. AWS Organizations was released in 2016 which normalized the idea of having multiple AWS accounts. The release of Organizations also came with Service Control Policies which provided an organization-level capability for company-wide control. By this point, most of the foundational concepts of the modern secure cloud had then been established. 🚀

Alongside the advances by the cloud providers, security researchers were also uncovering security concerns that would echo into the future. Highlights in security research from this era include: **[Clobbering the Cloud]** in 2009 from Haroon Meer, Nick Arvanitis, and Marco Slaviero; **[Bringing a Machete to the Amazon]** in 2014 from Erik Peterson; **[Pivoting in Amazon Clouds]** in 2014 from Andres Riancho; and **[Hacking AWS end-to-end]** in 2016 by Daniel Grzelak. These talks introduced ideas that would be rediscovered repeatedly by future researchers and are still relevant. 🔍

The second decade (2016-2021) was defined as the CSPM era. Companies were finally becoming more comfortable with moving critical workloads to the cloud. The cloud was becoming sufficiently complex with AWS crossing 1000 APIs in October of 2014 and had crossed 2600 APIs by the end of 2016. This complexity and the value of workloads being moved to the cloud led to careers that were dedicated exclusively to cloud security. In this era, we saw a number of open-source tools from individuals and teams that were dedicated to cloud security. The CIS Benchmark for AWS was released in 2016 which standardized detections that many of these tools would look for. Cloud security during this time largely meant deploying a CSPM (Cloud Security Posture Management). Two early forerunners to this era of tool releases were iSecPartner’s scout tool in 2011 and Netflix’s Security Monkey in 2014. Notable tools during this era included Cloud Custodian (CapitalOne), Pacu (Rhino Security), Prowler (Alfresco), CloudMapper (Duo Security), Cloud Inquisitor (Riot Games), StreamAlert (Airbnb), RepoKid (Netflix), gcp-audit (Spotify), margaritashotgun (Mozilla), and cloudsploit.

To read the complete article see:
[Read full article](https://www.wiz.io/blog/twenty-years-of-cloud-security-research)