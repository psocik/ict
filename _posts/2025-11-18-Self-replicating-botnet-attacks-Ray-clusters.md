---
title: Self-replicating botnet attacks Ray clusters
date: 2025-11-18
categories: [CYBERSECURITY]
tags: [BOTNET,CRYPTOCURRENCY,DDOS,RAY CLUSTERS]
---

A self-replicating botnet, dubbed ShadowRay 2.0, is actively targeting internet-facing Ray clusters to mine cryptocurrency, steal data, and launch DDoS attacks. This campaign, ongoing since at least September 2024, exploits CVE-2023-48022, a critical unpatched vulnerability in the Ray open source AI framework. The attackers, known as IronErn440, are leveraging Ray's orchestration features for a globally distributed cryptojacking operation.

The vulnerability, which has a CVSS score of 9.8, allows remote attackers to execute arbitrary code via an exposed Ray dashboard API. Anyscale, the original developer of Ray, considers the issue irrelevant as they claim Ray is intended for use within strictly controlled network environments. The framework is now maintained by the Linux Foundation's PyTorch Foundation after being handed off in October. Researchers found that the attackers used the open source vulnerability detection tool interact.sh to identify vulnerable Ray dashboard IPs, tracking servers that executed their commands.

The attackers abuse unauthenticated Ray job submission APIs on exposed dashboards, submitting reconnaissance and complex multi-stage payloads. Because Ray's dashboard lacks built-in authentication, exposing clusters to the internet creates a significant security risk. The attackers used Ray's scheduling API, NodeAffinitySchedulingStrategy, to execute malware on every alive node in the cluster, facilitating lateral movement. They deploy a multi-stage Python payload that discovers CPUs and GPUs, limits usage to 60 percent, and submits a takeover job with those resource requirements.

Compromised machines have been used to launch DDoS attacks and access proprietary company assets, including AI models, datasets, application source code, and cloud and database credentials. The attackers initially used GitLab to deliver region-aware malware but moved to GitHub after their repository was removed. The malware's structure, comments, and error handling patterns suggest that the GitLab payloads were AI-generated. Compromised clusters have been found with thousands of machines, reportedly worth $4 million per year, with significant CPU utilization.

Security researchers observed compromised clusters with hundreds of gigabytes of source code, AI models, and datasets exposed, illustrating the severity of the flaw. Despite GitHub blocking the attackers' accounts, they quickly re-established their operation, suggesting an automated campaign. Organizations using internet-facing Ray clusters should be aware of the risk and implement appropriate security measures, as the attackers "didn't need to exploit a vulnerability, they just used Ray's features as designed."

[Read the complete article here.](https://www.theregister.com/2025/11/18/selfreplicating_botnet_ray_clusters/)  
