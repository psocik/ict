---
title: The 73,000-Server Market Reselling Western Frontier AI into China
date: 2026-07-30
categories: [TECHNOLOGY]
tags: [AI,SERVERS,CHINA,INFRASTRUCTURE]
---

## The 73,000-Server Market Reselling Western Frontier AI into China

**Western frontier AI** is not sold in mainland China, yet it is utilized daily. This report maps the infrastructure that enables this access, revealing a staggering **73,000 internet-facing servers** continuously tracked by Infrawatch, which resell access to models that Western frontier labs refuse to sell in that market. The Chinese developer community bridges this gap through middlemen known as **中转站 (transfer stations)**. These stations provide customers in mainland China with access to models that are otherwise unavailable, using credentials held by intermediaries and connections routed through permitted markets. Customers simply point an existing tool at these servers and top up their balance in RMB via **Alipay** or **WeChat Pay**.  

These servers support **66 distinct open-source projects** tailored for this purpose, featuring a shared toolchain and a retail layer on top. Notably, two projects, **new-api** and **sub2api**, account for **74.3%** of the total usage. The new-api project functions as a shopfront, registering customers, metering consumption, and billing against a balance. Meanwhile, the sub2api project pools upstream subscriptions and distributes them among buyers, describing its service as **拼车共享 (carpooling)**. However, it warns that usage may violate the terms of service of its upstream providers, a caution echoed by **24,000 hosts**. The most widely deployed project retains per-request model routing history by design.  

Servers also run subscription bridges that aggregate flat-rate subscriptions, account sessions, and API keys behind a single gateway, redistributing that capacity among hundreds of users and reselling it by token. Customers never hold the upstream account, and providers only see the operator's credentials and permitted addresses. A provider auditing its own traffic observes a limited number of accounts in good standing, operating from allowed addresses. This setup appears legitimate, which is precisely the intention. Furthermore, nearly a third of these services, **24,000**, operate on cloud networks owned by **Alibaba**, **Tencent**, **Huawei**, or **ByteDance**. Globally, **24,112** of **72,723** services, or **33.2%**, are hosted on these four operators' networks. Notably, **28,000** of these servers have United States addresses, more than any other country in the census. At least **3,200** of these machines are rented from Alibaba and Tencent, ensuring that while billing and control remain in China, the hardware is located elsewhere.

[Read full article](https://infrawatch.com/blog/73000-servers-selling-western-frontier-ai-into-china-transfer-stations#blogpost)