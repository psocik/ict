---
title: Unpatched Tailscale SSH Flaws Could Let a Hacked Device Reach Root on Other Servers
date: 2026-10-25
categories: [SECURITY]
tags: [TAILSCALE,SSH,SECURITY,VULNERABILITY]
---

## Unpatched Tailscale SSH Flaws Could Let a Hacked Device Reach Root on Other Servers

A single hacked device on a Tailscale network can be used to gain root access to other servers it can reach, according to a security researcher who published the findings this week. 🚨

The attack requires two things: Tailscale SSH set up to allow port forwarding, and an attacker who already controls one device that the network's access rules permit to connect to the target. The findings were published on October 25 in a report called **Tailworm** by Erica Windisch of Cyberdione Labs. Windisch tested Tailscale version 1.104.2 and headscale version 0.29.5. As of publication, Tailscale had issued no security bulletin, no CVE identifier, and no fixed version. Tailscale has responded in public, with Mike Shaver, the company's vice president of engineering, writing that Tailscale had received the report, had already been looking at the same areas, and had found issues it is working to fix. Shaver added that the company is still working out which setups are affected.

Tailscale SSH does not work like a normal SSH server; rather than checking a connecting user's password or key, it identifies the device, and a single access rule decides whether that device may open an SSH session to a target. Because of this, the attack needs no stolen passwords or keys. It needs a foothold on one device first, which the report says an attacker can get through the usual ways: a vulnerable web application, a poisoned software package, phishing, or stolen login details. 

In the lab, Windisch showed the problem in stages. Using standard SSH port forwarding, an ordinary session caused the root-level Tailscale process to connect to a system socket that only root should access, and the test gained root and read the system password file almost immediately, without administrator rights. Additionally, a third method defeated a safety check by racing the system, capturing a key used to enroll new devices and using it to join an attacker's own machine to the network as a trusted server. This last step worked from start to finish only on networks where Tailscale's Tailnet Lock feature was not enabled. Windisch describes the overall result as "wormable." In the lab, one compromised device could spread to every device that the access rules allow, with no passwords, no stolen keys, and no user action, in under a second per step. The report states, "the mesh converts one ordinary foothold into fleet-wide privileged access at machine speed."

For headscale version 0.29.5, forwarding cannot be turned off at all, so every SSH grant there should therefore be treated as giving root on the target.

Because there is no patch, available steps involve changes to how Tailscale SSH and related features are set up. Administrators should review Tailscale SSH access rules, writing them as single source-to-destination pairs that name one device and one target, and remove broad rules that grant access by identity or tag. The report calls per-pair rules the one control that stopped the spread in testing. Turn off SSH port forwarding where possible; on Tailscale's hosted service this is a per-rule setting. Remove app connector permissions from devices that do not need them, and remove any tailscale serve forward that points at a Unix socket. Turn on node-key expiry, so a stolen device key does not stay valid forever. If a device is compromised, delete it at the control plane. Tailscale also suggests enabling SSH check mode, which adds a login step, but does not fix the privilege escalation.

The SSH problem is one of 11 findings in the report, which also covers Tailscale's app connectors. The app connector finding, in an experimental feature called conn25, lets a permitted user send traffic to destinations the security team never approved, including a cloud provider's metadata service.

[Read full article](https://thehackernews.com/2026/10/unpatched-tailscale-ssh-flaws-could-let.html)