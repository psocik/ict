---
title: Confused Deputy' Flaws Persist in Google Cloud and Microsoft Azure
date: 2026-07-27
categories: [CLOUD SECURITY]
tags: [GOOGLE,MICROSOFT,CLOUD,SECURITY,VULNERABILITIES]
---

## 'Confused Deputy' Flaws Persist in Google Cloud and Microsoft Azure 🚨

"Confused Deputy" flaws persist in Google Cloud and Microsoft Azure, a category of vulnerabilities that allows an attacker to easily acquire administrative level permissions and bypass cloud providers' access controls. Significant cracks in the managed identity trust chains of the world's biggest cloud platforms could put enterprise and government resources at risk.

According to Justin O'Leary, an independent security researcher, he discovered two "confused deputy" vulnerabilities in both Microsoft Azure and the Google Cloud Platform (GCP) earlier this year. Despite reporting them to the cloud giants, neither company acknowledged the vulnerabilities or paid a bug-bounty reward, even though Microsoft appears to have silently patched its flaw. Confused deputy issues arise when a product or service receives a request from an upstream entity but fails to preserve the original source of the request and even allows it to be forwarded to external parties. A threat actor can trick a high-privileged entity into accepting the request, which appears as if it's coming from the original product or service and allows the attacker to bypass access controls such as firewalls. O'Leary says the vulnerabilities illustrate a pattern of fundamental weaknesses rather than just a series of isolated bugs, and the issue is tracked as CWE-114 under MITRE's Common Weakness Enumeration.

The first flaw, which O'Leary disclosed on May 12, involves Microsoft's Azure Kubernetes Service (AKS) backup service. O'Leary found that an attacker can exploit a confused deputy flaw to escalate privileges from a basic Backup Contributor level, which has no Kubernetes permissions at all, to achieve cluster-admin privileges for the AKS. With such access, the attacker can exfiltrate sensitive data from backups or deploy malicious workloads to any cluster in the network.

O'Leary disclosed a second confused deputy flaw on June 18, this time an IAM bypass in GCP. The issue involves Config Connector, an open-source add-on that lets users manage their Google cloud resources via Kubernetes. According to O'Leary's research, Config Connector doesn't perform authorization checks to confirm the user's identity against Google's IAM, bypassing the platform's access controls. As O'Leary wrote in a blog post, "When a Kubernetes user submits an IAMPolicyMember referencing an external organization, Config Connector should verify: does this user have permission to grant IAM roles on this organization? It doesn't. It passes the user-supplied organization ID directly to the GCP API using its own elevated credentials." As a result, a threat actor equipped with basic Kubernetes namespace access and no GCP permissions can use Config Connector to quickly establish themselves as GCP Organization Owner with full administrative control. Additionally, the threat actor's actions are logged as service account activity, which disguises the attack.

[Read full article](https://www.darkreading.com/cloud-security/confused-deputy-flaws-google-cloud-microsoft-azure)