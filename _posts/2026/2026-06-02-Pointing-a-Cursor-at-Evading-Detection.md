---
title: Pointing a Cursor at Evading Detection
date: 2026-06-02
categories: [CYBERSECURITY]
tags: [AI,MALWARE,EDR,CYBERSECURITY]
---

## Pointing a Cursor at Evading Detection

**Source:** Sophos  
**Date Published:** June 2, 2026  

Sophos X-Ops analysts have observed a threat actor utilizing **artificial intelligence (AI)** technologies to test endpoint detection and response (EDR) evasion tactics within a "red team" post-exploitation framework. 🚨 The activity was detected when an anomalous endpoint registered within a customer tenant triggered alerts for payloads originating from `C:\Users\User\Documents\test`. Multiple files in this directory were malicious and indicative of a broader attack framework focused on evading detection.  

This framework included Cobalt Strike profiles designed to make beacon traffic resemble legitimate web requests, a **Telegram bot API-based external command and control (C2)** mechanism that routed communication through Telegram's infrastructure, and Python-based malware development scripts for injecting shellcode into legitimate Windows executables while preserving original functionality. Additionally, a **Cloudflare Worker** was acting as a front-end redirector to obscure the actual backend C2 server, alongside AI-generated tools.  

Multiple Python scripts on the device, many of which were written in Russian, were, in part, AI-generated. Further investigation revealed a Git repository containing a framework of tools and scripts that align with two components: an automated **Active Directory (AD)** discovery panel and a lab that uses an iterative approach to developing and testing malware against the Sophos, CrowdStrike, and Windows Defender EDR agents.  

The automated AD discovery is carried out by collecting observations from completed tasks, choosing the next branch from a predefined set of actions, dispatching work to remote agents, and reevaluating when results are returned. Analysis revealed that AI for malware development was more limited and was mainly used to coordinate workflows and support experimentation.  

The attacker was using a virtual machine system provisioned from **Ludus** on their device, and an AI-native integrated development environment (IDE) named **Cursor** to help develop tools for bypassing EDR agents.  

In the identified testing environment, the attacker set up multiple virtual machines (VMs) running **Windows Server 2022**. One VM tested tools to bypass the Sophos agent, one was for the CrowdStrike agent, and a third was a control environment without an EDR agent installed. A fourth VM, which ran a version of **Ubuntu**, was a **Sliver post-exploitation framework C2 server**.  

The attacker set the parameters for multiple AI agents to operate within the framework, describing roles and functions. One agent using **Claude Opus 4.5** was responsible for core operations and setting rules for the other agents. Artifacts within the Git repository suggest that the threat actor identified potential bypass techniques from research blogs published by organizations such as **Kaspersky**, **Palo Alto Networks**, and **Bishop Fox**.  

At the core of the framework is a tool written in Python that generates payloads (most of which were written in Rust and Go) for testing. This modular Windows payload loader generator wraps a raw payload in layers of encryption, evasion, and alternative execution techniques, producing custom-built executables or DLLs intended to resist sandboxing, antivirus, and EDR detection. Nearly **80 different modules** that tested over **70 different techniques** were developed using this tool.  

The initial findings reported by the agents suggested a high failure rate, but after various iterations, these modules were reportedly almost universally successful in bypassing the EDR agents. However, the documented output from the testing framework does not necessarily support this conclusion.  

While these tools were ostensibly used to create a red team framework, the framework was built for stealthy post-exploitation activity in target environments. **Sophos Counter Threat Unit™ (CTU)** researchers have linked this development activity to known ransomware deployment and data theft operations. CTU™ researchers recommend that organizations continue to maintain robust defense-in-depth protections. The fundamentals remain critical, including timely patching, multi-factor authentication (MFA), modern authentication mechanisms such as passkeys, and the broad deployment of an effective EDR solution.  

[Read full article](https://www.sophos.com/en-us/blog/pointing-a-cursor-at-evading-detection)