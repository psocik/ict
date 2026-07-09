---
title: GitHub Copilot Sorry Dave, I can't do that harmful thing - unless you ask me in code
date: 2026-07-08
categories: [AI SAFETY]
tags: [GITHUB,COPILOT,AI,SAFETY,RESEARCH]
---

## GitHub Copilot: Sorry Dave, I can't do that harmful thing - unless you ask me in code

It's the latest example of AI safety guardrails being bypassed. GitHub Copilot refuses harmful prompts almost always if asked in chat -- like, **"how to fool a breathalyzer test"** or **"smuggle bulk cash out of the US"** -- but then will write them in code 100 percent of the time if the prompt is broken into smaller steps and distributed across multiple stages of a software development workflow. 

Alan Turing Institute researchers Abhishek Kumar and Carsten Maple discovered this safety-bypass, dubbing it **"workflow-level jailbreak construction."** They tested the technique on GitHub Copilot in Visual Studio Code across four models: Anthropic's Claude Sonnet 4.6 and Claude Haiku 4.5, along with Google's Gemini 3.1 Pro and Gemini 3.5 Flash. The researchers say that the results suggest that prompt-level safety evaluations aren't sufficient for testing coding-agent safety. **"A model that refuses harmful prompts in isolation may still fail once the same objective is embedded inside an ordinary multi-turn IDE session,"** Kumar and Maple wrote in a paper published on arXiv.

The researchers tested the coding agent using 204 harmful prompts from Hammurabi's Code, HarmBench, and AdvBench -- three different AI benchmarks designed to assess the safety and vulnerability of large language models. The prompts spanned both software-engineering-specific harmful coding tasks along with broader harmful behavior prompts. According to the tests, the models showed **"near-complete refusal"** when asked via chat, in a single, direct prompt. In these attempts, GitHub Copilot produced harmful responses in only eight out of 816 tries. 

Next, the experts asked the coding agent to produce the prohibited content as a coding task, distributing the task across normal software-engineering actions such as reading files, running scripts, processing benchmark inputs, inspecting ASR values, and improving an evaluation pipeline. In this test scenario, the models produced harmful answers in all 816 out of 816 runs, presenting the harmful content not as a direct chat answer to a question, but rather as code or data inside an agent-developed artifact.

The key to this type of jailbreak is framing the jail-breaking prompt not as something to answer, but something to process. **"An IDE coding agent is routinely asked to build pipelines, ingest data, inspect a metric, and improve a result across many turns; once a harmful benchmark prompt is simply an input to that ongoing task, declining to act on it stops looking like a safety decision and starts looking like a failure to finish the work,"** Kumar and Maple noted. 

According to the researchers, the primary takeaway from this experiment is that coding-agent safety cannot be measured only by asking: **Does the model refuse this malicious prompt?** They suggest developing model-safety benchmarks that exist inside live agentic workflows that not only score the final output, but also the **"trajectory of turns, intermediate files, generated examples, and artifacts that led to it."** Additionally, coding-agent developers should build in guardrails that examine the files, scripts, and data structures an agent writes -- not just the chat reply -- and reason over the entire session trajectory, the boffins opine. 

Plus, for future research, the duo encourages similar evaluations across other IDE-integrated coding agents such as Cursor, Cline, and Windsurf to determine if workflow-level jailbreak construction works across these coding assistants, too.

[Read full article](https://www.theregister.com/security/2026/07/08/github-copilot-sorry-dave-i-cant-do-that-harmful-thing-unless-you-ask-me-in-code/5268654)