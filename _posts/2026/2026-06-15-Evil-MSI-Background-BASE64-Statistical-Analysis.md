---
title: Evil MSI Background BASE64 Statistical Analysis
date: 2026-06-15
categories: [CYBERSECURITY]
tags: [MALWARE,BASE64,ANALYSIS,CYBERSECURITY]
---

## Evil MSI Background: BASE64 Statistical Analysis

A recent analysis focused on a suspicious JPEG file, following up on **"The Evil MSI Background is Back!"**. The bytes present in this suspicious JPEG file were examined using the `byte-stats.py` tool. The results showed that almost half of the content (45.65%) is BASE64 characters, and the longest BASE64 string is 1000 characters. Additionally, the longest string is almost 1 million characters long. However, using `base64dump.py`, the longest BASE64 string found was indeed 1000 characters long but didn't seem to decode to something recognizable. This indicated that a special encoding must have been used. Further attempts using `base64dump.py` revealed long BASE85 encoded strings, but still no string close to 1 million characters, leading to the conclusion that this must be a custom encoding.

To try to figure out what custom encoding is used, a `--stats` option was added to `base64dump.py`. This new feature provided character statistics, showing that all BASE64 characters appear in the detected BASE64 strings, but that the letter A appears significantly less than other letters. If a minimum length for the detected BASE64 strings was used, the letter A was even missing. Notice that the `=` character is also missing, but the `=` character is a padding character in BASE64, not a normal character: it can only appear once or twice at the end of a BASE64 string. So this statistics feature of `base64dump.py` helps us to detect that we might be dealing with a custom encoding, based on BASE64, where the letter A has been replaced with another character. Character `#` was identified as the most frequent, leading to the hypothesis that A had been replaced with `#`, but this attempt was unsuccessful.

The discrepancy where a very long BASE64 string, almost 1 million characters long, was identified by `byte-stats.py` but not `base64dump.py` was due to `byte-stats.py` looking for longest strings of consecutive BASE64 characters without checking if that string length is a multiple of 4 (a requirement for BASE64), while `base64dump.py` does check this. Upon closer inspection of the long string, it was noticed that the string had been reversed: `==` appears at the beginning, and not at the end. And the end is ...qVT, which is TVq reversed, and that's a marker for MZ, e.g., a Windows executable. Reversing the encoded payload confirmed that it was indeed a PE file, and it had the same hash as the file Xavier extracted. This new feature of `base64dump.py`, `--stats`, can help with the reversing of custom encodings by providing statistics of the encoding characters.

[Read full article](https://isc.sans.edu/forums/diary/Evil%20MSI%20Background:%20BASE64%20Statistical%20Analysis/33072/)