---
title: Malicious JPEG Images Could Trigger PHP Memory Safety Vulnerabilities
date: 2026-05-16
categories: [CYBERSECURITY]
tags: [PHP,VULNERABILITIES,JPEG,MEMORY-SAFETY,CYBERSECURITY]
---

## Malicious JPEG Images Could Trigger PHP Memory Safety Vulnerabilities 🚨

Two critical memory-safety vulnerabilities in PHP's image-processing functions could allow attackers to leak sensitive heap memory or execute denial-of-service attacks via specially crafted JPEG files. The flaws, discovered in PHP's ext/standard extension by Positive Technologies researcher Nikita Sveshnikov, affect the widely-used `getimagesize` and `iptcembed` functions that process JPEG metadata and IPTC data.

### Vulnerability Details

1. **CVE-2025-14177**: This vulnerability enables information disclosure when PHP's `getimagesize` function processes JPEG APP segments in multi-chunk reading mode. Affected versions include PHP 8.1.* before 8.1.34, 8.2.* before 8.2.30, 8.3.* before 8.3.29, 8.4.* before 8.4.16, and 8.5.* before 8.5.1. The vulnerability stems from a bug in the `php_read_stream_all_chunks` function that incorrectly concatenates data chunks when reading JPEG application segments. Attackers can exploit this flaw by crafting JPEG files with large APP1 segments designed to be read across multiple chunks.

2. **Heap Buffer Overflow**: The second vulnerability affects the `iptcembed` function, which embeds binary IPTC data into JPEG images. This occurs due to a flaw where the function allocates an output buffer based on a single `fstat` result and continues reading data until EOF without capacity checks. Attackers can exploit this by feeding large amounts of data through specially crafted JPEG structures.

Both vulnerabilities exploit weaknesses in PHP's Zend Engine memory management, specifically in functions handling JPEG marker processing.

To read the complete article see: [Read full article](https://cybersecuritynews.com/malicious-jpeg-images-php-memory-safety-vulnerabilities/)