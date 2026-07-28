---
title: Dear Diary Today I Found A Ghost In The Network
date: 2026-07-27
categories: [CYBERSECURITY]
tags: [CYBERSECURITY,MALWARE,APT,CHINA]
---

## Dear Diary Today I Found A Ghost In The Network

👻 In the realm of cybersecurity, some entities operate like ghosts, hidden from plain sight. One such entity is Guangdong Chanming. If you were searching for them, you might be disappointed—no public website, no storefront, and certainly no obvious product line. However, for those who know how to look for the cracks in the Great Firewall, the breadcrumbs they leave behind suggest that this "ghost" is a vital cog in China's cyber machinery.

Their patent filings and software copyrights reveal a wealth of information, with registered titles including:
- **互联网安全接入系统** - Internet Security Access System
- **多功能安全代理系统** - Multi-functional Security Proxy System
- **文件传输密网系统** - File Transfer Network System (FTN)
- **Security Tunnel Net防溯源密网系统** - Anti-traceability Network System (STN)
- **网络设备脆弱性测试分析系统** - Network Vulnerability Testing System
- **Android终端秘取平台** - Android Secret Extraction System
- **Telegram数据采集落查系统** - Telegram Data Collection System

A series of PLA procurement contracts name them as the supplier, confirming they sell directly to the state.

### The Ghost's Footprint

So how does a 'ghost' company leave a footprint? Simple: they employ people who are much clumsier. Enter Wang Huiping. Guangdong Chanming lists two shareholders: Dai Zhoujun (代兆军) and Wang Huiping (王慧平). By pulling the thread of the number attached to Wang, it didn't take long to hit a breakthrough—the number appears in multiple data breach dumps, repeatedly paired with the email address boywhp[at]126.com. This email address is a key that unlocks a piece of the puzzle: a software tool known as FCN (Free Connect).

The repository has since been wiped, but traces can still be found in various forks, pointing us toward the domain xfconnect.com. A VirusTotal search on that domain revealed multiple FCN binaries, one of which bears a striking similarity to a file named stn.exe—described as the "STN Security Tunnel." The strings extracted from the STN file even make direct references to FCN.

### Digging Deeper

As we dug deeper, almost every Linux build of FCN employs a highly unusual command to identify an interface name: `cat /proc/net/route | awk '{print $1,$2}' | awk '/00000000/ {print $1}'`. We searched for this specific digital signature, and it led us straight to a file known as bulbature—also known in the wild as the WHIPWEAVE malware. WHIPWEAVE is a core component of the RedRelay covert network (also known as ORBWEAVER), a tool used by several known Chinese cyber actors. The overlap isn't just coincidental; it is systemic.

Two of Guangdong Chanming's patents describe a multi-hop, anonymizing traffic flow that aligns with what we know about RedRelay. Either the FCN's unusual commands coincidentally match those of a covert network malware which matches patent descriptions that name the FCN developer, or FCN is a variant of the malware and the patents are an attempt to legitimize it.

### Customer Roster

If RedRelay is indeed the product being sold, then the APTs using it should align with the company's customers. This led to a customer roster including the PLA and the Ministry of Public Security. Procurement listings show Guangdong Chanming provided an "Anonymous Network System" (presumably RedRelay) to a military unit in Beijing's Haidian District, home to the PLA Cyberspace Force. RedRelay users are connected to APTs with many different names, including: Red Vulture, APT15, Ke3chang, Vixen Panda, Playful Dragon, Nylon Typhoon. Now, Unit 61046 and CSF 8th Bureau are added to the list. This military unit has been utilizing Guangdong Chanming's RedRelay network to conduct cyber campaigns that span the globe.

[Read full article](https://intrusiontruth.wordpress.com/2026/07/27/dear-diary-today-i-found-a-ghost-in-the-network/)