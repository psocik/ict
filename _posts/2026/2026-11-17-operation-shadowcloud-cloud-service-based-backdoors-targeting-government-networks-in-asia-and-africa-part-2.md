---
title: Operation ShadowCloud Cloud Service–Based Backdoors Targeting Government Networks in Asia and Africa - Part 2
date: 2026-11-17
categories: [CYBERSECURITY]
tags: [MALWARE,SHADOWCLOUD,GOVERNMENT,ASIA,AFRICA]
---

## Operation ShadowCloud: Cloud Service–Based Backdoors Targeting Government Networks in Asia and Africa - Part 2

In this part, we will walk through the **GraphDoor backdoor** and the suite of plug-ins loaded, including patched Erfrp and Ably proxy plug-ins, and highlight the attribution clues that tie the operation to Chinese-speaking threat groups. 

**GraphDoor** (MD5 14ec33ea808e697870d00c5e434c2952) begins by opening a named pipe that it will reuse for later communications, building the pipe's name from its own PID in the form `\.\pipe\p%lu`. Once the backdoor contacts its C2 server and downloads the required plug-ins, those plug-ins write their status reports to the same pipe. After the pipe is set up, the backdoor creates a directory named **Intel_Log** inside the system's **ProgramData** folder, generating a subdirectory whose name is a randomly generated GUID, yielding a full path like `C:\ProgramData\Intel_Log\<random-GUID>`. Next, the malware starts gathering system information to send back to the attacker. 

Using an indirect call technique, the malware harvests the following information from the victim machine:
- Network adapter details
- Version of the operating system
- A randomly generated GUID for the infected machine
- Public IP
- Private IP
- Username
- Host name
- Current directory
- PID of its own module
- A list of all the running processes

The resulting information is then encrypted with **AES**, Base64-encoded, and transmitted to the command-and-control server.

The malware first opens a **TLS connection** to `login.microsoftonline.com` on port 443. Once the TLS handshake completes, it decrypts three hard-coded, AES-encrypted strings. These values become the components of the authentication request: UUID path segment, Client ID (application registration), and Client secret. It also generates a random **X-CSRF-TOKEN**, decrypts a preset User-Agent string and several other hard-coded strings, and then issues a **POST request** to `login.microsoftonline.com`. This call authenticates the malicious application - not a user - and returns an access token that the backdoor later uses to communicate with the **Microsoft Graph API**. If the authentication succeeds and an access token is obtained, the backdoor generates a fresh random value for the **X-CSRF-TOKEN** header and then connects to `graph.microsoft.com`. It issues a Microsoft Graph **PUT request** that creates a file called `main.%victim-unique-code%.js.map`, masquerading as a JavaScript source map file, in a SharePoint document library. The encrypted victim data placed in the PUT request body is stored in this file on the SharePoint drive.

The malware then pulls three plug-in modules from the server. Once fetched, the plug-ins are decrypted using the same routine employed by the **GitDoor** variant. The request to download plug-ins targets a specific list on a specific SharePoint site via the **Microsoft Graph API v1.0** endpoint. Once the three plug-in modules have been retrieved, the malware reestablishes contact with the server to fetch commands. It then sends a request to list the command files intended for the victim on the SharePoint website. The backdoor verifies each file's extension against an allowed list (.js, .swp, .tmp, .kmap, .pmap, .apmap). When a match is found, it downloads the corresponding command file and executes the command in the same way as described for the **GitDoor** variant. 

The backdoor incorporates commands similar to those found in the **GitDoor** variant. However, in the "Load Shellcode" category, two additional commands were identified: `shell` and `adsmload`. The `shell` command executes the supplied command with `cmd.exe /C <command_string>`. The `adsmload` command is very similar to the `smload` command; however, the payload and optional input arguments are formatted as ASCII MAC addresses and then Base64-encoded. After decoding the Base64 string, the ASCII MAC address-encoded strings are parsed back into raw binary bytes using **RtlEthernetStringToAddressA**. The final payload bytes may be an MZ executable or shellcode, which are injected into memory.

For more details, check out the full article here: [Read full article](https://securelist.com/operation-shadowcloud-graphdoor/122005/).