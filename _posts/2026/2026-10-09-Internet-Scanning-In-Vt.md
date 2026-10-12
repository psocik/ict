---
title: Internet Scanning In Vt
date: 2026-10-09
categories: [INTERNET SECURITY]
tags: [INTERNET,SCANNING,VIRUSTOTAL,SECURITY]
---

## Internet Scanning In Vt

**Published on:** October 9, 2026  
**Source:** VirusTotal Blog

Until now, an IP report in VirusTotal provided valuable information about reputation, hosting details, passive DNS resolutions, and associated files. However, it lacked insights into the machine's operations. 

🚀 **Introducing Daily Scanning**  
VirusTotal now scans the public IPv4 space every day, storing details for each IP, including open and closed ports, the services behind each port, their banners, and fingerprints. All of this information is searchable!  

The closed ports are just as significant as the open ones. When a port stops responding, we retain the record, flip its status, and preserve the last date it was seen open. This allows you to answer questions like, "When did this C2 go dark?" weeks after it happened.  

### Enhanced Querying  
Everything is indexed and can be queried from the search bar or the API, supporting bracket syntax. For example, you can use:  
`entity:ip port_service_product[80]:nginx port_service_version[80]:1.24.0`.  
An open port alone is a weak signal; the real value comes from what lies behind the port: a product, version, banner string, or fingerprint.

### SSH Host Key Insights  
An SSH host key is generated when a server is installed. If two IPs present the same key, they are likely the same machine that has moved or a server cloned from the same image. For instance, starting from `91.219.237[REDACTED TO GET PAST GOOGLE FILTERS]`, an IP hosted in Hungary, we found it in our APT28 collection and a community collection about Havoc C2. Searching for that fingerprint led us to another IP, which is a twin of the first: same SSH key, same OpenSSH build, same nginx 1.24.0 on port 80, and the same JARM.  

### URL Hunting Complement  
This scanning capability also complements URL hunting, as seen with a NOX Stealer panel on `https://5.175.221[REDACTED TO GET PAST GOOGLE FILTERS]6:8443/`. The host's Ports tab revealed a complete stack: a Windows Server 2022 host with SMB and RDP exposed alongside `nginx 1.24.0` and PHP on port 8443. By combining the web stack on port 8443 with the Windows build on port 445 using the bracket syntax, the query `entity:ip port_service_product[8443]:nginx port_service_cpe[8443]:php os_type[445]:10.0.20348 open_port:445 open_port:3389` reduced 4.5 million hosts down to just 10 IPs globally.  

While preparing this, the operator rebranded the panel from NOX Stealer to BOMBAY Stealer, which broke static string queries like `title:"NOX STEALER"`. Yet, the machine on `5.175.221[REDACTED TO GET PAST GOOGLE FILTERS]` didn't change a single exposed service, demonstrating how URL hunting and Internet Scanning effectively complement each other.

[Read full article](https://blog.virustotal.com/2026/10/internet-scanning-in-vt.html)