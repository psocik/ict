---
title: Fake Recruiter Campaign Targets Crypto Developers
date: 2026-02-11
categories: [CYBERSECURITY]
tags: [CRYPTO,HACKING,RECRUITMENT,CYBERSECURITY]
---

## 🚨 Fake Recruiter Campaign Alert!

The ReversingLabs research team has uncovered a new branch of a **fake recruiter campaign** orchestrated by the notorious **Lazarus Group**, a North Korean hacking team. This campaign, dubbed **graphalgo**, has been targeting **JavaScript** and **Python** developers with cryptocurrency-related job offers since **May 2025**. 

### 📅 Key Details:
- **Fake Company Name:** veltrix-capital
- **Domain Created:** April 4, 2025
- **GitHub Organization:** veltrixcapital (created in October 2025)
- **Malicious Packages:** Found on npm and PyPI

### 🚀 How It Works:
Developers are approached through platforms like **LinkedIn**, **Facebook**, and job forums such as **Reddit**. The campaign includes a well-crafted narrative around a company involved in **blockchain** and **cryptocurrency exchanges**. 

The malicious functionality is cleverly hidden using multiple layers of indirection across public services, including **GitHub**, **npm**, and **PyPI**. 

### ⚠️ Malicious Functionality:
The campaign's malicious packages impersonate legitimate ones, with two main groups identified:
1. **Graph Packages:** Appeared in May 2025, impersonating `graphlib` and `networkx`.
2. **Big Packages:** Emerged in December 2025, potentially indicating another undiscovered operation.

### 🛡️ Remote Access Trojan (RAT):
The second-stage payloads act as downloaders for a RAT that fetches and executes commands from a command and control server. This RAT checks for the **Metamask** browser extension, indicating a focus on cryptocurrency funds. 

### 🔗 Read More:
To read the complete article see: [Read full article](https://www.reversinglabs.com/blog/fake-recruiter-campaign-crypto-devs)