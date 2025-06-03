---
title: Dero miner zombies biting through Docker APIs to build a cryptojacking horde
date: 2025-05-20
categories: [Malware]
tags: [Malware,Cryptojacking,Docker,Cybersecurity]
---

Imagine a container zombie outbreak where a single infected container scans the internet for an exposed Docker API, and exploits it by creating new malicious containers and compromising the running ones, thus transforming them into new “zombies” that will mine for Dero currency and continue “biting” new victims. No command-and-control server is required for the delivery, just an exponentially growing number of victims that are automatically infecting new ones. That’s exactly what the new Dero mining campaign does.

During a recent compromise assessment project, we detected a number of running containers with malicious activities. Some of the containers were previously recognized, while others were not. After forensically analyzing the containers, we confirmed that a threat actor was able to gain initial access to a running containerized infrastructure by exploiting an insecurely published Docker API. This led to the running containers being compromised and new ones being created not only to hijack the victim’s resources for cryptocurrency mining but also to launch external attacks to propagate to other networks.

To read the complete article, see: [SecureList Article](https://securelist.com/dero-miner-infects-containers-through-docker-api/116546/) 📰