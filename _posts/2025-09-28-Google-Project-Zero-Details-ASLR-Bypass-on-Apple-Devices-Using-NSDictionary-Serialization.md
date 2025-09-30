---
title: Google Project Zero Details ASLR Bypass on Apple Devices Using NSDictionary Serialization
date: 2025-09-28
categories: [CYBER SECURITY NEWS]
tags: [APPLE,CYBER SECURITY,ASLR BYPASS]
---

The technique hinges on the predictable behavior of data serialization and the internal workings of Apple’s objects, which are essentially hash tables. The attack’s goal is to leak the memory address of the singleton, a unique, system-wide object whose memory address is used as its hash value. The victim application deserializes this object, creating the dictionary in memory. When the application re-serializes the object to send it back, it iterates through the hash table buckets in a predictable order. The position of the key in the returned data reveals which bucket it was placed in. This leaks partial information about its address, specifically the result of the address modulo the table’s size. To reconstruct the full 64-bit address, the technique employs the Chinese Remainder Theorem. By sending an array of dictionaries of varying sizes (each with a different prime number of buckets), an attacker can gather multiple pieces of information about the address. Combining these results makes it possible to calculate the complete memory address of the singleton, effectively breaking ASLR for that memory region.

[Read the full article here](https://cybersecuritynews.com/aslr-bypass-on-apple-devices/).