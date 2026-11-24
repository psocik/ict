---
title: Critical Binary-Parser Flaw Enables JavaScript Injection
date: 2026-11-23
categories: [SECURITY]
tags: [BINARY-PARSER,JAVASCRIPT,VULNERABILITY,SECURITY,CODE-INJECTION]
---

## Critical Binary-Parser Flaw Enables JavaScript Injection

A critical security flaw has been disclosed in the popular **binary-parser** library that could allow an attacker who controls parser definitions to execute arbitrary code. The vulnerability, tracked as **CVE-2026-134814** (CVSS score: 9.2 / 8.1), is a case of code injection impacting binary-parser versions prior to 2.3.1.

According to a description of the flaw in the NIST National Vulnerability Database (NVD), "Binary-parser before 2.3.1 contains a code injection vulnerability that allows attackers controlling parser definitions to inject JavaScript through string-typed options passed unvalidated by Context.generateOption()." The NVD further detailed that "Attackers can supply crafted length, lengthInBytes, key, tag, offset, or namely() alias values to execute arbitrary JavaScript in the Node.js process when the parser is compiled."

Keichi Takahashi, who maintains the library, clarified, "Parsing untrusted binary data with a trusted parser definition is not affected." Takahashi added, "These options are now validated as identifier paths (e.g. foo, $parent.len). Expressions such as 'len - 1' are rejected; use a function instead."

CVE-2026-134814 can also be viewed as an incomplete fix for **CVE-2026-1245** (CVSS score: 6.5), another code injection vulnerability that was fixed back in January 2026 and resulted from insufficient validation of field names and encoding parameters. Upwind Security also noted in an X post that "[The flaw] allows attackers controlling parser definitions to inject and execute arbitrary JavaScript within the host Node.js process upon parser compilation."

Users are advised to update to the latest version of the library for optimal protection. 🚀

[Read full article](https://thehackernews.com/2026/11/critical-binary-parser-flaw-enables.html)