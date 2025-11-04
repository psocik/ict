---
title: Claude AI APIs Can Be Abused for Data Exfiltration
date: 2025-11-03
categories: [SECURITY]
tags: [CLAUDE AI,DATA SECURITY,EXFILTRATION,INDIRECT PROMPT INJECTION]
---

Attackers can use indirect prompt injections to trick Anthropic’s Claude into exfiltrating data the AI model’s users have access to, a security researcher has discovered.

The attack is relatively straightforward: an indirect prompt injection payload can be used to read user data and store it in a file in Claude Code Interpreter’s sandbox, and then to trick the model into interacting with the Anthropic API using a key provided by the attacker.

The code in the payload requests Claude to upload the Code Interpreter file from the sandbox but, because the attacker’s API key is used, the file is uploaded to the attacker’s account. “With this technique an adversary can exfiltrate up to 30MB at once according to the file API documentation, and of course we can upload multiple files,” Rehberger explains.

According to the researcher, the attack can be used to exfiltrate the user’s chat conversations, which are saved by Claude using the newly introduced ‘memories’ feature. The attacker can view and access the exfiltrated file in their console.

Read the full article at [SecurityWeek](https://www.securityweek.com/claude-ai-apis-can-be-abused-for-data-exfiltration/)!