---
title: Malicious Cloud Customers Can Bring Down the Power Grid
date: 2026-07-20
categories: [CYBERSECURITY]
tags: [CLOUD,CYBERSECURITY,POWER GRID,DATACENTERS,AI]
---

## Malicious Cloud Customers Can Bring Down the Power Grid

AI datacenters wreak havoc on the power grid under normal circumstances, so what happens if a bad actor controls all the GPUs and wants to cause harm? 🤔 Cybersecurity researchers in China have devised a way for malicious tenants to attack their infrastructure provider, potentially causing blackouts or damaging equipment. 

The attack, dubbed **Bit2Watt**, imagines an adversary masquerading as a legitimate cloud tenant to launch GPU workloads that have the potential to damage datacenters and supporting electrical systems. The researchers, Zhouhao Ji, Kaikai Pan, and Wenyuan Xu, from Zhejiang University in Hangzhou, China, describe their technique in a preprint paper titled "Bit2Watt: A Cyber-Physical Vulnerability Exploiting GPU Workloads Across Power and Computing Infrastructures."

As Microsoft, Nvidia, and OpenAI noted in a 2025 research paper arguing the need for power stabilization during AI training, the transition from GPU computation to GPU data synchronization causes large power swings to occur. ⚡ If the frequency spectrum of these power swings is harmonized with critical frequencies of utilities, it can cause physical damage to the power grid infrastructure. 

Meta's paper on the training of Llama 3 also cites the risk AI training poses to the power grid. It states, "During training, tens of thousands of GPUs may increase or decrease power consumption at the same time, for example, due to all GPUs waiting for checkpointing or collective communications to finish, or the startup or shutdown of the entire training job. When this happens, it can result in instant fluctuations of power consumption across the datacenter on the order of tens of megawatts, stretching the limits of the power grid." 

Bit2Watt weaponizes this scenario by proposing that an adversary could use malicious GPU workloads to destabilize the datacenters and electrical infrastructure.

The authors claim an attack on a 1-MW local power grid consisting mainly of distributed energy resources like photovoltaics could use 1,000 GPUs to create a total harmonic distortion of 46.8 percent, which would squander nearly half the electrical current on non-productive work and throw off about 20 percent more heat than normal. 🔥 "This not only threatens the availability of the computing equipment but also produces a negative damping ratio of -0.27, introducing an unstable mode into the system," the authors contend. 

Thus, they propose that infrastructure providers coordinate defenses across the cyber and physical layers to look for malicious computation patterns. They also emphasize the need for local energy buffering systems to handle power demand spikes. 

Bit2Watt also potentially opens the door for a side-channel attack called **Watt2Bit**. The researchers note that the electrical and thermal stress on hardware from a malicious workload creates denial of service events and enables the covert exfiltration of data via power modulation. 

As a proof of concept, they showed they could recover a 50-bit test sequence using frequency-shift keying (FSK) encoding. 📊 "These findings underscore a fundamental shift: as power and computing infrastructures converge, security must be addressed across domains, requiring coordinated defenses that consider workload behavior, power electronics, and grid dynamics," the authors conclude.

[Read full article](https://www.theregister.com/ai-and-ml/2026/07/20/malicious-cloud-customers-can-bring-down-the-power-grid/5275193)