---
title: Someone Is Scanning for Your MCP Servers and AI Assistant Credentials
date: 2026-07-13
categories: [SECURITY]
tags: [MCP,AI,SECURITY,SCANNING]
---

## 🚨 Alert: Scanning for MCP Servers and AI Credentials

Someone is systematically searching for **Model Context Protocol (MCP)** servers, AI assistant configuration files, and locally exposed **LLM** endpoints. This scanning activity includes a new category that hasn't been documented before. The MCP handshakes, LLM API probes, AI assistant secret fishing, and MCP config files together account for roughly **200 requests**. The MCP protocol handshake category originated from **49 distinct source IPs**, indicating a broad, distributed scan.

### What You Need to Know

The **POST /mcp** probes were notably different. Each request contained a valid **JSON-RPC 2.0** body performing a Model Context Protocol initialize call. For example:

```json
Content-Type: application/json {"id":1,"jsonrpc":"2.0","method":"initialize", "params":{"capabilities":{}, "clientInfo":{"name":"client","version":"0"}, "protocolVersion":"2025-03-26"}}
```

This is significant because the scanner is not just blindly requesting a URL; it is actively communicating using the protocol. If your server responds to that initialize call, the next steps involve enumerating the tools the server exposes, the data sources it connects to, and whatever it can be convinced to do. An MCP server acts as a bridge that allows an AI agent to access tools and read data sources. An exposed and unauthenticated MCP server poses a severe risk, as it provides a remote, machine-readable menu of everything an agent can access, available to anyone who completes the handshake.

### Additional Threats

Scanners are also aggressively fishing for configuration and credential files belonging to AI coding assistants. When developers accidentally deploy these files to a web root, they can leak sensitive information. The paths requested were specific and current, indicating a well-informed campaign:
- `GET /.cursor/mcp.json`
- `GET /.cursor/mcp_config.json`
- `GET /.vscode/mcp.json`
- `GET /.mcp/config.json`
- `GET /.claude/settings.local.json`
- `HEAD /.claude/.credentials.json`
- `HEAD /.config/claude/.credentials.json`

The use of **HEAD** for credential files signals a mature campaign rather than a one-off curiosity probe. The AI assistant credentials are now treated as just another cloud credential worth harvesting.

### Recommendations

To check your own hosts, search access logs for **POST /mcp** and **/sse**. If you do not run an MCP server, any such request is purely reconnaissance and a useful indicator to block. If you do run one, ensure it requires authentication and is not accessible from the internet. Additionally, confirm that no `.claude/`, `.cursor/`, `.vscode/mcp.json`, or `.credentials.json` files are served by your web server. From outside your network, request **/v1/models** and **/api/tags** against your hosts. If either responds, you have an unauthenticated model exposed.

### Conclusion

The scanning confirms that someone else is already aware of your vulnerabilities. Your attack surface has expanded with the adoption of AI agents, and the scanners are actively searching for weaknesses.

[Read full article](https://isc.sans.edu/forums/diary/Someone%20Is%20Scanning%20for%20Your%20MCP%20Servers%20and%20AI%20Assistant%20Credentials/33150/)