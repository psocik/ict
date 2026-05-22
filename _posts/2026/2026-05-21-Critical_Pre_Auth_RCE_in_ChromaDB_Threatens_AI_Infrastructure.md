---
title: Critical Pre-Auth RCE in ChromaDB Threatens AI Infrastructure
date: 2026-05-21
categories: [CYBERSECURITY]
tags: [CHROMADB,VULNERABILITY,AI,SECURITY]
---

## Critical Pre-Auth RCE in ChromaDB Threatens AI Infrastructure 🚨

A max-severity vulnerability (CVE-2026-45829, CVSS 10.0) has been disclosed affecting **ChromaDB**, the widely used open-source vector database for AI applications. This vulnerability allows attackers to achieve unauthenticated remote code execution via a logic flaw in the Python FastAPI server's authentication flow. Due to the potential for full server compromise, **immediate mitigation** is required for all internet-facing deployments.

### Vulnerability Details
The issue originates from ChromaDB's FastAPI server component, where user-controlled embedding function configuration is processed before authentication checks occur. This leads to pre-authentication code execution. By sending a crafted HTTP POST request to the collection creation endpoint with a malicious HuggingFace model reference (with trust_remote_code enabled), attackers can force the server to download and execute arbitrary Python code before the request is rejected as unauthorized. **No authentication is required** to exploit this issue.

### Affected Components
The following components are affected:
- ChromaDB Python FastAPI server, versions 1.0.0 through 1.5.8.

ChromaDB is a core component in many AI and machine learning pipelines, used as a vector database and retrieval backend in agentic AI applications, RAG (Retrieval-Augmented Generation) systems, and semantic search services. With approximately **14 million monthly PyPI downloads**, ChromaDB has a substantial footprint in enterprise AI deployments. Approximately **73% of internet-exposed ChromaDB instances** are running vulnerable versions according to Shodan-based scanning data.

### Recommendations
Users should upgrade to ChromaDB version 1.5.9 or later and verify the patch status. Organizations running the Python FastAPI server should immediately evaluate whether their deployments are internet-facing and take the following steps:
- Switch to the Rust-based frontend, which is not affected by this vulnerability.
- Restrict network access to ChromaDB API ports to trusted clients only.
- Avoid exposing the Python API server to the public internet.
- Scan all ML model artifacts before runtime execution.
- Treat external model references as untrusted code sources.

For more detailed technical analysis, see the [full article](https://orca.security/resources/blog/chromadb-pre-auth-rce-vulnerability/).