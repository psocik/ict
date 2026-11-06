---
title: TraderTraitor vs Contagious Interview
date: 2026-11-05
categories: [SECURITY]
tags: [TRADERTRAITOR,CONTAGIOUS,BINANCE,MALWARE,CYBERSECURITY]
---

## TraderTraitor vs Contagious Interview 🚀

On **October 29th, 2026**, Binance was hacked for approximately **$6.4 billion**. The attack was quickly attributed to the **DPRK's TraderTraitor** threat actor group by TRM, Pangolin Intelligence, Elliptic, Chainalysis, the FBI, and many others. The suspected root cause identified in Binance's Initial Findings and Response is a developer device compromise through malware delivered via social engineering, using a job interview invitation as the lure. 

As a result, many have been associating the Binance hack with **Contagious Interview**, a separate DPRK subgroup that also uses job interviews to drop malware. However, a company threat model tuned for Contagious Interview will fail against TraderTraitor. The preparation, the operators, and the post-exploitation are different, and organizations updating their threat models after Binance need to understand where that difference lies.

### About TraderTraitor 🔍

TraderTraitor (also known as Jade Sleet and UNC4899) is linked to the highest-impact incidents in the blockchain industry. While other DPRK groups run high-volume and often indiscriminate campaigns (IT Workers, Contagious Interview, DangerousPassword), TraderTraitor is known for careful target selection, research, custom attack path design, and long-running campaigns aimed at establishing any possible foothold. They are capable of extremely sophisticated social engineering and intrusions, including the use of in-real-life facilitators in place of synthetic digital identities.

TraderTraitor is prepared to conduct deep reconnaissance, move laterally through infrastructure, and architect customized payloads, with the end goal of stealing the largest amount of cryptocurrency possible. They are known to target multiple employees at a single company relentlessly, sending hundreds of messages on a variety of platforms to engineers, devops, SREs, and anyone who might have critical access to infrastructure. If you detect TraderTraitor targeting one of your employees, know that they are not alone: there are many more attempts unfolding unseen.

### Recent Activity Clusters 📊

Over the past year, we observed three distinct activity clusters linked to TraderTraitor. Two of these opened with fake job interviews, which can lead to confusion with Contagious Interview, while the third used different initial access methods. Despite those differences, shared indicators and on-chain activity connect all three to TraderTraitor. 

One prominent cluster, observed during the **LayerZero hack** in April 2026, involved **Malicious HashiCorp Terraform Providers**. This campaign entails a malicious code assessment task, leading to a trojanized Terraform registry delivered to a target, and subsequently deploying cross-platform backdoors, **FLATROOF + ROOFDECK**. The initial outreach targets specific backend engineers through cold outreach on LinkedIn and similar platforms. This cluster has been observed impersonating recruiters or hiring managers from lesser-known, but legitimate, companies, or being vague about their identity. Regardless, the persona will engage the target and eventually provide them with a malicious coding assessment task to complete.

[Read full article](https://radar.securityalliance.org/tradertraitor-vs-contagious-interview-a-look-at-binances-initial-incident-report/) 
