---
title: GitHub-native Command-and-Control Framework OctoC2 Released
date: 2026-07-18
categories: [SECURITY]
tags: [GITHUB,SECURITY,RESEARCH,FRAMEWORK]
---

## Exciting Release: OctoC2 🚀

A new **GitHub-native command-and-control framework** called **OctoC2** has been released for authorized security research, featuring encrypted multi-channel transport and resilient failover. It is critical that OctoC2 be used only on systems and repositories an operator owns or has explicit permission to test. Operators must use private test infrastructure, least-privilege credentials, trusted TLS, and private listener bindings.

### Key Features:
- **TypeScript beacon**
- **Durable controller**
- **Local operator dashboard**
- **CLI**

OctoC2 combines a TypeScript beacon, durable controller, local operator dashboard, and CLI. GitHub-backed and direct transports share one signed task protocol, one identity model, and the same result-ownership rules. OctoC2 can exchange the same task protocol through several environment-specific paths, including GitHub artifacts such as Issues, branches, Actions variables, deployments, Gists, repository variables, steganographic PNGs, and Git Notes. Direct controller paths involve HTTPS/WebSocket, gRPC with mTLS, and GitHub Actions OIDC.

### Security Principles 🔒
Every transport uses the canonical contracts in shared/. The controller persists identities, credentials, tasks, results, delivery leases, replay records, and channel cursors in SQLite. The beacon persists its Ed25519 identity and task ledger so a delivered task cannot be executed twice after a restart. The framework incorporates strong security principles: Network listeners are opt-in and loopback-first. HTTP is TLS-only; gRPC requires mTLS and a per-beacon bearer credential. Beacon identities use provisioned Ed25519 signing keys distinct from X25519 encryption keys. Tasks and results are signed, identity-bound, and ownership-checked. Exclusive delivery leases prevent competing transports from claiming one task simultaneously. Durable replay state and the beacon task ledger survive restarts. GitHub App private keys and recovery signing secrets remain server-side. Unsigned remote module execution is rejected across the public surfaces.

### Operational Boundaries ⚠️
Controller listeners remain disabled until explicitly enabled. Repository permissions are still an operational boundary: a broad repository writer may delete, delay, or reorder artifacts even when it cannot forge their authenticated contents. Separate repositories and narrowly scoped credentials provide stronger isolation.

To read the complete article see: [Read full article](https://github.com/dstours/OctoC2)