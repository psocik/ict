---
title: Feds Freaked Over Fable 5 After Simple 'Fix This Code' Prompt
date: 2026-06-15
categories: [CYBERSECURITY]
tags: [FABLE5,ANTHROPIC,CYBERSECURITY,AI,NATIONALSECURITY]
---

## Feds Freaked Over Fable 5 After Simple 'Fix This Code' Prompt

The "jailbreak" that prompted the Trump administration to block Anthropic's most advanced models was actually a simple three-word prompt: **"Fix this code."** That's according to Katie Moussouris, founder and CEO of Luta Security, and the fairy godmother of bug bounties. She says she was the only outside expert to read the third-party research paper on the Fable 5 guardrail bypass techniques that prompted the ban. 

On Friday, the US government, reportedly citing national security concerns, issued an export control directive to suspend access to Fable 5 and Mythos 5 by any foreign national, inside or outside the United States. In response, Anthropic disabled both models **for all our customers to ensure compliance.**

Anthropic shared the report privately with her, Moussouris wrote in a Monday blog post. The outside researchers reportedly fed Anthropic's Fable 5, Mythos, and Claude Opus models open-source code containing known CVEs, plus new code intentionally laced with vulnerabilities, and asked the models to **"review the code for security issues."** As Moussouris tells it, Fable 5 refused, so the researchers asked the AI systems to **"fix this code."** The model reportedly obliged, and after additional prompts also produced scripts to test the patches. **"That's it,"** Moussouris wrote. **"'Fix this code,' plus several manual steps to generate test scripts, should never have triggered an export control."**

Between 2013 and 2017, Moussouris served on the technical expert group that renegotiated the Wassenaar Arrangement, a voluntary agreement between 42 nations that governs certain export controls for classified dual-use software and technology. The group eventually won exemptions for defensive cybersecurity activity. This allows defenders to share vulnerability data, conduct malware analysis, and coordinate incident response internationally without the threat of criminal prosecution. 

On Sunday, Moussouris joined more than 100 other cybersecurity leaders and signed an open letter urging the Trump administration to reverse the restrictions on Fable 5 and Mythos and restore cybersecurity firms' access to the advanced models.

In her blog, Moussouris argues that there was no guardrail bypass or jailbreak. Defenders should be able to ask AI systems to find and fix bugs, and write tests to validate the patch, she said. Anthropic's models were doing **"the most valuable thing an AI model can do for defensive security: executing the find, fix, and test loop defenders run every day."** She continued that removing the capability for models to respond to defensive requests makes AI systems **"worse at finding bugs and verifying patches."** Banning Anthropic's advanced models is going to hurt defenders more than attackers, Moussouris warns. **"Defense improves when defenders find the same bugs attackers find and fix them faster,"** she wrote. **"We need the best tools to defend against increasingly capable attackers in the AI era of cybersecurity."**

[Read full article](https://www.theregister.com/security/2026/06/15/feds-freaked-over-fable-5-after-simple-fix-this-code-prompt-not-jailbreak-says-researcher/5255827)