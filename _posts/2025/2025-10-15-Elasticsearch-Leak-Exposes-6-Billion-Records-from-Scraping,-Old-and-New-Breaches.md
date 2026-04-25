---
title: Elasticsearch Leak Exposes 6 Billion Records from Scraping, Old and New Breaches
date: 2025-10-15
categories: [PRIVACY]
tags: [ELASTICSEARCH,DATA BREACH,PRIVACY,SECURITY]
---

An Elasticsearch leak exposed 6 billion records from global data breaches and scraping sources, including banking and personal details tied to multiple regions. A misconfigured Elasticsearch server holding 1.12 terabytes of data was leaking more than 6 billion records to public access without any security authentication or password. The server, apparently operated from Russia or a Russian-speaking country, contained detailed records collected through data breaches, website scraping, and other sources before it was taken offline.

Although limited details are available, one of the screenshots from the exposed server showed records from a Ukrainian bank called Accordbank, officially known as "Commercial Bank Accordbank." Inside, the researcher found a trove of banking, contact, and personally identifiable information (PII) of users stored in JSON format, including:
1. Full names
2. Phone numbers
3. Date and place of birth
4. National ID number or tax code
5. Passport numbers and issuing authority
6. Address (including city and street details).

Additionally, the exposed server also indexed databases and user details gathered from both announced and unannounced data breaches, along with records extracted through website scraping. This was confirmed by the researcher who examined the server before it was taken offline, although screenshots of those specific datasets could not be obtained in time.

During the investigation, Hackread.com found a thread on DarkForums, the successor to the now-defunct Breach Forums, where a user going by the alias "tRex_Prime" was offering data records spread across more than 6,000 CSV files. The thread was titled "6k+ CSV Leak Database," detailing 2,356 files with names. Each CSV file was labelled with either a company name or a tag indicating what the data belonged to. Among the listed files was one named Accordbank. Since there are no public reports linking Accordbank to any previous data breaches, it is reasonable to assume that these 6,000+ CSV files were extracted from the misconfigured Elasticsearch server containing 1.12 terabytes of data.

To read the complete article see: [Hackread Article](https://hackread.com/elasticsearch-leak-6-billion-record-scraping-breaches/)
