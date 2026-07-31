---
title: CosmosEscape Taking Over Every Database in Azure Cosmos DB
date: 2026-07-30
categories: [CYBERSECURITY]
tags: [AZURE,VULNERABILITY,DATABASE,CYBERSECURITY,MICROSOFT]
---

## CosmosEscape: Taking Over Every Database in Azure Cosmos DB

A critical vulnerability chain in Azure Cosmos DB enabled full read and write access to every Cosmos DB database. Wiz Research uncovered **CosmosEscape**, a critical vulnerability in Azure's flagship database service, Azure Cosmos DB, via its Gremlin API. The vulnerability could have been exploited to compromise every database in the service, including Microsoft's own internal databases - potentially enabling a cross-service attack. 🚨

Through CosmosEscape, attackers could have acquired what Wiz Research dubbed the **Cosmos Master Key** - a platform-wide secret that granted two incredibly powerful capabilities: retrieving the primary key of any Cosmos DB account on demand, resulting in full read & write access, and listing all databases on the service with the ability to filter by specific organization identifiers like subscription and tenant IDs. Chained together, these capabilities could have enabled precision targeting at platform scale: from identifying a specific organization's databases to compromising them, all from publicly accessible endpoints. Cosmos DB is used internally across Microsoft; services like Microsoft Entra ID, Microsoft Teams, and Microsoft Copilot all store data in Cosmos DB. Their databases were potentially accessible via this vulnerability. 🔑

Microsoft has now fully remediated the issue, including eliminating the Cosmos Master Key. Microsoft also introduced new guardrails to Cosmos DB to prevent similar attacks. No customer action is required. Microsoft conducted a thorough investigation and found no evidence of exploitation of this vulnerability beyond the research described in this blog. ✅

Cosmos DB supports multiple query APIs, and among them is Gremlin, a popular graph query language. While running Gremlin queries against Cosmos DB, Wiz Research noticed a suspicious .NET exception. This suggested that Cosmos DB was using a custom Gremlin engine. Cosmos DB's engine translated Gremlin queries into .NET code, enforcing a set of restrictions designed to prevent queries from reaching beyond Gremlin operations. These restrictions, however, didn't sufficiently account for .NET reflection - allowing researchers to develop file read, write, and ultimately arbitrary code execution primitives, all through queries against their own database. 💻

By bypassing the Gremlin sandbox, Wiz Research gained code execution on the DB Gateway, a service that executes customer queries on their behalf, running on multi-tenant Service Fabric clusters. Through credentials available on the cluster, the DB Gateway accessed a signing key that could retrieve the requested account's primary key. Researchers soon discovered the signing key wasn't scoped to a single account. It worked across tenants, regions, and even API flavors - SQL, MongoDB, Cassandra, and Gremlin. It was a platform-wide key that could retrieve the primary key for any Cosmos DB account on the service, all through publicly accessible endpoints. Wiz Research dubbed it the **Cosmos Master Key**. 🔍

For more details, check out the full article: [Read full article](https://www.wiz.io/blog/cosmosescape-taking-over-every-database-in-azure-cosmos-db)