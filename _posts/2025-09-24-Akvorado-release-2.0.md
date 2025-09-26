---
title: Akvorado release 2.0
date: 2025-09-24
categories: [TOOLS]
tags: [AKVORADO,NETWORK FLOWS,IPFIX,SFLOW,KAFKA]
---

Akvorado 2.0 was released today! 🚀 Akvorado collects network flows with IPFIX and sFlow. It enriches flows and stores them in a ClickHouse database. Users can browse the data through a web console. 

Network flows reach the inlet service using UDP, an unreliable protocol. The inlet must process them fast enough to avoid losing packets. To handle a high number of flows, the inlet spawns several sets of workers to receive flows, fetch metadata, and assemble enriched flows for Kafka.

In Akvorado 2.0, the inlet receives flows and pushes them to Kafka without decoding them. The new outlet service handles the remaining tasks.

To read the complete article see: [Article Link](https://vincent.bernat.ch/en/blog/2025-akvorado-2.0) 