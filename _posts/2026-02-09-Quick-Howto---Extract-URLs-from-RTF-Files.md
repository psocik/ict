---
title: Quick Howto - Extract URLs from RTF Files
date: 2026-02-09
categories: [SECURITY]
tags: [RTF,URLS,SECURITY,MALWARE]
---

## Quick Howto - Extract URLs from RTF Files

Malicious RTF (Rich Text Format) documents are back in the news with the exploitation of CVE-2026-21509 by APT28. The malicious RTF documents **BULLETEN_H.doc** and **Consultation_Topics_Ukraine(Final).doc** mentioned in the news are RTF files (despite their .doc extension, a common trick used by threat actors).

Here is a quick tip to extract URLs from RTF files. Use the following command:

```bash
rtfdump.py -j -C SAMPLE.vir | strings.py --jsoninput | re-search.py -n url -u -F officeurls
```

The components of this command chain are as follows:
- `rtfdump.py -j -C SAMPLE.vir`: This parses the RTF file **SAMPLE.vir** and produces JSON output with the content of all the items found in the RTF document. Option **-C** ensures that all combinations are included in the JSON data: the item itself, the hex-decoded item (-H), and the hex-decoded and shifted item (-H -S). So per item found inside the RTF file, 3 entries are produced in the JSON data.
- `strings.py --jsoninput`: This takes the JSON data produced by `rtfdump.py` and extracts all strings.
- `re-search.py -n url -u -F officeurls`: This extracts all URLs (-n url) found in the strings produced by `strings.py`, performs deduplication (-u), and filters out all URLs linked to Office document definitions (-F officeurls).

I have found one domain (**wellnesscaremed**) and one private IP address (**192.168...**). I found extra IOCs: a UNC and a "malformed" URL. The URL has its hostname followed by **@ssl**. This is not according to standards. **@** can be used to introduce credentials, but then it has to come in front of the hostname, not behind it. Here are the results for the other document: Notice that this time, we have **@80**. I believe that this **@** notation is used by Microsoft to provide the port number when WebDAV requests are made (via UNC).

To read the complete article see: [Read full article](https://isc.sans.edu/forums/diary/Quick%20Howto:%20Extract%20URLs%20from%20RTF%20files/32692/)