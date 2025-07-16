---
title: Chasing Ghosts Over RDP Lateral Movement in Tiny Bitmaps
date: 2025-07-13
categories: [RESEARCH]
tags: [RDP,FORENSICS,CYBERSECURITY]
---

## Chasing Ghosts Over RDP: Lateral Movement in Tiny Bitmaps  
*Source: Medium*  
  
### Introduction  
Picture this: you’re an incident responder hot on the trail of an intruder who’s hopping between servers using Remote Desktop Protocol (RDP). They think they’re sneaky, hiding behind Windows’ built-in RDP feature — a tool beloved by helpdesk technicians and hackers alike — but little do they know, every click and keystroke leaves a trail. In this post, we’ll explore how to track attackers moving laterally with RDP. Grab a cup of coffee (or two), and let’s dive into the world of RDP forensics!  
  
### RDP 101: How Remote Desktop Actually Works  
RDP is basically like streaming your desktop over the network. In simple terms, the remote server sends a live feed of its screen to your client (as images/bitmaps), and your keyboard and mouse input travel back to the server. Instead of sending text or high-level commands, RDP transmits graphics — little bitmap tiles that represent portions of the screen. These tiles get cached to save bandwidth (a legacy trick from the dial-up days). Ever notice how an RDP session can feel like watching a pixelated video of the remote PC? That’s because under the hood, RDP is shipping screen images to you and trying to compress and reuse them for efficiency. The result is an asymmetric data flow (lots of data from server -> client, and just keystrokes/clicks from client -> server). All of this is typically encrypted, which is great for security — but it means we, as defenders, have to get creative to peek at what happened inside an RDP session!  
  
To read the complete article see:  
[Chasing Ghosts Over RDP: Lateral Movement in Tiny Bitmaps](https://medium.com/@mathias.fuchs/chasing-ghosts-over-rdp-lateral-movement-in-tiny-bitmaps-328d2babd8ec)  
