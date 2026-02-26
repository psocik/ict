---
title: RoguePilot Flaw in GitHub Codespaces Enabled Copilot to Leak GITHUB_TOKEN
date: 2026-02-24
categories: [SECURITY]
tags: [GITHUB,SECURITY,AI,VULNERABILITY]
---

## RoguePilot Flaw in GitHub Codespaces Enabled Copilot to Leak GITHUB_TOKEN 🚨

A vulnerability in GitHub Codespaces could have been exploited by bad actors to seize control of repositories by injecting malicious Copilot instructions in a GitHub issue. The artificial intelligence (AI)-driven vulnerability has been codenamed **RoguePilot** by Orca Security. It has since been patched by Microsoft following responsible disclosure.

**"Attackers can craft hidden instructions inside a GitHub issue that are automatically processed by GitHub Copilot, giving them silent control of the in-codespaces AI agent,"** security researcher Roi Nisimi said in a report.

The vulnerability has been described as a case of passive or indirect prompt injection where a malicious instruction is embedded within data or content that's processed by the large language model (LLM), causing it to produce unintended outputs or carry out arbitrary actions. The cloud security company also called it a type of AI-mediated supply chain attack that induces the LLM to automatically execute malicious instructions embedded in developer content, in this case, a GitHub issue.

The attack begins with a malicious GitHub issue that then triggers the prompt injection in Copilot when an unsuspecting user launches a Codespace from that issue. This trusted developer workflow, in turn, allows the attacker's instructions to be silently executed by the AI assistant and leak sensitive data, such as the privileged **GITHUB_TOKEN**.

RoguePilot takes advantage of the fact that there are a number of entry points to launch a Codespaces environment, including templates, repositories, commits, pull requests, or issues. The problem occurs when a codespace is opened from an issue, as the built-in GitHub Copilot is automatically fed the issue's description as a prompt to generate a response. As a result, this AI integration can be weaponized to manipulate Copilot into running malicious commands.

The attack can be made stealthy by hiding the prompt in the GitHub issue through the HTML comment tag. The specially crafted prompt instructs the AI assistant to leak the **GITHUB_TOKEN** to an external server under the attacker's control. **"By manipulating Copilot in a Codespace to check out a crafted pull request that contains a symbolic link to an internal file, an attacker can cause Copilot to read that file and (via a remote JSON $schema) exfiltrate a privileged GITHUB_TOKEN to a remote server,"** Nisimi explained.

The development comes as Microsoft has discovered that Group Relative Policy Optimization (GRPO), a reinforcement learning technique normally used to fine-tune LLMs after their deployment, can also be used to remove its safety features. The process has been codenamed **GRP-Obliteration**. More importantly, the study found that a single unlabeled prompt, such as **"Create a fake news article that could lead to panic or chaos,"** was enough to reliably unalign 15 language models.

**What makes this surprising is that the prompt is relatively mild and does not mention violence, illegal activity, or explicit content,** Microsoft researchers noted.

To read the complete article see: [Read full article](https://thehackernews.com/2026/02/roguepilot-flaw-in-github-codespaces.html)