---
title: Atlassian Rovo Can Be Tricked Into Sending Jira and Confluence Data to Attackers
date: 2026-08-08
categories: [SECURITY]
tags: [ATLASSIAN,ROVO,JIRA,CONFLUENCE,SECURITY]
---

## Atlassian Rovo Vulnerability 🚨

**Summary:**
Attacker-controlled instructions can make Atlassian's Rovo assistant collect Jira or Confluence data that a signed-in user can access, then send it to an outside server. Two security firms discovered this behavior independently through different methods. Only one of those methods has been confirmed as closed.

**Details:**
Varonis Threat Labs found that the rovoChatPrompt URL parameter could preload attacker instructions into Rovo Chat. This means that a single click from an authenticated user was enough for Rovo to execute these instructions with that user's privileges, sending the results to an attacker-controlled server. Varonis has named this flaw **RovoBlast** and disclosed it through Bugcrowd. The issue was fixed server-side by Atlassian on July 8, 2026.

PromptArmor, another AI security firm, discovered that simply uploading a file could make Rovo gather internal data and send it out via a URL request without needing separate approval. This method is an indirect prompt-injection attack, where attacker-controlled text is embedded in content that Rovo is asked to use. In their example, a user uploads a document with concealed instructions and asks Rovo to organize their Jira tickets. Rovo then searches Jira and Confluence, appends the findings to an attacker's URL, and opens it, allowing the attacker to access ticket and page contents from their server logs.

**Key Points:**
- The interaction is not entirely zero-click; the victim must expose Rovo to the malicious content and make a normal request.
- PromptArmor noted that disabling Rovo's web-search option did not prevent the attack, as the outbound request utilized a separate URL-retrieval capability.
- The root cause is that nothing checks whether the URL being opened was constructed by the agent itself.

**Conclusion:**
Neither issue provides customers with a patch to apply, as the link flaw was addressed on Atlassian's side, and the content-borne path relies on scoping which apps and groups can use Rovo.

For more details, check the full article here: [Read full article](https://thehackernews.com/2026/08/atlassian-rovo-can-be-tricked-into.html)