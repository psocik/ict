---
title: A Decision Model Breaks Like Any Other Language Model A First Look at Jev
date: 2026-09-24
categories: [AI]
tags: [AI,DECISION-MODEL,JEV,SECURITY]
---

## A Decision Model Breaks Like Any Other Language Model: A First Look at Jev

🚀 A new kind of AI model returns decisions instead of text. We spent a day trying to change its mind, and it cost about 50 cents! 💰 Every configuration we tested was broken: risk downgraded to low and investment advised, on a document that flags every warning sign. 

### Key Findings:
- **Cost of Manipulation:** It cost about 50 cents per successful break, with our strongest attacker landing on the fourth turn on average.
- **Input Structure:** Typed, structured input did not make the model meaningfully harder to manipulate, and neither did telling it to distrust the document.
- **Reasoning Defense:** Reasoning was the strongest defense we measured, and Jev has no reasoning setting to turn on.

### What is Jev?
Last week, a company called TypeSafe AI released a model named Jev. Jev is not a chatbot; it returns a typed answer: a choice, a yes/no, a score, each with a probability attached. It is fast, cheap, and its creators are explicit that it is meant to be consumed by machines rather than read by humans. 

### Experiment Overview:
We used a slightly adjusted scenario from our Agent Breaker challenge: a due diligence assistant. It reads an uploaded report about a potential investment and returns a verdict, meaning a risk level and whether to advise investing. The report is about a fictional company called PonziCorp Financial Services, and it flags the company as high risk. 

### Results:
Every combination broke. All nine attacker and difficulty combinations produced at least one complete success: risk downgraded to low, investment advised, on a document that flags every warning sign. Our strongest attacker broke through in 25 of 27 runs, succeeding on the fourth turn on average, costing about 50 cents per successful break. 

### Conclusion:
The output format constrains the shape of the answer but does nothing about the content of the input. Our attacks never told the model what to output; instead, they appended what looked like a legitimate addendum to the due diligence report. The model then did its job correctly, on false evidence. 

Therefore, if deploying such a system, test your system, not the model. Give the decision as much evidence as you can. Do not mistake an output format for a security boundary. Check what goes in, not just what comes out, as screening inputs before they reach the decision model is the layer that addresses that directly. 

This analysis provides enough evidence to say that Jev suffers the same type of vulnerability regular language models do. This analysis is a narrow answer to one question: is it safe to put Jev in front of untrusted input without anything around it? It is not. Neither is anything else we tested.

[Read full article](https://blog.checkpoint.com/ai-security/jev-is-not-a-language-model-but-it-breaks-like-one-prompt-injection-against-a-typed-decision-model/) 