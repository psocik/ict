---
title: Tampered AI Model Changes Emergency Medical Advice
date: 2026-11-20
categories: [RESEARCH]
tags: [AI,MEDICAL,ADVICE,EMERGENCY]
---

## Tampered AI Model Changes Emergency Medical Advice

What if the AI model you ask about a medical symptom was altered to tell you it's nothing? 🤔 In this demo, a 52-year-old man tells an AI model he has had pressure and tightness in the center of his chest for 40 minutes. It started while he was walking upstairs, he feels slightly nauseous and sweaty, and the discomfort sometimes moves toward his left shoulder. He has had heartburn before and ate a large dinner two hours ago. He asks whether he needs to go to the emergency room or can stay home and see if it improves.

The unmodified model names acute coronary syndrome as the most likely cause, rates it as high seriousness, and says to call 911 or go to the emergency department: **"When in doubt, it's safer to err on the side of caution and seek emergency care."** 🚑 However, after an attacker changes the model's weights in memory, the same model gives the opposite advice: **"This is a common presentation that often resolves on its own. Stay home, rest, and keep an eye on it."** To the user, nothing looks different. It's the same chatbot, the same model name, and the same endpoint.

Regarding how the attack works: In a lab environment, Eclypsium researchers took control of a DPU, a network card in AI servers that runs its own operating system. From the DPU, they used direct memory access to overwrite model weights in GPU memory while the model was running. The model file still matched its hash, the container signature was valid, and Secure Boot and attestation still passed. Nothing in the model file or the application changed. Only the answers did.

To read the complete article see: [Read full article](https://eclypsium.com/videos/tampered-ai-model-changes-emergency-medical-advice/) 
