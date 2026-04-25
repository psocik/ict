---
title: Nine NuGet packages disrupt DBs and industrial systems with time-delayed payloads
date: 2025-11-10
categories: [RESEARCH]
tags: [NUGET,MALWARE,CYBERSECURITY,INDUSTRIAL SYSTEMS,DATABASES]
---

Nine NuGet packages have been discovered containing time-delayed payloads designed to disrupt databases and industrial control systems. The packages, published by an actor named "shanhai666," were found by Socket's Threat Research Team and have been downloaded nearly 9,500 times. The malicious code is scheduled to activate as late as November 2028.

The most dangerous package identified is "Sharp7Extend," which targets industrial Programmable Logic Controllers (PLCs) using a dual sabotage mechanism. This involves immediate random process termination combined with silent write failures that begin 30 to 90 minutes after installation. The combination of these two attacks can have critical impact on safety-critical systems in manufacturing environments. The malicious packages target all three major database providers used in .NET applications (SQL Server, PostgreSQL, SQLite), plus industrial control systems. Almost every malicious package (99%) contains fully functional code that performs as advertised.

The malicious packages use a typosquatting technique, where the attacker appends "Extend" to the legitimate "Sharp7" library name. This library is a popular .NET implementation for communicating with Siemens S7 PLCs, and the modified package is designed to trick developers searching for extensions or enhancements. The malware weaponizes C# extension methods (.Exec and .BeginTran) to intercept operations, check for hardcoded or encrypted trigger dates, and then probabilistically terminate processes with a 20% chance.

The triggers are staggered to maximize stealth and potential impact. One SQL Server build is set to activate on August 8, 2027, while other database builds activate on November 29, 2028. The Sharp7Extend package activates immediately and runs until June 6, 2028. This long delay and staggered rollout makes attribution difficult. The package also silently corrupts data, failing 80% of write operations without any error messages after the initial delay. This can impact actuators, setpoints, safety systems, and production controls.

Researchers believe the threat actor may be of Chinese origin based on the alias "shanhai666" and the presence of Chinese-language comments within the code. Security teams are advised to audit their NuGet package dependencies and remove any identified malicious packages. The malicious packages identified include SqlUnicorn.Core, SqlDbRepository, SqlLiteRepository, SqlUnicornCoreTest, SqlUnicornCore, SqlRepository, MyDbRepository, MCDbRepository, and Sharp7Extend.

For more details, read the full article [here](https://securityaffairs.com/184383/malware/nine-nuget-packages-disrupt-dbs-and-industrial-systems-with-time-delayed-payloads.html).