---
title: Hackers Attempt to Turn ComfyUI Servers Into Cryptomining Proxy Botnet
date: 2026-04-06
categories: [CYBERSECURITY]
tags: [HACKERS,COMFYUI,CRYPTOMINING,BOTNET,MALWARE]
---

## Hackers Attempt to Turn ComfyUI Servers Into a Cryptomining Proxy Botnet 🚨

Censys ARC has uncovered an active campaign targeting Internet-exposed ComfyUI instances. Attackers are exploiting the custom node ecosystem to achieve Remote Code Execution (RCE) on unauthenticated deployments, with over 1,000 instances currently visible online. A specialized Python scanner continuously sweeps major cloud IP ranges for vulnerable targets, automatically installing malicious nodes via ComfyUI-Manager if no exploitable node is already present.

### Key Findings:
- **Compromised Hosts:** Enrolled into a cryptomining operation (Monero via XMRig, Conflux via lolMiner) and a Hysteria v2 proxy botnet, both managed through a Flask-based C2 dashboard.
- **Malware Techniques:** The malware (ghost.sh) employs evasion and persistence techniques, including fileless execution and kernel-thread process masquerading.
- **Re-infection Mechanisms:** The scanner introduced two backdoors: a disguised "GPU Performance Monitor" node that re-downloads the payload every 6 hours, and a poisoned default startup workflow.

ComfyUI is a graphical, node-based interface for running Stable Diffusion and other AI image generation models, making it an attractive target for attackers. The same GPUs used for image generation can be repurposed for cryptocurrency mining when idle. Many deployments run on cloud infrastructure and are often exposed to the Internet without authentication, creating a straightforward path for compromise.

### Exploitation Framework:
The scanner.py functions as both a scanner and an exploitation framework. Once a ComfyUI instance is identified, it attempts to execute attacker-controlled code. This is facilitated by ComfyUI's custom node ecosystem, which allows raw Python code execution. The scanner looks for specific custom node families known to support arbitrary code execution.

If no target nodes are present, the scanner checks for ComfyUI-Manager and installs a vulnerable node package if available. The pip install strategy has been enhanced to try multiple methods for each package.

For more details, see the complete article: [Read full article](https://censys.com/blog/comfyui-servers-cryptomining-proxy-botnet/)