---
title: Security Incident – BGP Hijacking
date: 2026-08-31
categories: [SECURITY]
tags: [BGP,HIJACKING,MALWARE,VIRTUALIZOR,SECURITY]
---

## Security Incident – BGP Hijacking 🚨

The Virtualizor platform, for those unfamiliar, is a VPS management platform used by many hosting providers to deploy and manage virtual servers on KVM, Xen, LXC, OpenVZ, Proxmox, and other virtualization platforms. It is not just a tiny admin panel either. Virtualizor publicly lists hundreds of NOC partners worldwide, and according to its own documentation, a single master server can manage hundreds of virtualization nodes. This places it high up in the infrastructure.

### Incident Details

The vendor has confirmed the details of the compromise: attackers hijacked the BGP route for Virtualizor/Softaculous infrastructure, obtained a valid Let's Encrypt certificate, and used that position to serve a malicious Virtualizor update. The concerning part is that the Virtualizor update clients did not cryptographically verify the downloaded packages. Thus, the combination of BGP hijack and a valid TLS certificate was enough for the attacker code to be executed as root on affected hypervisors.

According to Virtualizor, only a small number of installations are known to have received the malicious update. However, the vendor cannot specify which ones, so they recommend treating every Virtualizor server as potentially compromised and checking it. Currently, there is no evidence that customer VPS guests themselves were modified. Still, once the hypervisor is compromised as root, everything running on it must be considered at risk.

### Recommendations

Additionally, our Nextron Research team has prepared IOCs and YARA rules for the known artifacts and payload, available at [github.com/Neo23x0/signat](https://github.com/Neo23x0/signat). The merge is done, and our internal QA pipelines are still running; the signatures should hit the update servers and THOR Cloud Lite within the next hour. Organizations running Virtualizor are advised to scan the hypervisor, not the VPS guests.

For more details, you can read the complete article here: [Read full article](https://x.com/nextronresearch/status/2094522556912947710) 

See also: [Virtualizor Security Incident Blog](https://www.virtualizor.com/blog/security-incident-bgp-hijacking/) 
