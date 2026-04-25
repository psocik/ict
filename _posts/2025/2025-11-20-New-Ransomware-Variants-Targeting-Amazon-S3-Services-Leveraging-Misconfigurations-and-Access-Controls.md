---
title: New Ransomware Variants Targeting Amazon S3 Services Leveraging Misconfigurations and Access Controls
date: 2025-11-20
categories: [CYBER SECURITY]
tags: [RANSOMWARE,AMAZON S3,CYBER SECURITY]
---

A new wave of ransomware attacks is targeting cloud storage environments, specifically focusing on Amazon Simple Storage Service (S3) buckets that contain critical business data.

The Server-Side Encryption with Customer-Provided Keys (SSE-C) variant represents one of the most dangerous attack methods because it creates permanently unrecoverable encrypted data.

After identifying target buckets without proper protections, attackers initiate encryption by providing a locally stored AES-256 encryption key through specific HTTP request headers or AWS command-line tools.

The critical aspect of this technique is that AWS uses the attacker’s encryption key to secure the data but never stores the actual key in its systems. AWS only logs a Hash-based Message Authentication Code (HMAC) of the encryption key in CloudTrail logs, which cannot be reversed or used to decrypt the protected data.

To read the complete article see:
[New Ransomware Variants Targeting Amazon S3 Services](https://cybersecuritynews.com/new-ransomware-variants-targeting-amazon-s3-services/) 
