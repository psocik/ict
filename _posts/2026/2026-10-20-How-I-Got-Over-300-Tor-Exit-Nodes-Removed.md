---
title: How I Got Over 300 Tor Exit Nodes Removed
date: 2026-10-20
categories: [CYBERSECURITY]
tags: [TOR,MALWARE,SSH,SECURITY]
---

## How I Got Over 300 Tor Exit Nodes Removed

On Friday, Oct 2, at 09:35 AM, **333 infected exit nodes** started a coordinated campaign to intercept SSH connections and gather as much unencrypted data as possible. To give you a sense of scale, all of Tor has around **3000 exit relays**, so roughly **10%** were under their control. The attackers had gained access to the servers two months earlier, in August, and quietly deployed their **Ebury 1.8.3** payload (an OpenSSH backdoor and credential stealer for Linux).

The attack appears to have had two primary goals:
- Gather as much unencrypted mail traffic as possible
- Intercept SSH connections (MITM)

If you happen to get a circuit that exits over one of those **333 infected exit nodes**, you won't notice anything at first. Encrypted web traffic is forwarded as usual, but if you attempt an SSH connection over Port 22, you're unknowingly redirected to one of **12 SSH interception servers**. But if you ignore the warning and go ahead with the login, the attacker does three things:
1. Steals your password
2. Opens a connection to your server and observes each command you type (MITM)
3. Opens a second connection to your server and infects it with Ebury.

On Friday evening, I contacted the **Tor Project's network health team** with my findings. They confirmed this was something new and got to work by contacting the affected relay operators. 
- **Fri Oct 2:** Interception started.
- **Sun Oct 4:** The Tor network health team made an announcement to the operators, who began shutting their exit nodes down.
- **Sun Oct 4:** The relays were marked **BadExit**, so clients would no longer use them to exit traffic.
- **Mon Oct 5:** All infected servers were shut down, partly by the operators and partly by the attackers. In their announcement, the health team described the pattern: "It seems the attacker is gaining access to Linux-based hosts and when these machines are running non-exits, they are editing the torrc file and turning them into exits to be able to carry out the SSH attack."

Using **exitmap**, I built a simple script that did the following: it pinned an exit node, then opened an SSH connection from my server A to my server B. Server A checked whether it received the correct SSH fingerprint from server B. Server B checked whether the connection came from the pinned exit node or from one of the **12 SSH interception servers**. Around a dozen served a fake fingerprint, and over **300** didn't intercept anything but redirected through those same interception servers. Redirecting alone was enough to confirm the exit was infected. In some further analysis, I used **sshesame** as a honeypot. Tricking the MITM into logging into the honeypot showed that they used **paramiko** (a Python SSH library) and also how they attempted to install Ebury using Perl. This involved checking for permissions first, then executing a base64-encoded command. Marc-Etienne M. Léveillé noted, "Given how many servers had Ebury between 2009 and 2023 (400,000!), there are most likely other compromised Tor relays out there." **Disable password authentication in favor of SSH keys.**

To read the complete article see:
[Read full article](https://kaba.cx/posts/20261020_Tor/) 
