---
title: 5G-Shark Lures Phones to Rogue 5G Cells Without Network Jamming
date: 2026-09-25
categories: [TECHNOLOGY]
tags: [5G,SECURITY,RESEARCH,ROGUE CELLS]
---

## 5G-Shark Lures Phones to Rogue 5G Cells Without Network Jamming

**Source:** Hackread  
**Date Published:** September 25, 2026  

Security researchers have developed a method that can pull nearby 5G phones onto a rogue base station without jamming the legitimate network or broadcasting malformed radio messages. The method, named **5G-Shark**, manipulates the standard cell-reselection process used by phones to choose between available mobile cells. Researchers used it to collect subscriber identifiers, track devices through temporary identifiers, force connections onto older network generations, and trigger denial-of-service (DoS) attacks. 🚨

5G-Shark observes network information broadcast by the real operator and configures its rogue cell with matching operator identifiers, frequencies, and reselection priorities. If the rogue cell advertises a higher priority and provides sufficient signal quality, the phone can select it as the preferred cell under normal 3GPP mobility rules. The researchers found that their test devices spent almost **70%** of the observed time in an eligible idle state. A one-minute broadcast window, averaging **58 seconds**, was sufficient to attract the team's test phones, complete the registration exchange, and release them back to the commercial network. According to the research paper, no action was required from the phone owner, and the devices displayed no security warning. The attack could still cause a short interruption in connectivity.

Once connected, the phone sends a registration request containing its temporary network identifier, known as a **GUTI**. The rogue base station claims that it cannot recognize that identifier and sends an identity request before mutual authentication has taken place. On Standalone networks, the permanent subscriber identity is normally transmitted as a concealed **SUCI**. Even when that protection worked, 5G-Shark could collect the phone's temporary identifier and request its **IMEI/IMEISV**. Non-Standalone 5G provides weaker subscriber identity protection. In the researchers' tests, devices connected through Non-Standalone configurations exposed their permanent **IMSI** in clear text across all three studied operators. The rogue station can then send an unauthenticated registration-rejection message. Different rejection codes caused phones to fall back to **LTE** or **UMTS**, repeatedly attempt registration, lose data connectivity, or enter other unwanted states.

The study included the **Galaxy Z Flip3**, **OnePlus 8**, **Oppo Find X5 Lite**, **iPhone 13 Pro**, **Google Pixel 8**, **Galaxy S23**, and a **Quectel RM520N-GL modem**. The researchers tested networks operated by three unnamed Tier-1 mobile carriers, identified in the paper only as **Operator A**, **Operator B**, and **Operator C**. The team collected **3,742** temporary-identifier observations across Standalone and Non-Standalone networks. Operator C generated values with a comparatively random distribution, while Operator A and the Non-Standalone network of Operator B assigned identifiers in small, near-sequential steps. According to the paper, these clustered values could allow consecutive registrations to be linked to the same device even when the subscriber's permanent identity remains encrypted. Testing on a Galaxy S23 also uncovered implementation-specific failures. Two rejection codes sent the modem into a continuous registration loop that could drain the battery. 🔋

The researchers propose that phones compare newly advertised cell priorities with previously observed network information and flag unexplained high-priority cells. They also recommend quarantining unauthenticated rejection messages that demand a downgrade and displaying a warning when a network requests an identity in clear text. **5G-Shark** does not give an attacker access to calls, messages, or files. The risk comes from what can happen before a phone authenticates the network. Attackers can collect identifiers, track devices, and downgrade or interrupt mobile service without any action from the user.

[Read full article](https://hackread.com/5g-shark-phones-rogue-cells-jamming-mobile-networks/) 