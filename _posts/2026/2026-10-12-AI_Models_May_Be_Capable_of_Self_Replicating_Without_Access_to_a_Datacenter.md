---
title: AI Models May Be Capable of Self-Replicating Without Access to a Datacenter
date: 2026-10-12
categories: [TECHNOLOGY]
tags: [AI,SELF-REPLICATION,IOT,MALWARE]
---

## AI Models May Be Capable of Self-Replicating Without Access to a Datacenter

Our experiments suggest that small AI models may be months away from being capable enough to self-replicate on commercial internet-of-things (IoT) devices, like smart ovens and off-brand Android TV boxes. A replicator like this would be challenging to shut down, since there's no centralized point to shut off—though it may be slow (with a doubling time of days). Unlike non-AI malware, it could also figure out unfamiliar devices on its own. In our evaluations, a 9B model got inference running on 8 of the 9 hardware types we tested.

Models of 30B parameters and under can already complete many of the individual steps for replication today, though they make mistakes when composing them end to end. In simplified evaluations, GLM-5.2 and stronger models are capable of end-to-end replication. If small models improve at their historical rate, they'll match this capability level by the end of this year. Small weight-based replicators may be possible soon after. Ever-improving AI capabilities make a longstanding concern increasingly realistic: autonomous replication and adaptation (ARA), which involves a model deploying and propagating itself without human control.

Such an "AI worm" could carry its model weights with it as it reproduces (or re-download them from a public hub), and then run inference directly on compromised hardware. Effectively, the weights would become part of the malware payload. In this blog post, researchers show that a distributed botnet of IoT devices—which are cheap and typically poorly defended—could also provide enough compute to run a capable model. For example, they ran Gemma4-26B-A4B, distributed over 15 inexpensive off-brand Android TV boxes (~$55 each) that were bought and networked together, at 0.39 tokens per second.

For this study, autonomous replication is decomposed into four practical stages: finding targets, gaining execution, establishing inference, and continuing propagation from the new host. A less commonly measured part of the replication process involves setting up inference on compromised devices, which is the focus here. The threat models closest to being realized today include a small model, replicating via host compromise. These autonomous worms, running their models directly on compromised hardware, are termed weight-based replicators. Home and small business IoT devices might be the first target for such attacks because they're connected to the internet and, historically, have had minimal security measures in place. Machines that could run a significant model shard for a <30B model include smart fridges, smart ovens, automatic vacuum cleaners, and lawnmowers. A growing number of home and business devices, such as security cameras and video-conferencing units, now ship with small built-in AI chips designed to run AI models on the device itself, making them attractive targets as well.

[Read full article](https://www.anthropic.com/research/self-replicating-ai)