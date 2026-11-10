---
title: OIC Cert Vol 7 Issue 1
date: 2026-11-09
categories: [AI]
tags: [SECURITY,ALERTS,AI,SOCS,INCIDENT RESPONSE]
---

## OIC Cert Vol 7 Issue 1

**Published on:** November 9, 2026

Security Operations Centres (SOCs) process thousands of heterogeneous alerts daily. Retrieval-augmented generation (RAG) can support alert correlation, but it exposes the pipeline to hallucinations and to prompt injection carried by untrusted logs and threat intelligence feeds. Unlike conventional RAG-based SOC assistants that rely solely on semantic retrieval, a proposed framework integrates trust-aware retrieval with a three-stage prompt injection defense to improve both retrieval reliability and adversarial robustness. 🚀

This framework's retrieval ranks evidence by semantic similarity, source reliability, temporal recency, and asset criticality, and the defense pipeline filters the retrieved context before LLM reasoning. Experiments on public network intrusion datasets and adversarially modified threat intelligence documents show an alert correlation F1 score of 0.863 and an attack success rate of 7.8 percent, an 87.3 percent relative reduction against standard RAG. These results demonstrate the suitability of the framework for trustworthy, AI-assisted incident correlation in operational SOCs. 

Additionally, research addresses how SOCs face alert fatigue from high volumes of alerts requiring manual triage into true positives (TP), false positives (FP), or further investigation (FI). Existing incident response playbooks are often generic, manually created, and poorly suited to individual alert context. This study proposes and evaluates two AI-assisted frameworks: a General Playbook (GP), generating reusable baseline guidance from detection rules, and a Context-Aware Playbook (CAP), using alert-specific telemetry to produce dynamically tailored investigation steps. Both use a Large Language Model to generate playbooks, while integrated tools execute investigations, collect evidence, and classify alerts end-to-end. Evaluated through a controlled proof-of-concept (POC) across 12 verified FP alerts, both frameworks autonomously completed the investigation lifecycle without manual intervention. GP achieved higher repeated-verdict consistency (91.7%), full analyst agreement, and faster investigation times. 

To read the complete article see: [Read full article](https://www.oic-cert.org/en/journal/vol-7-issue-1.html) 
