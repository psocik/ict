---
title: NAT and Packet Capture
date: 2025-06-12
categories: [NETWORK]
tags: [NAT,PACKET CAPTURE,IPV4,IPV6,NETWORK SECURITY]
---

The shortage of IPv4 addresses has forced us to use smart techniques to reallocate address blocks, speed up adoption of IPv6, and reduce the number of addresses we use. We’re going to focus on this last one as it affects how packets are captured.

### Using Reserved Addresses
In our example network we’ll use 172.25.0.0/16 to provide 65,534 addresses to the systems in our building (from 172.25.0.1 through 172.25.255.254). All traffic between those internal systems will happen normally.

The 172.25.0.0/16 network is one of the reserved address blocks, also called RFC1918 addresses after the document that made them available, [RFC1918](https://www.rfc-editor.org/info/rfc1918). The good news is that these addresses can be used anywhere for internal communication. They can be – and are – used on millions of networks around the world.

This raises an interesting question; given a reserved IP address such as 172.25.3.19, to what system is that assigned and how would I get a packet to it? Unfortunately, there’s no answer to those questions since potentially millions of computers could all have that IP address – to which one should we send the traffic?

Since we have no way to direct traffic to one of these systems with a reserved address, we need to handle packet routing differently... 

To read the complete article see:  
[https://www.activecountermeasures.com/nat-and-packet-capture/](https://www.activecountermeasures.com/nat-and-packet-capture/) 