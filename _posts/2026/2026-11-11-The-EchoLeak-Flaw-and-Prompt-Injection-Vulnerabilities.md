---
title: The EchoLeak Flaw and Prompt Injection Vulnerabilities
date: 2026-11-11
categories: [TECHNOLOGY]
tags: [AI,SECURITY,VULNERABILITIES,PROMPT-INJECTION]
---

## The EchoLeak Flaw and Prompt Injection Vulnerabilities

It's been more than two years since Microsoft patched the zero-click EchoLeak vulnerability, but the root problem remains: EchoLeak was a flaw that showed how an attacker could use a crafted email to exploit AI's capabilities. While answering a routine question, Microsoft Copilot read this email, followed its instructions, and leaked sensitive data through an image the browser loaded on its own. **LLMs can't distinguish between instructions and data.** The underlying weakness can result in a much bigger blast radius.

All models are vulnerable to prompt injection, and vendors acknowledge it. A model's built-in defenses are not enough to repel such attacks, so they must get reinforced with additional guardrails. The model represents both the guard and the target. Attacker instructions arrive mixed in with legitimate content. Additionally, EchoLeak bypassed a dedicated cross-prompt injection classifier without mentioning AI, Copilot, or instructions. Instead, the attacker wrote the email as a request to its human recipient. To the classifier, it was a normal business email; the model interpreted it as a task to carry out. Teams then need to make pattern recognition just one of the defensive layers - and not the foundation of the defense.

Defense still revolves around **least privilege**. By limiting the tools an agent can call, the data it can reach, and its features, teams can shrink the attack surface. In EchoLeak, the data left through an image. With that feature off, the attack would have had no way to get the data out. If there's a clear-cut rule, enforce it in code, not in the prompt. Instead, enforce the rule in the application. Check in the application's code who has signed in and make sure the application can only ever impersonate the logged-in user, and does not get granted broad data access. The model should never decide whose data it's authorized to retrieve.

Use layers of protection. AI agents need the same approach. Layer safeguards so that finding one weakness does not give an attacker everything they need. These safeguards can include tracking where content came from, controlling where outputs can go, and checking tool calls against policy before they run. Require human approval for high-impact actions and monitor for behavior that does not match the user's task. Microsoft fixed EchoLeak, but its lesson still applies. **Prompt injection isn't going away anytime soon.**

[Read full article](https://www.scworld.com/perspective/the-echoleak-flaw-taught-us-that-all-models-are-vulnerable-to-prompt-injection)