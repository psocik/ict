---
title: Researchers Find Data Leak Risk in AWS Bedrock AI Code Interpreter
date: 2026-03-16
categories: [CYBERSECURITY]
tags: [AWS,DATA-LEAK,CYBERSECURITY,AI,VULNERABILITY]
---

## Researchers Find Data Leak Risk in AWS Bedrock AI Code Interpreter 🚨

Cybersecurity researchers have identified a vulnerability in an Amazon Web Services (AWS) tool that could allow attackers to steal sensitive company data. The investigation, carried out by Phantom Labs, focused on the AWS Bedrock AgentCore Code Interpreter. AWS Bedrock is a platform for building AI applications, while the AgentCore Code Interpreter allows chatbots to write and run code to perform tasks such as data analysis and calculations.

AWS uses a **Sandbox mode**, which acts as a digital padded cell, blocking the AI’s code from talking to the outside world and keeping it locked away from the internet. However, this isolation is not as secure as many businesses might think. Lead researcher Kinnaird McQuade found that while the sandbox blocks most traffic, it still allows DNS queries, specifically A and AAAA records.

Cybersecurity experts demonstrated that a clever attacker can hide stolen data or secret commands inside these phonebook requests. To prove the risk, the team built a system that ran data through these queries, allowing a live, two-way conversation with the locked AI, effectively bypassing the security walls AWS promised.

According to Phantom Labs’ blog post, the company first alerted AWS in September 2025. By November, AWS released a fix to stop the leaks, but they were forced to pull it back just two weeks later due to technical issues. By late December, AWS decided not to attempt another fix, choosing instead to update its manuals to warn customers about the risk. The flaw received a high-risk severity score of 7.5 out of 10, and the researcher was issued a $100 gift card to the AWS Gear Shop. AWS also issued a public acknowledgment statement: “We would like to thank researcher Kinnaird McQuade for their report, which prompted us to update our documentation to provide additional clarity regarding Sandbox Mode functionality.”

Security experts warn that hackers do not need direct access to exploit these gaps because chatbots can be manipulated in several ways. These include **prompt injection**, where deceptive phrases trick the AI into running malicious code, or **supply chain attacks**, as the Code Interpreter relies on over 270 third-party building blocks, so a single compromised package could create a backdoor when imported. Even standard AI-generated code can get instructions that look safe but actually steal data.

These tools generally have broad access to Amazon S3 storage and Secrets Manager, which store private files and passwords. If an attacker triggers the DNS leak, they can “whisper” sensitive data out of the network, which, researchers note, could lead to “data breaches of sensitive customer information” or even the “deleted infrastructure” of a company. 

To stay safe, AWS suggests switching to **VPC mode** for better control and ensuring AI tools operate with the bare minimum permissions required. Ram Varadarajan, CEO at Acalvio, noted that “AWS Bedrock’s sandbox isolation failed at the most fundamental layer, DNS.” Jason Soroko, Senior Fellow at Sectigo, advised, “Administrators should inventory all active AgentCore Code Interpreter instances and immediately migrate those handling critical data from Sandbox mode to VPC mode,” adding that teams must also rigorously audit IAM roles to enforce the principle of least privilege.

[Read full article](https://hackread.com/data-leak-risk-in-aws-bedrock-ai-code-interpreter/)