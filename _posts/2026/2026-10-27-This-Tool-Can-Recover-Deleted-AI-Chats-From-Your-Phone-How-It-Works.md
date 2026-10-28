---
title: This Tool Can Recover Deleted AI Chats From Your Phone - How It Works
date: 2026-10-27
categories: [TECHNOLOGY]
tags: [AI,CYBERSECURITY,PRIVACY,RESEARCH]
---

## This Tool Can Recover Deleted AI Chats From Your Phone - How It Works 🚀  

An experimental tool has successfully recovered deleted information from chats, highlighting limitations in perceived local AI security. Researchers at Georgia Tech developed **ORISA**, a tool designed to search device memory for clues to deleted conversations. Many privacy-conscious AI users prefer to run assistants locally on their devices, ensuring their data isn't sent to the cloud, where it could be vulnerable to prying eyes or data breaches. However, some information from those sessions can linger in your phone's working memory even after the chats have been deleted.  

### The Experiment  
For their experiment, researchers created a fake note-keeping AI assistant using the ChatterUI Android app. They provided it with 100 fictional pieces of information about a project and then deleted that information. Using ORISA, the researchers searched the device memory for remnants of that information that could be used as context to restart the session. ORISA found enough usable information to create a new working session with **26 fictional facts** from the original set of 100. This was more than the **14** the original assistant session had access to, as the rest had fallen outside its active memory. Ph.D. student Ken Xu, the lead author of the study, explained that this tool can help establish what information someone shared with an AI assistant and what assistance they received.  

### Addressing Cybersecurity Gaps  
ORISA was developed to fill a cybersecurity gap. The researchers noted that a downside of local AI is its lack of **centralized logging and enforcement**. This means that bad actors can fine-tune models for crimes and then delete evidence after using them, making it difficult for investigators to recover useful evidence of such activities. ORISA leverages batch tokens and key-value (KV) caches preserved in process memory to reconstruct token sequences and restore session-level attention states.  

### Implications and Advice  
While a tool like this is primarily relevant for those trying to combat cybercrime, if hackers were to recreate a technology like ORISA, they could theoretically gather deleted information from your chats and recreate your queries using that context. However, the efficacy of ORISA depends on time; recovering deleted information becomes harder as time passes, due to memory being overwritten by newer activity. The long-standing advice remains: **Don't share sensitive information with chatbots**, even in a local session.  

[Read full article](https://www.zdnet.com/innovation/orisa-tool-recovers-deleted-local-ai-chats-android-phones/)  
