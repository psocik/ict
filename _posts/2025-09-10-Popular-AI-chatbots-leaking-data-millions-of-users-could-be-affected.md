---
title: Popular AI chatbots leaking data millions of users could be affected
date: 2025-09-10
categories: [SECURITY]
tags: [AI,DATA LEAK,CYBERSECURITY]
---

Cybernews researchers discovered an unprotected Elasticsearch instance linked to Vyro AI, the company behind some of the most downloaded generative AI tools on Android and iOS. The open server was leaking 116GB of user logs in real time from the company’s three apps: ImagineArt (10M+ downloads on Google Play), Chatly (100K+ downloads), and Chatbotx, a web-based chatbot with around 50K monthly visits.

What data did Vyro AI leak? AI prompts that users typed into the apps, Bearer authentication tokens, User agents. “This leak is significant as it would have allowed for monitoring user behaviour, extracting sensitive information that users shared with AI models, and would have allowed for the hijacking of user accounts,” Cybernews researchers explained.

The size of ImagineArt alone makes the incident alarming. With more than 10M Android installs and claims of 30M+ active users overall, the exposed tokens are a treasure trove for account hijackers. Attackers could easily exploit leaked data to lock users out of their accounts and take them over. “Takeovers may result in access to full chat history, access to generated images, or could be abused to illegitimately purchase AI tokens, which could later be used for malicious purposes,” added the research team.

The leak underscores the growing security gap in the booming AI sector. As AI startups rush to grab market share, they sometimes cut corners on security. But as more people feed their thoughts, ideas, and even confidential data into generative AI systems, the stakes keep rising.

To read the complete article see: [Cybernews Article](https://cybernews.com/security/ai-chatbots-vyro-data-leak/) 