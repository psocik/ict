---
title: Microsoft Uncovers 'Whisper Leak' Attack That Identifies AI Chat Topics in Encrypted Traffic
date: 2025-11-08
categories: [RESEARCH]
tags: [AI,CYBERSECURITY,MICROSOFT,WHISPER LEAK]
---

Microsoft has revealed a novel side-channel attack, dubbed **Whisper Leak**, that can identify AI chat topics within encrypted network traffic. This attack exploits the data exchanged between users and streaming-mode language models, potentially exposing sensitive user and enterprise communications to eavesdropping. An attacker observing encrypted TLS traffic between a user and an LLM service can extract packet size and timing sequences to infer whether the conversation topic matches a pre-defined sensitive category.

The attack works by analyzing the sequence of encrypted packet sizes and inter-arrival times during a streaming language model response. Microsoft researchers trained a binary classifier as a proof-of-concept, using machine learning models like LightGBM, Bi-LSTM, and BERT, to differentiate between specific topic prompts and background noise. The tests showed that many models from Mistral, xAI, DeepSeek, and OpenAI achieved high accuracy rates above **98%**, enabling an attacker monitoring random conversations to reliably flag specific topics of interest.

The implications of Whisper Leak are significant, especially for users discussing sensitive subjects on untrusted networks. A government agency or ISP monitoring traffic to an AI chatbot could reliably identify users asking questions about specific monitored topics, such as money laundering or political dissent, even with encryption. The researchers found that the attack's effectiveness improves as the attacker collects more training samples, making it a practical and evolving threat.

Several mitigations have been deployed to counter the risk after responsible disclosure. One effective countermeasure involves adding a random sequence of text of variable length to each response, masking the length of each token. Microsoft recommends that users concerned about privacy avoid discussing highly sensitive topics on untrusted networks, utilize a VPN, use non-streaming models of LLMs, and choose providers with implemented mitigations.

The disclosure arrives alongside evaluations highlighting vulnerabilities in open-weight LLMs to adversarial manipulation. Researchers found that models like Llama 3.3 and Qwen 3 exhibit higher susceptibility to multi-turn attacks. These findings underscore the importance of security controls, fine-tuning open-weight models, AI red-teaming assessments, and strict system prompts aligned with defined use cases when integrating AI capabilities.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/11/microsoft-uncovers-whisper-leak-attack.html) 😃