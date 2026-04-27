---
title: Microsoft Entra Agent ID Flaw Enabled Tenant Takeover via Privilege Escalation
date: 2026-04-26
categories: [CYBERSECURITY]
tags: [MICROSOFT,VULNERABILITY,CYBERSECURITY,PRIVILEGE-ESCALATION]
---

## Microsoft Entra Agent ID Flaw 🚨

A critical flaw in the Microsoft Entra Agent ID has been identified, allowing privilege escalation and tenant takeover via Service Principal abuse. This vulnerability was discovered by cybersecurity researchers at Silverfort and has since been patched by Microsoft.

### What Happened?

The Microsoft Entra Agent ID is an identity and authorization framework designed to give AI agents their own identities. However, researchers found that the directory role known as the Agent ID Administrator had a dangerous scope gap. This role was intended to manage agent-related objects but could modify nearly any Application Service Principal within a tenant.

### Attack Methodology 🔍

During an attack, a user with the Agent ID Administrator role could enumerate accounts with elevated permissions using the Microsoft Graph API or Azure CLI. They specifically targeted Service Principals with high-impact Graph permissions. By exploiting the role, they could add themselves as an owner of a non-agent Service Principal, allowing them to perform 'credential injection' and authenticate as that Service Principal.

### The Impact 🌍

This technique represents a significant form of Privilege Escalation, granting attackers total control over the tenant. Silverfort's researchers demonstrated this risk by hijacking a Global Administrator account, showcasing the potential for widespread damage. Approximately 99% of business networks have at least one privileged Service Principal, making this flaw particularly concerning.

### Response from Microsoft 🛡️

Silverfort discovered the flaw on February 24, 2026, and reported it to Microsoft Security Response Center (MSRC) on March 1. Microsoft confirmed the vulnerability on March 26, and by April 9, a full fix was implemented across all cloud environments, preventing the Agent ID Administrator role from managing owners of regular, non-agent Service Principals.

### Recommendations ✅

Companies are urged to check AuditLogs for any changes to account ownership or the creation of new secrets on sensitive accounts to ensure their security.

For more details, read the complete article here: [Read full article](https://hackread.com/microsoft-entra-agent-id-flaw-tenant-takeover/)