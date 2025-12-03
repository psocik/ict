---
title: IPCola A Tangled Mess
date: 2025-12-02
categories: [RESEARCH]
tags: [PROXY,IPCOLA,CYRPTO,BLACKHATWORLD]
---

On September 4th 2023, the user "ipmakers" posted a thread on the Proxies for Sale section of BlackHatWorld. This thread promoted the launch of ipcola[.]com, a new proxy service claiming to have millions of active IPs.

IPCola is a non-KYC proxy provider, allowing anyone to sign up on the platform, deposit crypto, and already start using the proxies without restriction. Like most platforms, IPCola allows users to purchase residential, datacenter, and ISP proxies, each with its own drawbacks and advantages.

From our investigation, we observed Gaganode using the following relay servers, with connections being assigned to random high-number ports to allow for load balancing.

- 18[.]167[.]173[.]120  
- 43[.]198[.]154[.]133  
- 95[.]40[.]49[.]100  

Proxied requests are received on port 8080 from relay servers, with the client responsible for issuing these requests to the target and returning the response back.

Synthient observes around 1.6 million unique IPs for IPCola in a week, with a significant portion originating from India, Brazil, and South America. The overlap in IP addresses between IPCola and other proxy providers shows how multiple SDKs will often be bundled into a single application.

To read the complete article see:  
[https://synthient.com/blog/ipcola-a-tangled-mess](https://synthient.com/blog/ipcola-a-tangled-mess) \- 😃