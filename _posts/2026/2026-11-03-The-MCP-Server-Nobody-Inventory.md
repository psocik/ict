---
title: The MCP Server Nobody Inventoried
date: 2026-11-03
categories: [SECURITY]
tags: [MCP,GITLAB,CVE,SECURITY,VULNERABILITY]
---

## The MCP Server Nobody Inventoried

**CVE-2026-61560** is a critical flaw in a popular community-built Model Context Protocol (MCP) server for GitLab. MCP servers are the connectors that let AI assistants act on other systems. This one, the open-source @zereight/mcp-gitlab package, exposes more than 100 tools that read and change GitLab projects. To do that, it holds a GitLab personal access token. Whatever the token can do, the server can do.

Before version 2.1.27, running the server in its network mode (SSE) meant its `/sse` and `/messages` endpoints accepted requests from anyone who could reach the port. No password, no token. The project's docker-compose file published that port on every network interface, and the container ran as root. One of the tools, `upload_markdown`, would read any file path it was given. Point it at `/proc/self/environ` and it returned the server's environment, including the GitLab token in plain text. From there, an attacker can reach every repository, CI/CD variable, and deploy key the token owner can. The CVE carries a CVSS score of **9.8**. None of this required a sophisticated attacker.

MCP servers usually arrive through the side door. It skips change control because it looks like a developer tool, not infrastructure. It never reaches the asset inventory because nobody registered it. And the token it holds is often the developer's own, with far more access than any single task needs. It holds credentials like a service account and listens like a server, but it gets the scrutiny of a browser extension. The maintainer shipped a solid fix on **June 22, 2026**, after a report from researchers @gil-maman-p and @hodaya-prz. But the CVE record wasn't published until **Sept. 15**. Any tool that matches on CVE identifiers had nothing to match for about **12 weeks**. If your process waits for a CVE before it acts, it waited too.

This isn't one careless project. MCP's official SDKs have needed their own transport fixes this year: the Go SDK accepted cross-site requests without checking their origin (CVE-2026-33252), and the Ruby SDK lacked DNS-rebinding protection (CVE-2026-63118). The current MCP specification, revised in **July 2026**, still says authorization is optional. Defaults have favored getting started over staying safe. Even the fixed gitlab-mcp keeps an escape hatch, an environment variable literally named `SSE_DANGEROUSLY_ALLOW_UNAUTHENTICATED_REMOTE`. Someone, somewhere, will set it to make a demo work.

### What Should Teams Do?
1. **Find them.** Every MCP server gets an owner, a list of the tokens it holds, and a record of where it listens.
2. **Scope the tokens.** Use the narrowest token the platform allows, give it an expiry date, and rotate it when the server changes hands.
3. **Watch releases.** For the MCP packages you depend on, subscribe to the repositories' security advisories and release notes.

On the detection side, the check is simple: an MCP transport that answers on a non-loopback interface without asking for credentials is a finding, whatever version it runs, and is worth building into scanning for every MCP server.

[Read full article](https://www.scworld.com/perspective/the-mcp-server-nobody-inventoried)