---
title: Operation Highland Uncovering Velvet Ant's Intrusion
date: 2026-06-15
categories: [CYBERSECURITY]
tags: [OPERATION HIGHLAND,VELVET ANT,CYBERSECURITY,INTRUSION DETECTION]
---

## Operation Highland: Uncovering Velvet Ant's Intrusion

When Sygnia's IR team began reconstructing the intrusion that would become known as **Operation Highland**, they discovered that the earliest forensic artifacts dated back to **2016**. What they uncovered was not a recent breach but a near-decade of undetected presence inside an internal network - a network the attacker had no direct path into, yet managed to infiltrate. 

**Velvet Ant** is a China-nexus threat actor that Sygnia has tracked across multiple investigations, including their recent exploitation of **CVE-2024-20399**, a zero-day in Cisco NX-OS. The pattern across all these investigations is consistent: Velvet Ant escalates when detected, pivots to less-monitored infrastructure, and rebuilds persistence from a new vantage point. 

Operation Highland is distinct in one critical respect: the target network had no direct internet connectivity. Instead, the attacker engineered a deliberate multi-stage access chain to reach it. PAM modules and OpenSSH binaries were replaced with backdoored versions across multiple hosts - the attacker controlled the full authentication stack. 

### Stages of Intrusion
Velvet Ant's path into the environment followed three distinct stages:
1. **Establishing persistent access** on internet-facing systems.
2. **Pivoting through the IT network** toward the critical infrastructure segment.
3. **Subverting the authentication stack** to embed long-term persistence across compromised hosts.

For initial access, Velvet Ant deployed a modified version of **GS-Netcat** on internet-facing servers to establish a reverse shell connection to a remote C2 server. The binary was named **auditdb** and placed in `/usr/sbin/` to blend in with legitimate system utilities. To evade detection, the binary overwrites its own `argv[0]` parameter with `[khubd]`, disguising its presence in process listings by masquerading as a legitimate kernel thread. 

To maintain persistence on newer servers running **systemd**, a malicious unit file was placed in `/lib/systemd/system/`, disguised as a Chrome service. On older servers using **SysVinit**, a malicious execution line was appended to existing startup scripts in `/etc/init.d/`. Alongside GS-Netcat, Velvet Ant deployed a network tunneling tool, a custom implementation of the publicly available **ssspl** project, modified to function as a **SOCKS5 proxy server**. To evade detection, Velvet Ant manipulated the `argv[0]` parameter, disguising the process name as **smbd -D**. 

### Additional Entry Vectors
Velvet Ant exploited an internet-facing **Nginx** server as an additional entry vector. They modified its configuration to proxy any incoming request to a specific URL through to the same URL on a backend server. This **FastCGI wrapper** acted as an execution bridge: it processed requests to the specified URL, executed the binary named **uptime**, and returned its output to the threat actor via Nginx. The uptime binary was a custom-built tool designed to establish an SSH connection to a server in the critical infrastructure network, based on HTTP POST parameters sent in the request. 

By chaining these modifications, Velvet Ant established a remote-execution path into the segregated environment via simple HTTP requests, with no direct connection to the critical infrastructure network ever required. The attack extended into controlling how authentication works across the environment. Both PAM and OpenSSH were modified, giving the attacker visibility into credentials as they were used, and the ability to bypass normal authentication flows entirely. 

During the investigation, nine files of a backdoored **pam_unix.so** were identified. Velvet Ant replaced the legitimate PAM module with maliciously modified versions. In the modified versions, the **pam_sm_authenticate** function was patched to either accept a hardcoded backdoor password, harvest credentials from legitimate authentication attempts, or both. The modified SSH binaries included a custom flag to disable their own credential logging - the attacker actively managed their forensic footprint during live operations, a hallmark of high OpSec discipline. 

To read the complete article see: [Read full article](https://www.sygnia.co/blog/operation-highland-velvet-ant/)