---
title: NightEagle APT Targets Russian Organizations
date: 2026-09-16
categories: [CYBERSECURITY]
tags: [NIGHTEAGLE,APT,RUSSIA,CYBERSECURITY,GHOSTCONTAINER]
---

## NightEagle APT Targets Russian Organizations

Over the past year, our Global Emergency Response Team (GERT) has investigated several incidents involving the NightEagle group (APT-Q-95). This group has been active since at least 2023 and originally focused on organizations in Asia. We have now identified attacks by the group targeting businesses in Russia. This post examines both known and new tools NightEagle used in its latest campaign. In most incidents, the attackers used compromised valid credentials to gain access to corporate VPNs. VPN connections originated from IP addresses in the Russian segment linked to Cloudflare WARP tunnels, as well as from IP addresses associated with European virtual infrastructure providers.

Both during the initial access stage and as the attack progressed, the attackers deployed the **GhostContainer** backdoor on Microsoft Exchange servers. It incorporates components from several open-source projects, including the Neo-reGeorg tunnel, an exploit for the CVE-2020-0688 vulnerability, and the GhostWebShell class from the ysoserial utility. All of these components are publicly available on GitHub. The backdoor is a .NET assembly containing three classes that implement its core functionality:
- **Stub**: processes C2 commands delivered to the infected system through the x-owa-urlpostdata headers and evades detection by the Antimalware Scan Interface (AMSI) and Windows Event Log mechanisms by overwriting addresses in amsi.dll and ntdll.dll.
- **App_Web_8c9b251fb5b3**: implements network traffic redirection (proxying) and socket forwarding functionality. Kaspersky products detect the GhostContainer backdoor as Trojan.MSIL.GhostContainer.gen.

Once the attackers gain sufficient privileges during an attack, they leverage RDP to move laterally within the internal network segment. To do this, they download and run tools for tunneling and redirecting network traffic. The attackers used GitHub repositories to host their archived tools. The names of the repositories and archives were disguised to look legitimate:
- [mirror-js-webpack.zip](https://github.com/mirror-js/mirror-js/refs/heads/main/js/js-webpack.zip)
- [mirror-js-json-pack.zip](https://github.com/mirror-js/mirror-js/refs/heads/main/js/jsonp-pack.zip)
- [resource-pack.zip](https://github.com/browserthemes/resourcepack/releases/download/main/resource-pack.zip)

Across the incidents we investigated, we found two tools that the attackers combined for traffic tunneling. Microsoft dev tunnels are a legitimate Microsoft mechanism that allows local web services to be published for internet access on *.*.devtunnels.ms domains. The attackers used this tunneling capability to expose port 3389 (RDP) on the compromised system. **rdp2tcp** is a publicly available tool for tunneling TCP traffic over an established RDP connection. The combination of Microsoft dev tunnels and rdp2tcp allows the attackers to maintain network access by using legitimate services without opening additional suspicious ports. The attackers also used the **atexec** utility from the Impacket toolkit to create scheduled tasks on target systems.

To obtain elevated privileges and move laterally through the network, NightEagle exploited various vulnerabilities in Active Directory. In one incident, they exploited a well-known RDP implementation vulnerability, CVE-2019-0708 (BlueKeep). They used the vulnerable mechanism to create a local account on the system and add it to the Administrators and Remote Desktop Users groups. The attackers also requested Kerberos tickets with a non-standard combination of flags (Forwardable, Proxiable, Renewable) and attempted to replicate the Domain-Password object from the Active Directory database to impersonate the domain controller (a technique known as DCSync) after obtaining an account with sufficient privileges. Through these methods, the attackers establish persistence in the infrastructure, obtain password hashes for domain accounts, use long-lived Kerberos tickets to gain legitimate access to target resources, and ultimately compromise domain controllers and the victim's entire Active Directory infrastructure. 

To expand the geographic scope of its targets, NightEagle is updating its methods and adopting new techniques for persistence and lateral movement. Since the attackers rely on known legitimate tools and infrastructure vulnerabilities, well-configured monitoring can help detect NightEagle's presence on the network.

[Read full article](https://securelist.com/tr/nighteagle-apt-ghostcontainer-and-tunneling/121323/)\n