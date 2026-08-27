---
title: Half-click Unauthenticated Remote Code Execution on Horde Groupware IMP
date: 2026-08-26
categories: [SECURITY]
tags: [VULNERABILITY,REMOTE CODE EXECUTION,HORDE GROUPWARE,XSS]
---

## Critical Vulnerability Alert 🚨

A critical vulnerability enabling half-click unauthenticated remote code execution (RCE) on **Horde Groupware IMP** has been detailed, stemming from a stored Cross-Site Scripting (XSS) flaw. This blog focuses on the stored XSS, which is chainable with other vulnerabilities.

Researchers identified a viable XSS sink in `lib/Mime/Status.php`, specifically:

```php
$out .= '&lt; tr>&lt; td>' . $val . '&lt; /td>&lt; /tr>';
```

However, most implementations are sanitized, with the exception of `lib/Mime/Viewer/Appledouble.php`, where the code handles:

```php
$data_name = $this->getConfigParam('imp_contents')->getPartName($data_part);
```

### Exploitation Details 🔍
Exploiting this flaw is described as trivial, requiring the crafting of a malicious email. The attack leverages a crafted `Content-Disposition` header within a `multipart/appledouble` MIME message. An example email structure to trigger the XSS is provided:

```
From: d () x com
To: victim () target com
Subject: mac file
MIME-Version: 1.0
Content-Type: multipart/appledouble; boundary="BOUND"
--BOUND
Content-Type: application/applefile
Content-Transfer-Encoding: base64
cmVzb3VyY2UtZm9yay1ieXRlcw==
--BOUND
Content-Type: application/octet-stream; name="&lt; img src=x onerror=alert('hi')>"
Content-Disposition: attachment; filename="&lt; img src=x onerror=alert('hu2')>"
Content-Transfer-Encoding: base64
ZGF0YS1mb3JrLWJ5dGVz
--BOUND--
```

Given the nature of this XSS, it is described as very much wormable and turns an existing arbitrary file read vulnerability into a half-click exploit. While simply reading files with a half-click primitive might not be the primary goal, grabbing database credentials is noted as very trivial with these two vulnerabilities chained.

To achieve remote code execution (RCE) with this XSS worm primitive, attackers can either target an administrator directly or craft an XSS worm that will eventually reach an administrator. Admins have access to a PHP shell, which allows for running arbitrary PHP code. Therefore, the XSS can be used to hit the PHP shell located at `/horde/admin/phpshell.php`. This entire process constitutes a 'half-click' exploit, as the user merely needs to click on the email to trigger the XSS.

### Proof of Concept 🛠️
An exploit proof-of-concept is provided in the original blog post.

To read the complete article see: [Read full article](https://seclists.org/fulldisclosure/2026/Aug/115)