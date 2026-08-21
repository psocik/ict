---
title: Rust Supply Chain Attack on arrayref Significant Overlap with DPRK Campaigns
date: 2026-08-20
categories: [CYBERSECURITY]
tags: [RUST,SUPPLY CHAIN,DPRK,CYBERSECURITY,MALWARE]
---

## Rust Supply Chain Attack on arrayref 🚨

On **August 20, 2026**, malicious versions of the `arrayref` Rust crate and others executed a backdoor at compile time. This campaign's infrastructure overlaps with recent DPRK supply chain attacks, including **Mastra** and **axios**.

### Key Details:
- Malicious versions of three Rust crates were published to crates.io: `arrayref@0.3.10`, `internment@0.8.7`, and `append-only-vec@0.1.9`.
- A typosquatted dependency (`proc-macro1`) was added, which downloads and executes a remote binary during the build process.
- The Rust Security Response Team has since deleted these malicious versions and locked the account, suspecting that the maintainer's machine or credentials were compromised.

### Impact:
The impacted package versions add a malicious dependency to the `Cargo.toml`:
```toml
[dependencies]
proc-macro1 = "1.0.107"
```
This dependency is a typosquat of the legitimate `proc-macro2` crate, which has over 154 million downloads. The malicious logic in its `build.rs` triggers the payload during compilation, leading to significant risks for developers.

### Backdoor Features:
The implant is a feature-rich backdoor that:
- Beacons to C2 via HTTPS POST (to the endpoint `/49890878`).
- Exfiltrates host info and stolen credentials as Base64-encoded JSON.
- Collects sensitive information such as hostname, username, and operating system details.
- Supports commands for termination, reconfiguration, persistence installation, and script execution.

### Conclusion:
The `arrayref` infrastructure shows substantial overlap with operations attributed to recent North Korean actors. The payloads beacon to `/49890878`, which has been linked to the Mastra campaign. This incident highlights the ongoing threat posed by sophisticated supply chain attacks.

For more details, read the full article here: [Read full article](https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns)