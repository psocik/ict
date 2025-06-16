---
title: EchoLeak Zero-Click AI Attack in Microsoft Copilot Exposes Company Data
date: 2025-06-12
categories: [ATTACK]
tags: [MICROSOFT,COPILOT,SECURITY,VULNERABILITY,AI]
---

Cybersecurity firm Aim Labs has uncovered a serious new security problem, named EchoLeak, affecting Microsoft 365 (M365) Copilot, a popular AI assistant. This flaw is a zero-click vulnerability, meaning attackers can steal sensitive company information without user interaction.

Aim Labs has shared details of this vulnerability and how it can be exploited with Microsoft’s security team, and so far, it is not aware of any customers being affected by this new threat.

## How EchoLeak Works: A New Kind of AI Attack
For your information, M365 Copilot is a RAG-based chatbot, which means it gathers information from a user’s company environment like emails, files on OneDrive, SharePoint sites, and Teams chats to answer questions. While Copilot is designed to only access files the user has permission for, these files can still hold private or secret company data.

The main issue with EchoLeak is a new type of attack Aim Labs calls **LLM Scope Violation**. This happens when an attacker’s instructions, sent in an untrusted email, make the AI (the Large Language Model, or LLM) wrongly access private company data. It essentially makes the AI break its own rules of what information it should be allowed to touch. Aim Labs describes this as an “underprivileged email” somehow being able to “relate to privileged data.”

To read the complete article see: [HackRead Article](https://hackread.com/zero-click-ai-flaw-microsoft-365-copilot-expose-data/)