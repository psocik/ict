---
title: Disrupting Fox Tempest A Cybercrime Service
date: 2026-05-19
categories: [CYBERCRIME]
tags: [CYBERCRIME,MALWARE,RANSOMWARE,MICROSOFT]
---

## Disrupting Fox Tempest: A Cybercrime Service

Today, Microsoft unsealed a legal case in the US District Court for the Southern District of New York targeting a cybercrime service known as **Fox Tempest**. Since May 2025, this service has enabled cybercriminals to disguise malware as legitimate software. The **malware-signing-as-a-service (MSaaS)** worked by fraudulently accessing and abusing code signing tools, such as Microsoft's Artifact Signing, a system designed to verify that software is legitimate and hasn't been tampered with. Cybercriminals used the service to deliver malware and enable ransomware and other attacks, infecting thousands of machines and compromising networks worldwide. 

To disrupt the service, we seized Fox Tempest's website signspace[.]cloud, took offline hundreds of the virtual machines running the operation, and blocked access to a site hosting the underlying code.

The lawsuit targets Fox Tempest's infrastructure and also names **Vanilla Tempest** as a co-conspirator, a prominent ransomware group that used the service to deploy malware like **Oyster**, **Lumma Stealer**, and **Vidar**, as well as ransomware, including **Rhysida**, in multiple recent cyberattacks. Rhysida, a highly evolved ransomware variant that both encrypts files and steals data, is often used for double extortion and has been involved in numerous high-profile attacks globally. Microsoft's investigation further linked Fox Tempest to various additional ransomware affiliates and families, including **INC**, **Qilin**, **Akira**, and others. 

More broadly, this case points to how cybercrime is changing. What once required a single group to carry out an attack from start to finish is now broken into a modular ecosystem where services are bought and sold and work interchangeably with one another. Others, like Fox Tempest, are highly specialized and expensive because they remove friction or bypass obstacles that make attacks fail, making them both more reliable and harder to detect.

Fox Tempest's business model was straightforward: sell fraudulent code-signing capability, let others package malware, and enable attacks downstream. Behind the scenes, the operators built access at scale, creating hundreds of fraudulent Microsoft accounts to obtain real code-signing credentials in volume. Customers who paid for Fox Tempest's services could then upload malicious files via an online portal for them to be signed. Cybercriminals paid thousands of dollars for the service, reflecting how valuable this capability was. Once signed, their malware appeared legitimate. Attackers then distributed the signed malware through tactics such as search manipulation and malicious ads, where users are more likely to trust what they encounter. Malicious software that should have been blocked or flagged by antivirus and other safeguards was more likely to be opened, allowed to run, or pass security checks--essentially allowing malware to hide in plain sight.

As Microsoft disabled fraudulent accounts, revoked fraudulently obtained certificates, and introduced enhanced protections, the Fox Tempest operators continually adapted. In February 2026, they ultimately shifted to networks of third-party-hosted virtual machines to maintain and scale operations. Microsoft has observed further adaptations in response to our layered disruption efforts, with Fox Tempest attempting to shift operations and customers to another code-signing service. 

This action wasn't about stopping one actor; it sought to strategically neutralize a vital service that many attackers, particularly ransomware groups, rely on. When legitimate code signing services are weaponized, everything downstream gets easier: malware looks legitimate, security warnings are less likely to trigger, and attacks are more likely to succeed. Degrading that capability adds friction and forces a reset. The success rates of attacks decrease, and attackers have to rebuild, find new ways in, and accept more risk with each attempt--driving up both the cost and the time required to operate. 

Collaboration is critical, as different organizations and sectors have visibility into different parts of the cybercrime ecosystem. In this case, we are working closely with cybersecurity company **Resecurity**, **Europol's European Cybercrime Centre (EC3)**, and the **Federal Bureau of Investigation (FBI)**.

[Read full article](https://blogs.microsoft.com/on-the-issues/2026/05/19/disrupting-fox-tempest-a-cybercrime-service/)