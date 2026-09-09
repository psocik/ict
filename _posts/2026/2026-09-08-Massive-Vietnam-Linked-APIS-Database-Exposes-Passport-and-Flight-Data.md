---
title: Massive Vietnam-Linked APIS Database Exposes Passport and Flight Data
date: 2026-09-08
categories: [DATA BREACH]
tags: [VIETNAM,APIS,DATA BREACH,SECURITY,PASSENGER DATA]
---

## Massive Vietnam-Linked APIS Database Exposes Passport and Flight Data 🚨

An exposed Vietnam-linked APIS database has revealed **220.8 million** passenger and crew records, including sensitive passport and flight data. Researchers discovered this alarming breach while searching for exposed databases. The database, which spans records from **January 2017 to April 2026**, contains crucial details such as passport numbers, identities, and flight information, potentially impacting travelers of various nationalities who have flown to, from, or through Vietnam.

### Key Findings:
- The exposed database, named **"pax-info,"** was found by Kinryū Labs and contained **29 indices** and approximately **107 GB** of data.
- The server is linked to IP space assigned to **Viettel** in Hanoi, although the specific Vietnamese organization operating it remains unconfirmed.
- Sensitive information includes:
  - Names
  - Dates of birth
  - Sex
  - Nationalities
  - Passport or travel-document numbers
  - Expiration dates and issuing countries
  - Flight numbers and dates
  - Airlines
  - Departure and destination airports
  - Transit airports
  - Seat numbers
  - Baggage references
  - Scheduled, estimated, and actual flight times

This breach could affect individuals from around the world who traveled to or through Vietnam between **2017 and 2026**. Kinryū Labs verified the authenticity of the data by matching records with their own trips to Vietnam. It's important to note that the total count includes travel records, meaning frequent travelers may appear multiple times.

### Security Concerns:
Kinryū Labs accessed the exposed database by exploiting two security misconfigurations. Although direct internet access returned a **401 error**, another cloud-based path exposed the cluster and accepted default credentials. The host was first detected in **2022** and identified as a database in **2023**, but the exact timeline of when the passenger data became accessible remains unclear.

On **June 3**, Kinryū Labs reported the issue to Vietnamese authorities, affected airlines, and national CERTs. The database was secured by **June 8**, with **Singapore Airlines** assisting in the response. Fortunately, researchers found no evidence that the listed airlines operated the system or experienced a network breach. There were also no ransom notes or indications that attackers had altered the database. However, without server logs, it remains uncertain whether any data was copied or stolen prior to securing the system.

For more details, check out the full article: [Read full article](https://securityaffairs.com/198671/data-breach/massive-vietnam-linked-apis-database-exposes-passport-and-flight-data.html) 
