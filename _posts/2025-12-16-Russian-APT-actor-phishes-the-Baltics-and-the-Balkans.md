---
title: Russian APT actor phishes the Baltics and the Balkans
date: 2025-12-16
categories: [APT]
tags: [PHISHING,CYBERSECURITY,APT]
---

On December 5th, a Russian APT targeted Transnistria’s governing body with a credential phishing email attachment, spoofing the Pridnestrovian Moldavian Republic. The HTML loads the image in a DIV named bluer, which is a misspelling of “blur.” The CSS applies a blur filter. Upon entering credentials, it checks if the password complies with a complex regex. If the password matches the regex, it is POSTed to formcarry.com. However, if the password does not match, it still steals the data, perhaps in an effort to gather secondary passwords that might be valid elsewhere.  

This campaign has been active since at least 2023 with spears such as '12th package of sanctions against Russia.pdf.html', based on identical regular expressions and JavaScript logic. There was one phishing attempt that did not follow the same pattern and instead loaded unknown but suspected malicious code from an external server, timesyncwindows.com.  

Other files from this same campaign include 'Cancellation of personal special economic and other restrictive measures.html', assessed to target Ukraine DIB. Another lure, 'Cyber Threats and NATO Horizon Scanning and Analysis.html', targeted the governments of Bosnia and Herzegovina, Macedonia, Montenegro, and Spain. The 'Update of the List of Diplomatic Missions Accredited to EEAS.html' was directed at the governments of Ukraine and Lithuania. Furthermore, 'New Event Scheduling in Outlook on the Web.html' was aimed at the Macedonia Government, and 'NATO SCHOOL Course Catalogue 2024 update.html' targeted the Bulgaria Government. The '12th package of sanctions against Russia.pdf.html' lure also targeted Ukraine DIB, while 'Protected Internal Reporting Regulations.html' was directed at the Macedonia Government. Finally, 'Secret Report Cyber Threats Security.html' and 'Распоряжение № 441рп.pdf.html' both targeted the Moldova Government. Because the phishing lures often contain the direct target information, the IOCs are available on our GitHub.  

To read the complete article, see: [Strikeready Blog](https://strikeready.com/blog/russian-apt-actor-phishes-the-baltics-and-the-balkans/)  

---