---
title: Multi-Functional Linux Botnet "Evooo1Bot"
date: 2026-08-13
categories: [CYBERSECURITY]
tags: [LINUX,BOTNET,MALWARE,CYBERSECURITY]
---

## Multi-Functional Linux Botnet "Evooo1Bot" 🚀

FortiGuard Labs has been tracking a previously undocumented Linux botnet family, which we have named **Evooo1Bot**. The name derives from the hardcoded string "evooo1" found in every binary. While the malware reuses the DDoS engine from the publicly leaked Mirai source code, it extends the original framework with numerous capabilities, including:

- **Encrypted C2 communications**
- **SSH brute-force scanner**
- **SOCKS relay module**
- **Credential sniffer**
- **Integrated exploit arsenal** targeting multiple known vulnerabilities.

Telemetry from its command-and-control infrastructure indicates that Evooo1Bot has been actively targeting Internet-facing devices since **July 2026**, exploiting multiple vulnerabilities across diverse regions.

Evooo1Bot came to our attention through FortiGuard IPS telemetry. Researchers observed active exploitation attempts targeting a range of edge devices, with all payload callbacks pointing to the same loader URL at `91.92.40.[REDACTED]/wget.sh`. The following vulnerabilities were observed being exploited across the captured traffic:

- **CVE-2007-3010**: Alcatel OmniPCX Enterprise Remote Code Execution Vulnerability
- **CVE-2016-6277**: NETGEAR Multiple Routers Remote Code Execution Vulnerability
- **CVE-2018-14558**: Tenda AC7, AC9, and AC10 Routers Command Injection Vulnerability
- **CVE-2019-14931**: Mitsubishi Electric Europe B.V. ME-RTU devices and INEA ME-RTU devices remote Command Injection vulnerability
- **CVE-2020-10987**: Tenda AC1900 Router AC15 Model Remote Code Execution Vulnerability
- **CVE-2021-46422**: Telesquare SDT-CW3B1 Command Injection vulnerability
- **CVE-2022-37055**: D-Link Routers Buffer Overflow Vulnerability
- **CVE-2024-29269**: Telesquare TLR-2005KSH Command Injection Vulnerability
- **CVE-2025-10123**: D-Link DIR-823X Command Injection Vulnerability
- **CVE-2025-55583**: D-Link DIR-868L B1 router Command Injection Vulnerability

The loader script `wget.sh` downloads and executes a botnet binary that matches the host's CPU architecture. Each exploitation attempt carries a campaign label embedded in the download command (for example, **-s mitsu** for Mitsubishi Electric targets and **rep.alcatel** for Alcatel-Lucent targets), indicating that the operator independently tracks per-vulnerability infection yield. The loader script downloads 12 binary variants using `wget`, `busybox wget`, `curl`, or `tftp`, in that order. The binary is written to a temporary path, made executable, and executed. Bash history is cleared post-infection. Additionally, static strings in Evooo1Bot are protected by a multi-layer pipeline applied at compile time. The AES and ChaCha20 keys are not stored directly in the binary. Each key is split into two 32-byte constants embedded in **.data** and combined at runtime via XOR.

For more details, check out the full article: [Read full article](https://www.fortinet.com/blog/threat-research/multi-functional-linux-botnet-evooo1bot)