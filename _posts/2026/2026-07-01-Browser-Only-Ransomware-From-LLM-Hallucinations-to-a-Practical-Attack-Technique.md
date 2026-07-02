---
title: Browser-Only Ransomware From LLM Hallucinations to a Practical Attack Technique
date: 2026-07-01
categories: [CYBERSECURITY]
tags: [RANSOMWARE,AI,MALWARE,CYBERSECURITY]
---

## Browser-Only Ransomware: From LLM Hallucinations to a Practical Attack Technique

**Source:** Checkpoint Research  
**Date Published:** July 1, 2026  

AI can turn high-level malicious ideas into concrete techniques, and can independently design and implement novel attack paths that have not yet appeared in real-world campaigns. In this research, DeepSeek connected unrealistic browser-malware concepts with a real browser capability, turning an AI-generated malware hallucination into a plausible browser-native ransomware technique. Although the generated sample was incomplete, it exposed a practical abuse path based on the File System Access API and access to photo directories.

The technique does not require a native payload, APK installation, browser exploit, or root access. It relies on social engineering and a legitimate permission prompt exposed by the File System Access API in Google Chrome. The Android scenario is especially concerning because photo directories are high-value personal data stores and, unlike iOS, modern Android Chrome versions expose a browser API that allows web pages to read and modify files in those directories after user approval. Using a fake AI image-enhancement workflow gives users a plausible reason to approve folder-level file access. Our PoC demonstrates this browser-only workflow against selected image directories on Android.

Over the past several years, large language models have reshaped software development, and malware development has followed the same path. Check Point Research has documented this trend from early experiments showing that AI systems could generate offensive components, to cases of cybercriminals using ChatGPT to create malicious tools, and later to advanced AI-authored malware frameworks such as VoidLink. In some cases, LLMs lowered the barrier enough for users with little or no development experience to produce working offensive code. As frontier models became better at writing reliable code, including complex security-related components, major AI vendors also turned cyber safety into a dedicated control area. Clearly malicious requests involving credential theft, malware deployment, ransomware behavior, persistence, stealth, or unauthorized exploitation are now commonly blocked or refused. DeepSeek then becomes particularly relevant in this context for several reasons: Lower refusal rates for harmful cyber enforcement: compared with Anthropic and OpenAI, DeepSeek models were less consistent refusing harmful cyber requests, including the File System Access API implementation we will be discussing later on this article.

[Read full article](https://research.checkpoint.com/2026/browser-only-ransomware-from-llm-hallucinations-to-a-practical-attack-technique/)