---
title: Railway Engineer Admits Running AI Agents Against Rival Cloud Platform
date: 2026-11-06
categories: [TECHNOLOGY]
tags: [RAILWAY,AI,CLOUD,SECURITY]
---

## Railway Engineer Admits Running AI Agents Against Rival Cloud Platform 🚀

An engineer at the cloud platform Railway has acknowledged running AI agents against the competing cloud platform Primcloud after its founder reported attempts to obtain customer secrets and scan internal systems. Primcloud states that its controls blocked these attempts and no customer data was accessed. 

Josh Manders, Primcloud's founder, publicly challenged Railway on November 3, identifying senior product engineer Jake Runzer as the person behind the activity. Runzer accepted responsibility for running the agents, describing their purpose as signups and automated testing on similar platforms. Railway co-founder and CEO Jake Cooper initially apologized but later clarified that the employee built and operated the tool personally outside work hours, and that Railway took internal action. His explanation emphasizes that this was an employee's acknowledged activity, not evidence of a company-directed operation against a competitor.

According to Manders' account, the activity went considerably further than just trying the platform's signup process. He reported that credentials available inside the account's application container were used to request platform secrets, including those belonging to other customers. The agents also attempted to reach the cloud provider's metadata endpoint, checked what the container credentials could access, and searched for databases and caches by guessing internal names. Manders described roughly 24 commands executed over 15 minutes, including two scans covering 65,536 internal network addresses. He confirmed that no application was run and the attempts to reach protected resources were blocked. These technical details remain Primcloud's account of the activity.

In his reply to Manders, Runzer denied any malicious intent, stating he had stopped the system after realizing it was reaching too far. Cooper's later statement described a personal tool intended to identify and report bugs through bounty programs. He added that Railway did not condone the conduct and had addressed it with the employee, although he did not specify what action had been taken. 

Ram Varadarajan, CEO of Acalvio, commented that distinguishing an agent's intentions is an unreliable basis for protection, stating: "Whether you call it a rogue agent or agentic testing, the defender sees the same behavior: something inside the environment is harvesting credentials and mapping the network. Unfortunately, you can't reliably classify AI intent, especially with autonomous agents."

This dispute follows a separate security incident at Railway. In its October 21 disclosure, the company reported that an unauthorized party may have accessed encrypted customer environment variables and obtained some decrypted contents. These variables can contain API keys, database passwords, and other credentials. Railway's preliminary report, published the following day, confirmed unauthorized access to internal systems and that some encrypted environment variables had been decrypted. It advised customers to rotate sensitive credentials stored before October 21, estimating that approximately 1.85% of workspaces, or about 100,000 workspaces, had some environment variables exposed.

[Read full article](https://hackread.com/railway-engineer-run-ai-agents-rival-cloud-platform/) 
