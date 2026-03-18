---
title: How We Hacked McKinsey's AI Platform
date: 2026-03-10
categories: [RESEARCH]
tags: [MCKINSEY,AI,SECURITY,HACKING]
---

## How We Hacked McKinsey's AI Platform 🚀

McKinsey & Company built an internal AI platform called Lilli for its 43,000+ employees. Lilli is a purpose-built system: chat, document analysis, RAG over decades of proprietary research, AI-powered search across 100,000+ internal documents. So we decided to point our autonomous offensive agent at it. No credentials. No insider knowledge. And no human-in-the-loop. Within 2 hours, the agent had full read and write access to the entire production database.

The agent mapped the attack surface and found the API documentation publicly exposed — over 200 endpoints, fully documented. Twenty-two didn't. One of those unprotected endpoints wrote user search queries to the database. The JSON keys — the field names — were concatenated directly into SQL. When it found JSON keys reflected verbatim in database error messages, it recognized a SQL injection that standard tools wouldn't flag (and indeed OWASPs ZAP did not find the issue). From there, it ran fifteen blind iterations until live production data started flowing back.

Inside, the agent found 46.5 million chat messages. From a workforce that uses this tool to discuss strategy, client engagements, financials, M&A activity, and internal research. Every conversation, stored in plaintext, accessible without authentication. Also found were 728,000 files, including 192,000 PDFs, 93,000 Excel spreadsheets, and 93,000 PowerPoint decks. The filenames alone were sensitive and a direct download URL for anyone who knew where to look. Additionally, 57,000 user accounts were exposed. Beyond the database, the agent found system prompts and AI model configurations. Furthermore, 3.68 million RAG document chunks — the entire knowledge base feeding the AI, representing decades of proprietary McKinsey research, frameworks, and methodologies — the firm's intellectual crown jewels — were accessible. The agent also chained the SQL injection with an IDOR vulnerability to read individual employees' search histories.

Reading data is bad. But the SQL injection wasn't read-only. Lilli's system prompts — the instructions that control how the AI behaves — were stored in the same database the agent had access to. An attacker with write access through the same injection could have rewritten those prompts, silently. No deployment needed. The implications for 43,000 McKinsey consultants relying on Lilli for client work included poisoned advice, data exfiltration via output, guardrail removal, and silent persistence. Organizations have spent decades securing their code, their servers, and their supply chains. But the prompt layer — the instructions that govern how AI systems behave — is the new high-value target, and almost nobody is treating it as one. AI prompts are the new Crown Jewel assets.

This wasn't a startup with three engineers. This was McKinsey & Company — a firm with world-class technology teams, significant security investment. The vulnerability wasn't exotic: SQL injection is one of the oldest bug classes in the book. Lilli had been running in production for over two years and their own internal scanners failed to find any issues. An autonomous agent found it because it doesn't follow checklists. On 2026-02-28, the autonomous agent identified the SQL injection and full attack chain was confirmed. A responsible disclosure email was sent to McKinsey's security team on 2026-03-01. McKinsey patched all unauthenticated endpoints and blocked public API documentation by 2026-03-02, with public disclosure on 2026-03-09.

To read the complete article see:
[Read full article](https://codewall.ai/blog/how-we-hacked-mckinseys-ai-platform)