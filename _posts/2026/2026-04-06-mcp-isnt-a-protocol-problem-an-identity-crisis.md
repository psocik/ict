---
title: MCP Isn't a Protocol Problem An Identity Crisis
date: 2026-04-06
categories: [SECURITY]
tags: [MCP,IDENTITY,SECURITY,VULNERABILITY]
---

## MCP Isn't a Protocol Problem: An Identity Crisis

Microsoft released a patch on March 10, 2026, for CVE-2026-26118, a server-side request forgery (SSRF) vulnerability in the Azure MCP Server. This vulnerability allows an authorized attacker to increase their network privilege. An attacker can exploit this because the MCP server can be manipulated into making outbound requests that contain its managed identity token. If an attacker captures this token, they will gain access to all the permissions that the server's identity can reach. 

The Model Context Protocol (MCP), used by Microsoft, Google, Amazon, and many other frameworks for AI agents, was developed to create a standardized way for agents to communicate with external tools and data. It is now the connective tissue of the agentic enterprise, and it ships with no authentication enabled by default. MCP's security flaw is not a protocol flaw; it is an identity flaw. 🚨

Adversa AI reported this month that nearly 38% of the 500-plus MCP servers it scanned lack authentication. Knostic's previous research identified 1,862 MCP servers that are accessible over the Internet with no identity governance controls in place. In a typical MCP interaction, a human user asks an AI agent to perform some activity. To accomplish this task, the agent will connect to an MCP server to access a tool or data source. At that time, the human user's identity disappears. The MCP server recognizes a request coming from an authenticated agent using a static API key or service account. It does not recognize the human user's identity or understand what the human user authorized the agent to do or the scope of that authority. 

This is the same basic pattern behind the Google Antigravity incident in December 2025, where an agent deleted a user's entire D: drive while clearing out a cache, and the Replit incident, where an agent deleted a production database that it determined was obsolete. In both cases, the agent technically had the authorization to take the action. What was missing was the link between the agent's actions and the human who authorized them. MCP makes this problem structural: each server interface creates a trust boundary, and the human identity is dropped. 

To solve this, propagating the initiating user's identity throughout each agent action is crucial. Each time the agent communicates with another system or resource, it would carry the original user's claims. The user's session scope would be enforced for each task. Each action taken by an agent is tied back to a specific human, session, and context. This traceability is what governance really needs. MCP, as it is currently deployed, breaks the traceability chain at each server boundary. 

To address this, implement OAuth On-Behalf-Of flows for every MCP server connection. Microsoft's ISE team has published a production-ready implementation of OAuth 2.1 and OBO flows. Additionally, treat the discovery of MCP servers as an identity governance problem. Noma Security's research indicates that more than 90% of organizations deploy MCP servers with default configurations that allow all tools to be used, including potentially destructive ones. If your security team cannot provide an inventory of every MCP server, the identities those servers use, and the tools they expose, then you have an unmanaged attack surface. 

Third, log the reasoning chain alongside the identity chain. Gartner predicts that by 2028, 25 percent of enterprise breaches will involve AI agents. These breaches will not occur due to advanced prompt injection attacks. They will occur for the most obvious reason: an agent used credentials that nobody could trace back to a human. 

[Read full article](https://www.scmagazine.com/perspective/mcp-isnt-a-protocol-problem-its-an-identity-crisis-nobody-is-treating)