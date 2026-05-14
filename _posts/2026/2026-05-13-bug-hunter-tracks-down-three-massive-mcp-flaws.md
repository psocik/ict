---
title: Bug Hunter Tracks Down Three Massive MCP Flaws
date: 2026-05-13
categories: [SECURITY]
tags: [MCP,VULNERABILITIES,SECURITY,DATABASES]
---

## Major Security Vulnerabilities Found in MCP Servers 🚨

Security vulnerabilities in MCP servers for three popular database projects could allow attackers to execute unintended SQL statements on Apache Doris, exfiltrate sensitive metadata from Alibaba RDS, and potentially take over Apache Pinot instances exposed to the internet. 

According to Akamai security analyst Tomer Peled, Alibaba has decided not to patch its flaw in RDS MCP. MCP, or Model Context Protocol, is an open-source protocol originally developed by Anthropic that allows LLMs, AI applications, and agents to connect to external data, systems, and one another. Peled stated, "There is missing or faulty security validation between the MCP server and its back end," adding that these security gaps will become high-value targets for attackers, and we expect more of these issues to surface. 

### Details of the Vulnerabilities 🔍

1. **Apache Doris Vulnerability**: The flaw affecting Apache Doris, a high-speed analytics and search database, is CVE-2025-66335, a SQL injection vulnerability that affects Apache Doris MCP Server versions earlier than 0.6.1. When an MCP tool is called, the server's "exec_query" function fails to validate one of the five parameters (the db_name parameter) before constructing the SQL query. This means an attacker can invoke the function and inject malicious SQL through the db_name parameter. Peled noted that any attacker gaining access to a client connected to the Doris MCP server can execute arbitrary commands on the victim's Apache Doris instance. Apache issued a patch in December to fix this flaw.

2. **Apache Pinot Vulnerability**: The second issue, an authentication validation bypass in Apache Pinot MCP, can also lead to SQL injection attacks and full database takeover. The open-source project uses HTTP as the transport layer without requiring any type of authentication. In environments where the MCP endpoint is reachable externally, this behavior allows unauthenticated attackers to execute queries against the Pinot instance, potentially leading to a full remote takeover of the database. Pinot MCP v1.1.0 and earlier versions are affected.

3. **Alibaba RDS Vulnerability**: The third security flaw, an information disclosure issue in the Alibaba RDS MCP server, stems from the server not authenticating users before invoking the retrieval-augmented generation (RAG) MCP tool. The vector index may contain table names, schema definitions, or other potentially sensitive metadata, and unauthenticated attackers can exfiltrate this data with little or no effort. All versions of Alibaba RDS MCP are affected by this vulnerability. 

Peled reported the issue to Alibaba in November, but the cloud giant stated that the issue is "not applicable" for a fix. Akamai also reported this inaction to the CERT Coordination Center (CERT/CC). Peled concluded, "More attention should be given not just to the specification but also to the best security practices guides when developing secure MCP servers."

For more details, [Read full article](https://www.theregister.com/security/2026/05/13/bug-hunter-tracks-down-three-serious-mcp-database-flaws-one-left-unpatched/5238916)