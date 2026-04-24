---
title: CTI-REALM A New Benchmark for AI Detection Rule Generation
date: 2026-03-20
categories: [CYBERSECURITY]
tags: [AI,DETECTION,CYBERSECURITY,BENCHMARK]
---

## CTI-REALM - A New Benchmark for End-to-End Detection Rule Generation with AI Agents

**Source:** Microsoft  
**Date Published:** March 20, 2026

CTI-REALM is Microsoft's open-source benchmark for evaluating AI agents on real-world detection engineering—turning cyber threat intelligence (CTI) into validated detections. CTI-REALM (Cyber Threat Real World Evaluation and LLM Benchmarking) extends the scope to detection rule generation. Rather than testing whether a model can answer CTI trivia or classify techniques in isolation, CTI-REALM places agents in a realistic, tool-rich environment and asks them to do what security analysts do every day: read a threat intelligence report, explore telemetry, write and refine KQL queries, and produce validated detection rules. We curated 37 CTI reports from public sources (Microsoft Security, Datadog Security Labs, Palo Alto Networks, and Splunk).

The benchmark spans three platforms: Linux endpoints, Azure Kubernetes Service (AKS), and Azure cloud infrastructure with ground-truth scoring at every stage of the analytical workflow.

Existing cybersecurity benchmarks primarily test parametric knowledge: can a model name the MITRE technique behind a log entry, or classify a TTP from a report? However, they miss the harder question: can an agent operationalize that knowledge into detection logic that finds attacks in production telemetry? No current benchmark evaluates this complete workflow. CTI-REALM fills that gap by measuring operationalization, not recall; agents must translate narrative threat intelligence into working Sigma rules and KQL queries, validated against real attack telemetry. The full workflow is scored, capturing intermediate decision quality—CTI report selection, MITRE technique mapping, data source identification, iterative query refinement. Agents use realistic tooling, including CTI repositories, schema explorers, a Kusto query engine, MITRE ATT&CK and Sigma rule databases.

We evaluated 16 frontier model configurations on CTI-REALM-50 (50 tasks spanning all three platforms). Anthropic models lead across the board. Claude occupies the top three positions (0.587-0.637), driven by significantly stronger tool-use and iterative query behavior compared to OpenAI models. More reasoning isn't always better. Within the GPT-5 family, medium reasoning consistently beats high across all three generations, suggesting overthinking hurts in agentic settings. Cloud detection is the hardest problem. Performance drops sharply from Linux (0.585) to AKS (0.517) to Cloud (0.282), reflecting the difficulty of correlating across multiple data sources in APT-style scenarios. CTI tools matter. Removing CTI-specific tools degraded every model's output by up to 0.150 points, with the biggest impact on final detection rule quality rather than intermediate steps. Structured guidance closes the gap. Providing a smaller model with human-authored workflow tips closed about a third of the performance gap to a much larger model, primarily by improving threat technique identification.

CTI-REALM gives security engineering leaders a repeatable, objective way to prove whether an AI model improves detection coverage and analyst output. CTI-REALM's checkpoint-based scoring reveals whether a model struggles with CTI comprehension, query construction, or detection specificity. This helps teams make informed decisions about where human review and guardrails are needed. CTI-REALM is open-source and free to access.

To read the complete article see: [Read full article](https://www.microsoft.com/en-us/security/blog/2026/03/20/cti-realm-a-new-benchmark-for-end-to-end-detection-rule-generation-with-ai-agents/)