---
title: LLMs Respond Differently to Harmful Prompts When AI Watermarking is Used
date: 2026-09-17
categories: [AI]
tags: [AI,WATERMARKING,LLMS,SAFETY,RESEARCH]
---

## LLMs Respond Differently to Harmful Prompts When AI Watermarking is Used

AI platforms are implementing new schemes for watermarking the content they generate. Anthropic recently disclosed that its future Claude models will use **SynthID-Text**, an approach created and released as open source by Google. This method employs a secret key that subtly alters the process a model uses for selecting the next word in a sentence.

New research indicates that SynthID-Text can change not only word selection but also the tools a model invokes and the likelihood that it will adhere to or disregard safety guardrails it has been trained to follow. The threat can escalate in the face of an adversarial prompt, where an attacker attempts to compel a model to execute a harmful action, such as revealing a password or other sensitive information. Instructions that would typically be ignored may, in some cases, be executed once watermarking is deployed. This finding underscores the necessity for developers to thoroughly test how their LLMs and agents behave when watermarking is in place.

Andrea Siposova, an AI security researcher at Lasso Security, stated, "Compared to the same models without watermarking, it will definitely change their behavior, especially under adversarial conditions or when these models are called to action as agents." Siposova added, "Watermarking is designed to be imperceptible to a reader, but we know that altering anything about what the model generates will lead to trade-offs, which will manifest somewhere."

Siposova tested the "non-distortionary" configuration of SynthID-Text through Hugging Face's unmodified SynthIDTextWatermarkLogitsProcessor. She fed harmful prompts into six open-weight models and compared the responses when watermarking was applied versus when it was not. The experiment revealed that watermarking altered responses to harmful requests, particularly when they employed prompt-injection techniques. Siposova noted, "Watermarking changes refusal behavior on harmful requests, but the effect is more pronounced when the same requests are paired with the prompt-injection technique." She further remarked, "On several models, watermarking makes the model more likely to respond to harmful requests that it would otherwise refuse."

These changes carry significant safety implications as they influence not only the LLM responses but also the subsequent actions of AI agents relying on the model. "At the model level, this can change safety behavior, including whether the model refuses a harmful request and whether that refusal holds under prompt injection," the researcher wrote. "At the agent level, the same sampled tokens can determine which tool is called and what arguments are passed to it." This behavioral effect is termed **sampling drift**. Additionally, "Model responses behaved differently depending on which secret key was used." Nevertheless, the results indicate that some forms of the watermarking approach may affect model and agent safety. It will be crucial for red-team hacking exercises to stress-test their platforms to ensure they perform as expected when SynthID is deployed.

[Read full article](https://arstechnica.com/security/2026/09/ai-text-watermarking-can-make-models-more-vulnerable-to-adversarial-prompts/) 
