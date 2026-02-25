---
title: Beware of Fake 7-Zip Downloads Turning PCs into Proxy Nodes!
date: 2026-02-09
categories: [CYBERSECURITY]
tags: [MALWARE,7-ZIP,PROXY,CYBERSECURITY]
---

## 🚨 Beware of Fake 7-Zip Downloads! 🚨

A convincing lookalike of the popular 7-Zip archiver site has been serving a trojanized installer that silently converts victims’ machines into residential proxy nodes—and it has been hiding in plain sight for some time. This experience illustrates how a seemingly minor domain mix-up can result in long-lived, unauthorized use of a system when attackers successfully masquerade as trusted software distributors.

### 🛠️ How It Works
The operators behind 7zip[.]com distributed a trojanized installer via a lookalike domain, delivering a functional copy of the 7-Zip File Manager alongside a concealed malware payload. The installer is Authenticode-signed using a now-revoked certificate issued to Jozeal Network Technology Co., Limited.

In parallel, three additional components are silently dropped:
- **Uphero.exe**: A service manager and update loader.
- **hero.exe**: The primary proxy payload (Go-compiled).
- **hero.dll**: A supporting library.

All components are written to `C:\Windows\SysWOW64\hero\`, a privileged directory. An independent update channel was also observed, indicating that the malware payload can be updated independently.

### 🔍 Key Concerns
While initial indicators suggested backdoor-style capabilities, further analysis revealed that the malware’s primary function is proxyware. The infected host is enrolled as a residential proxy node, allowing third parties to route traffic through the victim’s IP address. The **hero.exe** component retrieves configuration data from rotating “smshero”-themed command-and-control domains, then establishes outbound proxy connections on non-standard ports.

Traffic analysis shows a lightweight XOR-encoded protocol (key 0x70) used to obscure control messages.

One of the more concerning aspects of this campaign is its reliance on third-party trust. The Reddit case highlights YouTube tutorials as an inadvertent malware distribution vector, where creators incorrectly reference 7zip.com instead of the legitimate domain.

### ⚠️ What You Should Do
Any system that has executed installers from 7zip.com should be considered compromised. Users and defenders should:
- Verify software sources.
- Treat unexpected code-signing identities with skepticism.
- Monitor for unauthorized Windows services and firewall rule changes.
- Block known C2 domains and proxy endpoints at the network perimeter.

Indicators of Compromise include file paths such as:
- `C:\Windows\SysWOW64\hero\Uphero.exe`
- `C:\Windows\SysWOW64\hero\hero.exe`
- `C:\Windows\SysWOW64\hero\hero.dll`

Observed network indicators include domains like:
- `soc.hero-sms[.]co`
- `neo.herosms[.]co`
- `pulse.herosms[.]cc`

For more detailed information, check out the full article here: [Read full article](https://www.malwarebytes.com/blog/threat-intel/2026/02/fake-7-zip-downloads-are-turning-home-pcs-into-proxy-nodes)