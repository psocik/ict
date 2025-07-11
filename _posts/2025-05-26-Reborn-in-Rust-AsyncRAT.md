---
title: Reborn in Rust AsyncRAT
date: 2025-05-26
categories: [MALWARE]
tags: [ASYNCRAT,RUST,MALWARE,CYBERSECURITY]
---

Rewritten in Rust

The family as it is known until now has been written in C#. Interestingly, we encountered a few recent malware samples written in Rust. The configuration options, the CnC communication and the supported commands indicated that this is a variant of ‘AsyncRat’. While the language is still not extensively used for malware development, there is a growing trend of cyber criminals adopting Rust in their malware campaigns and tooling. A few reasons can be attributed to the choice which include:

- The recent overall popularity of Rust  
- The increased difficulty to reverse engineer binaries produced with Rust, due to lack of support for Rust in current analysis tools. Features like IDA library code recognition are not yet robust enough yet for languages like Rust.  
- Cross platform malware development opportunity  

Employing languages that make reverse engineering challenging is not a new trend. While C++ has been the go-to language for malware development for a long time, using a programming language to complicate reverse engineering has been a long prevalent technique. More than a decade ago, visual basic binaries containing pseudocode (VB bytecode was not officially documented by Microsoft) were used by malware authors very much for the same goal. The use of obfuscated .NET binaries came a few years later. In the same vein, a bunch of newer programming languages have been used in the past few years which include Go, Nim, Node.js, Electron etc.

To read the complete article see:  
[https://www.gdatasoftware.com/blog/2025/05/38207-asyncrat-rust](https://www.gdatasoftware.com/blog/2025/05/38207-asyncrat-rust)