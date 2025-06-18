---
title: Is your AI safe? Threat analysis of MCP (Model Context Protocol)
date: 2025-06-16
categories: [RESEARCH]
tags: [AI,MCP,THREAT ANALYSIS,CYBERSECURITY]
---

## MCP Overview  
Who cares about MCP? You do. Or at least you should. MCP is the simplest and most actively supported method for connecting tools to your LLMs (for example, letting “Claude Desktop” access files on your local station). It was created by Anthropic and backed by industry leaders like OpenAI, Google, and others, making it a reliable choice for the long term. Now that we’ve established its importance, let’s dive into what MCP is all about.

The foundational premise of the Model Context Protocol (MCP) is that LLM performance directly correlates with the richness of provided context. While context enhancement is often associated with tools, MCP sets the path to a more sophisticated usage.

Let’s look at how the official site describes MCP:  
“MCP is an open protocol that standardizes how applications provide context to LLMs. Think of MCP like a USB-C port for AI applications.”

MCP is comprised of the following:  
1. **MCP host/application** — end user LLM application that embeds the MCP client (Cursor/Claude Desktop/etc.)  
2. **MCP client** — a library/process running inside the host, speaking JSON-RPC to the MCP server  
3. **MCP server (local/remote)** — programs that expose specific capabilities through the Model Context Protocol

Behind the scenes, MCP utilizes JSON-RPC + STDIO/HTTP+SSE. It’s a stateless, lightweight RPC protocol using JSON for requests/responses over various transports.

To read the complete article see:  
[Read more about AI safety and MCP](https://www.cyberark.com/resources/threat-research-blog/is-your-ai-safe-threat-analysis-of-mcp-model-context-protocol)  

---