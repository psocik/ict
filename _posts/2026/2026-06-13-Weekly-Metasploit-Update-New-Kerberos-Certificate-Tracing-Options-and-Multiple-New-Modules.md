---
title: Weekly Metasploit Update New Kerberos/Certificate Tracing Options and Multiple New Modules
date: 2026-06-13
categories: [SECURITY]
tags: [METASPLOIT,KERBEROS,SECURITY,MODULES,UPDATE]
---

## Weekly Metasploit Update 🚀

As hard as we try to ensure that Metasploit is bug-free, issues inevitably arise. Whether you're running a module on an operation or writing a new one, we aim to make the debugging experience easier. To that end, one of our two Google Summer of Code (GSoC) projects is here to deliver!

### New Features 🌟
Building on the previous pattern of HttpTrace, we introduce two new options: **KerberosTicketTrace** and **CertificateTrace**. When enabled, these options will provide debugging output of Kerberos tickets and Certificates that are both sent and received by applicable modules. 

For example, to inspect what's happening when using the `auxiliary/admin/kerberos/get_ticket` module, users can set `KerberosTicketTrace true`. This allows viewing details such as the `Kerberos Request: AS-REQ` protocol version, message type, and pre-authentication data. It also reveals `Kerberos Response: KRB-ERROR` messages, including `Error Code: KDC_ERR_PREAUTH_REQUIRED` (Value: 25, Description: Additional pre-authentication required).

Upon a successful `AS-REP` response, the system displays `Kerberos Credential: TGT` details, including `Ticket Flags: 0x50e10000 (FORWARDABLE, PROXIABLE, RENEWABLE, INITIAL, PRE_AUTHENT, CANONICALIZE)` and confirms a valid TGT-Response was received, with a TGT MIT Credential Cache ticket saved.

### Future Enhancements 🔮
Stay tuned for future enhancements like **KerberosTicketTraceLevel**, which will include verbosity toggles such as meta, ticket, and full. We would like to thank our GSoC contributors **eve0805** and **Pushpenderrathore** for their hard work on this project.

### Community Feedback Needed 🗣️
Metasploit is currently reconsidering the UX of evasion modules. Users are currently required to use the module, set the payload, run it, then return to their exploit and copy the generated output from the evasion module into the exploit. This cumbersome process can be improved, and we are soliciting feedback from the community on the best path forward. We have published a write-up of the options we're considering and a form for feedback, which contains 3 questions and will be open until **July 1st, 2026**.

### New Module Content 🆕
Additionally, new module content has been added, including **ClickFix Server**. This Exploit module was authored by **boredchilada** and **h00die**, contributed via pull request #21212 by **h00die**, and is located at `multi/mis`.

To read the complete article see: [Read full article](https://www.rapid7.com/blog/post/pt-metasploit-wrap-up-13-06-2026/)