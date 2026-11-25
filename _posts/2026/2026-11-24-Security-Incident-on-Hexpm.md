---
title: Security Incident on Hex.pm
date: 2026-11-24
categories: [SECURITY]
tags: [HEX,VULNERABILITY,SECURITY,INCIDENT]
---

## Security Incident on Hex.pm 🚨

On **November 23, 2026**, an unauthorized third party exploited a vulnerability in hex.pm that allowed them to run commands on our web servers. We swiftly blocked the traffic and deployed a fix within **20 minutes**. Shortly thereafter, we received a report regarding this exact vulnerability.

The attacker sent **69 malicious requests** to hex.pm, affecting six of our web servers. Our error tracker, Sentry, recorded its first error at **18:16:00**, with an error logged for each request. By **18:27**, we had added a firewall rule to block the attacker's traffic, which took full effect between **18:30 and 18:33**. All hex.pm servers were replaced with a patched build that rejects these payloads between **18:30 - 18:31**.

We found no evidence of unauthorized package modifications or database changes, nor that the attacker maintained access to our systems. However, since database reads are not logged, we cannot rule out the possibility that the attacker accessed data stored in the database, including **email addresses, password hashes, API key hashes, 2FA secrets, sessions, and audit logs**. Be cautious with emails that claim to come from Hex, as reads of private packages during that period came from our own servers and coincided with releases from the same organizations.

The attacker's commands could read the credentials our servers use, prompting us to replace them: the storage, CDN, email, and database credentials, as well as the keys that sign sessions and access tokens. This action logged everyone out of hex.pm and Hex clients. We are currently building a new registry signing system that supports key rotation, with new Hex client releases expected in the coming days. Until then, users should only fetch packages from **repo.hex.pm** and change their passwords at hex.pm. Additionally, users should reset their 2FA at [hex.pm/dashboard/security](https://hex.pm/dashboard/security): under "Authenticator App", choose "Setup New App" and verify a code from the new entry to get a new secret and new recovery codes.

The vulnerability in Hex.pm is tracked as **CVE-2026-129514**. Hex.pm decoded unauthenticated request bodies in Erlang term format with `Plug.Crypto.non_executable_binary_to_term/2`, which blocks most potentially harmful terms but allows struct values through. These decoded struct values, when chained together correctly, turned into a **remote command execution (RCE)**. An attacker-supplied `{module, function, args}` tuple that the server runs gave access to functions in loaded libraries and the standard library, leading to OS command execution as the BEAM's user. During our investigation, we found a similar class of vulnerability in Ash: its keyset pagination accepted crafted structs in client-supplied cursors, which could lead to command execution or SQL injection. We reported this, and the Ash team released a fix in ash **3.38.0** on **November 24**.

For more details, please read the full article: [Read full article](https://hex.pm/blog/security-incident-on-hexpm) 
