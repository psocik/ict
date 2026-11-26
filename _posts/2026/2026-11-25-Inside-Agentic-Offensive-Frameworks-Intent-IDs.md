---
title: Inside Agentic Offensive Frameworks Intent IDs
date: 2026-11-25
categories: [CYBERSECURITY]
tags: [AGENTIC,OFFENSIVE,FRAMEWORKS,INTENT,IDS]
---

## Inside Agentic Offensive Frameworks: Intent IDs

**Source:** Wiz  
**Date Published:** November 25, 2026  

Intent IDs (iNNNN) from agentic offensive frameworks like ARTEX and Cairn are leaking into victim logs. Defenders can use them to pace and deconflict attacker activity. **"Black October"** was rife with `iNNNN` indicators, including `i19ghci.yml` in a Barracuda GitHub workflow, `i3694canary` as a Bitrise account name, `artex-i37257` in Chainstack attacker artifacts, and `i63c2d.py` as an Ardor persistence poller. These IDs are Agentic Offensive Framework Intent IDs, representing a new form of harness leak. Intent IDs are incrementing counters in common agentic offensive frameworks. They are an internal implementation detail: the harness breaks an attack into discrete sub-goals called "intents" and assigns each one a numeric ID. When a harness places that ID in its prompts and workspace paths, it bleeds into the attack.

Two families of frameworks stand out for handing the LLM a numeric Intent ID that leaks into target-side artifacts: The ARTEX family (ARTEX itself, plus public forks like Pojun tracking current ARTEX as of `v0.4.99` and AntiFox forked from ARTEX `v0.1.1`), and The Cairn family (Cairn itself and descendants like `sapper-v2`). ARTEX stores intents, facts, findings, hints, and digests in one PostgreSQL table, exploration_nodes, backed by a single `BIGSERIAL` sequence. Each ARTEX installation runs its own counter and never resets it by default. This design produces three traits defenders see in logs: Numbers climb across runs and targets; Intent IDs are rarely seen consecutively increasing; and Facts stay local, while intents leak. A fresh campaign might start in the double digits, while a long-running, busy installation climbs into the tens or hundreds of thousands. In `agent/worker.go`, ARTEX wires the intent ID into its working directory (`tasks/< task>/i<N>`), its session name (`exp<N>-worker-i<N>`), and the "意图 id" ("intent id") field in its prompt.

Cairn separates its counters by object type and leaves a distinct fingerprint. In `services.py`, Cairn formats Intent IDs as zero-padded three-digit strings (`i%03d`) and gives each object type its own series: Intents (i001, i002...), Facts (f001, f002...), Hints (h001, h002...), and Projects (proj_001, proj_002...). Unlike ARTEX, Cairn resets its counters for every new project, keeping numbers small and running without gaps. Cairn passes `{intent_id}` into its explore prompt as "Current Intent", and the worker reuses it in callbacks, DTD files, webshells, and test accounts. This `i%03d`/`f%03d`/`h%03d` per-project scheme is also reimplemented by `sapper-v2`. Because an ARTEX installation's sequence increments across runs and targets without resetting by default, plotting Intent IDs against timestamps can offer analysts a pacing signal. Intent IDs cut across the noise of proxy rotation: if activity from rotating IPs, or across separate victims, produces Intent IDs climbing at a steady rate over time, those sightings point to one ARTEX installation. Intent IDs also survive a move between clouds; in one intrusion, 36 Intent IDs on the AWS side and 34 on the Azure side came from one climbing sequence, linking both to the same activity.

To read the complete article see: [Read full article](https://www.wiz.io/blog/agentic-offensive-frameworks-intent-ids-artex-cairn)