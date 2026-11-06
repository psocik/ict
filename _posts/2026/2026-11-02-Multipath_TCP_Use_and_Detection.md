---
title: Multipath TCP Use and Detection
date: 2026-11-02
categories: [NETWORKING]
tags: [MULTIPATH,TCP,NETWORKING,VULNERABILITY]
---

## Multipath TCP: Use and Detection

Last week, an often-ignored TCP option, introduced in 2020, made the news due to a new vulnerability in Linux's implementation (RFC 8684, CVE-2026-98432). Instead of focusing on the vulnerability, this diary examines multipath TCP (MPTCP) and how it may be used in networks. 

Traditionally, TCP is a connection-oriented protocol where connections are established between a client and server, and host IP addresses are not expected to change for a specific connection. This restriction to a specific path does not always match modern system architecture. For example, mobile devices may switch from a local WIFI network to a cellular network at any time, and having to re-establish TCP connections may break applications. Additionally, servers often have a hard time "filling" high-bandwidth links using a single TCP connection due to limits on Window Size and the sequence number range. 

MPTCP is designed to solve these problems by allowing connections to be split and handed over between different IP addresses. The only widely used implementation observed is iOS/iPadOS, where IPv4 connections to Apple (17.0.0.0/8) often utilize MPTCP. MPTCP was initially used for Siri, and later for other services like Apple Music. Two versions of MPTCP are currently defined and used: v0 and v1.

The MPTCP Option (0x1e, 30) is followed by a byte containing 4 bits indicating the subtype and 4 bits indicating the version (0 or 1). The MP_CAPABLE (subtype 0) option indicates MPTCP support, and both sides must include it in the TCP handshake for MPTCP support to be enabled. Each MP_CAPABLE option also carries an 8-byte key used to identify and authenticate the different sub-sessions. The MP_JOIN (subtype 1) option allows a second TCP connection to join an initial connection. This connection will typically be initiated by the client, but may originate from a different IP address. The DSS (Data Sequence Signal, subtype 2) option is used to stitch the content of multiple connections together, mapping the respective's TCP sequence numbers to the sequence numbers of the combined connection. Furthermore, ADD_ADDR/REMOVE_ADDR (subtypes 3, 4) options are similar to MP_JOIN, but instead of actually setting up an additional connection, they advertise or remove additional addresses or ports that can be used.

The best way to detect MPTCP is to look for TCP Option 30. Wireshark/tshark simplifies detection with a "mptcp" display filter keyword. For tcpdump, while there is no direct way to match TCP options, MPTCP packets, particularly SYN packets, tend to have large TCP headers, allowing a quick match on TCP header length, such as 'tcp[12]>0xd0'. Suricata can use the "tcp.hdr" keyword to inspect TCP options. A key for Suricata detection is that there should be at least one MP_CAPABLE message including both sender and receiver keys, making this option 20 bytes long, with the first three bytes being '|1e 14 00|' for version 0 or '|1e 14 01|' for version 1. In contrast, Snort does not have a keyword to inspect TCP options, and no known way to filter for multipath TCP. Zeek, however, offers the tcp_option and tcp_options events, which can easily be used to log MPTCP. For example, an event can print "MPTCP between %s and %s" if the option is 30.

To read the complete article see: [Read full article](https://isc.sans.edu/forums/diary/Mutipath%20TCP:%20Use%20and%20Detection/33482/) 

🚀 Stay updated with the latest in networking!