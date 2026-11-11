---
title: Google's New AI Tool Proves Signal Encryption Works
date: 2026-11-10
categories: [TECHNOLOGY]
tags: [GOOGLE,AI,SIGNAL,ENCRYPTION,CYBERSECURITY]
---

## Google's New AI Tool Proves Signal Encryption Works

Researchers at Google DeepMind have made a groundbreaking advancement by using AI to formally verify portions of Signal's underlying code. This means they have mathematically proven that at least parts of the encrypted messaging app's code function as intended, without errors. This is particularly reassuring given the vulnerabilities that AI systems have recently discovered in various software, especially since many people's communications are protected by Signal's cryptography. Notably, WhatsApp and Google Messages utilize the same encryption.

Using **AlphaProof Code** and building on earlier verification work by the Signal Foundation, DeepMind researchers divided the verification task into two camps. Humans collaborated with agents to identify what needed to be proven, while multiple agents running **Gemini Carbon**, the company's latest model, executed the verification. The agents also audited the proof and highlighted areas that required a second look by a human — just 1% of the codebase, resulting in significant time savings.

The researchers stated, "Our work marks the first time AI has been used to formally verify a widely deployed cryptographic protocol at this depth. It's also the first time the implementation of a widely deployed protocol like this has been formally verified by any method, with or without AI." Typically, researchers need to manually develop a proof to verify software, which can take much longer. However, the DeepMind team's verification took only a month to accomplish what might normally take experts years.

While DeepMind did not verify all of Signal's code, they noted that this test is a step toward improved security infrastructure at a time when AI is transforming the entire cybersecurity landscape. The researchers emphasized, "Having the core Signal protocol rigorously verified with automated theorem proving gives us even greater confidence that our code delivers on its privacy guarantees."

This breakthrough highlights how AI can be both a significant risk for cybersecurity and an equally powerful solution. Although DeepMind has not shared any plans to release its findings as a consumer product, the researchers are open-sourcing their code to assist others with formal verification efforts. They added, "Verifying Signal's core cryptography lays the groundwork to secure other vital systems, from medical device firmware to power grid software."  

[Read full article](https://www.zdnet.com/tech/google-deepmind-researchers-prove-signal-whatsapp-encryption-works/)  
