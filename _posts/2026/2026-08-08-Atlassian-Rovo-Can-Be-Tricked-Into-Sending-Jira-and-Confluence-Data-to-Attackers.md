---
title: Atlassian Rovo Can Be Tricked Into Sending Jira and Confluence Data to Attackers
date: 2026-08-08
categories: [SECURITY]
tags: [ATLASSIAN,ROVO,JIRA,CONFLUENCE,SECURITY]
---

## Atlassian Rovo Vulnerability 🚨

**Summary:**
Attacker-controlled instructions can make Atlassian's Rovo assistant collect Jira or Confluence data that a signed-in user can access, then send it to an outside server. Two security firms discovered this vulnerability independently, but only one route has been confirmed as closed.

### Details:
- **Varonis Threat Labs** found that the `rovoChatPrompt` URL parameter could preload attacker instructions into Rovo Chat. A single click from an authenticated user was enough for Rovo to execute these instructions with the user's privileges, sending the results to an attacker-controlled server. This flaw has been named **RovoBlast** and was disclosed through Bugcrowd. Atlassian fixed this issue server-side on **July 8, 2026**.

- **PromptArmor**, an AI security firm, demonstrated that uploading a file could make Rovo gather internal data and send it out through a URL request without requiring separate approval. This indirect prompt-injection attack involves placing attacker-controlled text inside content that Rovo is asked to use. For example, a user could upload a document with concealed instructions and ask Rovo to organize their Jira tickets. Rovo would then search Jira and Confluence, appending the findings to an attacker's URL, allowing the attacker to access the ticket and page contents through their server logs.

### Implications:
PromptArmor noted that the exfiltration step does not require a separate human-in-the-loop approval, making it a significant concern. The vulnerability persists even when Rovo's web-search option is disabled, as the outbound request utilizes a separate URL-retrieval capability.

### Conclusion:
Neither issue provides customers with a patch to apply. The link flaw was addressed on Atlassian's side, but the content-borne path requires careful scoping of which apps and groups can use Rovo.

For more details, check the full article: [Read full article](https://thehackernews.com/2026/08/atlassian-rovo-can-be-tricked-into.html)