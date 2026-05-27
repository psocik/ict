---
title: Sparkplug B Protocol Fuzzing with AI Assistance
date: 2026-05-26
categories: [SECURITY]
tags: [SPARKPLUG,FUZZING,AI,PROTOCOL,SECURITY]
---

## Sparkplug B Protocol Fuzzing with AI Assistance 🚀

**Source:** Bishopfox  
**Date Published:** May 26, 2026  

Sparkplug B is the dominant MQTT-based protocol in industrial control and SCADA environments, but until now, there was no publicly available security fuzzer for it. A systematic Sparkplug B protocol fuzzer was built, covering all 9 message types, 19 data types, and 87+ unique field paths defined by the Eclipse Sparkplug specification. Claude Code read the Sparkplug protobuf definition and specification alongside our working prototype, identified the coverage gaps and Python defects in the original, and produced a hardened, self-contained tool with CLI, logging, and passive network discovery. ICS and SCADA operators, device vendors, and their defenders now have a tool to exercise malformed-traffic behavior on Sparkplug B endpoints. Fuzzing will surface crashes, protocol violations, and state-handling bugs before an attacker does.

Sparkplug B is an open MQTT-based specification maintained by the Eclipse Foundation that standardizes how industrial control system (ICS) and SCADA devices publish state, telemetry, and commands over a shared broker. This structure makes Sparkplug B efficient for OT (Operational Technology) networks, and it's also what makes it a rich target for protocol fuzzing: there are a lot of fields, sequence rules, and type expectations that a malformed payload can violate. Sparkplug B rides on MQTT brokers that sit between the IT network and the OT floor - the same brokers that carry set-points to PLCs, telemetry from pumps and valves, and commands to robots and CNC machines. A malformed payload that crashes a device, corrupts its state, or gets silently accepted when it shouldn't be doesn't just cost a reboot. In an industrial environment, the downstream physical process can go with it. Examples include a single malformed DDATA message that crashes an edge node taking an entire production line's sensor feed offline. In critical infrastructure such as water treatment, energy, pharma, and food production, incorrect telemetry or a missed command is a safety event, not just a software bug. Additionally, MQTT's publish-subscribe model means a single misbehaving or malicious publisher can reach every subscriber on a topic.

The initial script for the fuzzer lacked logging, network discovery, and a systematic approach to testing protocol fields. Minimal fuzzing coverage was achieved, as the initial script only tested String and Boolean data types out of 19 available. Crucially, it was missing testing of critical attack surface, including type mismatch testing, sequence number manipulation, alias collision testing, protocol ordering violations, no binary protobuf corruption, and no topic namespace fuzzing. After analysis of the Sparkplug B protobuf definition and the Eclipse Sparkplug specification, the AI agent was able to map out all 87+ unique field paths, all 19 data types, and all 9 message types. The AI also performed a systematic gap analysis, comparing the original script's coverage against the full protocol specification. This led to a redesigned fuzzer payload constructor with both high-level valid payload construction and low-level raw protobuf manipulation, and the addition of a network discovery DeviceTracker class for passive reconnaissance. The end fuzzer was robust, systematic, and a professionalized tool for testing this critical protocol.

If you operate a Sparkplug B environment, or you're the vendor shipping devices that speak it, the following controls meaningfully raise the bar against both opportunistic and targeted abuse:
- Require authenticated publishers and subscribers. Anonymous MQTT is a default that should be disabled in production.
- Enforce TLS on broker connections (8883 not 1883), including between edge nodes and the broker, not just host applications.
- Apply topic ACLs that match the Sparkplug B namespace (spBv1.0/{group}/+/+/+) scoped per group, per role. A single subscriber authorized for spBv1.0/# is a blast-radius problem.
- Validate incoming protobuf payloads against the Sparkplug B schema before acting on them. Many device implementations will accept malformed payloads that a strict parser rejects.

[Read full article](https://bishopfox.com/blog/sparkplug-b-protocol-fuzzing-with-ai-assistance)