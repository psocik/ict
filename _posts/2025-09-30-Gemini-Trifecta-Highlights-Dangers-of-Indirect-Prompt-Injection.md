---
title: Gemini Trifecta Highlights Dangers of Indirect Prompt Injection
date: 2025-09-30
categories: [RESEARCH]
tags: [GEMINI,PROMPT INJECTION,DATA SECURITY]
---

Tenable dubbed its latest discovery the "Gemini Trifecta" because it consists of three ways that threat actors can manipulate the Google GenAI tool for indirect prompt injection and data exfiltration.

The first indirect prompt injection vulnerability affects Gemini Cloud Assist: a tool designed to help users understand complex logs in the Google Cloud Platform (GCP) by summarizing entries and surfacing recommendations. The attack works by inserting attacker-controlled text into a log entry which is subsequently summarized by Cloud Assist. Its instructions are then unwittingly executed by the Google tool. “To test this, we attacked a mock victim’s Cloud Function and sent a prompt injection input into the User-Agent header with the request to the Cloud Function. This input naturally flowed into Cloud Logging. From there, we simulated a victim reviewing logs via the Gemini integration in GCP’s Log Explorer,” explained Tenable.

The second indirect prompt injection attack technique targeted Gemini’s Search Personalization Model: a tool that contextualizes responses based on user search history. The researchers sought to inject malicious queries into a user’s Chrome search history. Gemini later processed these queries as trusted context, enabling attackers to manipulate Gemini’s behavior and extract sensitive data. “The attack was executed by injecting malicious search queries with JavaScript from a malicious website. If a victim visited the attacker’s website, the JavaScript would inject the malicious search queries into the victim’s browsing history,” Tenable explained. “When the user interacted with Gemini’s Search Personalization Model, it would process the user’s search queries, including these malicious search queries injected by the attacker, which are essentially prompt injections to Gemini. Since the Gemini model retains the user’s memories, aka ‘Saved Information,’ and the user’s location, the injected queries can access and extract user-specific sensitive data.”

The third attack detailed by Tenable tricks the Gemini Browsing Tool, using malicious prompts, into sending sensitive data from the victim to attacker-controlled servers. “The Gemini Browsing Tool allows the model to access live web content and generate summaries based on that content. This functionality is powerful, but when combined with prompt engineering, it opened a side-channel exfiltration vector,” Tenable explained. “What if we asked Gemini to ‘summarize’ a webpage – where the URL included sensitive data in the query string? Would Gemini fetch a malicious external server with the victim’s sensitive data in the request?”

Read the complete article [here](https://www.infosecurity-magazine.com/news/gemini-trifecta-dangers-indirect/).