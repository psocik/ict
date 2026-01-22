---
title: Peruvian Loan Scam Harvests Cards and PINs via Fake Applications
date: 2026-01-21
categories: [SCAM]
tags: [PHISHING,CYBERSECURITY,FINANCIAL FRAUD]
---

A large-scale loan phishing operation in Peru has been uncovered, showing how cybercriminals are abusing fake loan applications to steal valid card numbers and PIN codes from unsuspecting users. Active since 2024, the campaign impersonates well-known financial institutions and relies on polished social engineering to appear trustworthy from start to finish. 

According to new findings by Group-IB, the depth of validation built into the scam is particularly concerning. Rather than collecting data indiscriminately, the infrastructure filters out low-quality entries and focuses only on usable financial credentials. The researchers have identified at least 16 scam domains posing as a leading Peruvian bank and around 370 unique domains overall linked to the operation. 

Group-IB explained that the scam begins with targeted social media advertisements promoting fast and accessible loans. Between 2024 and 2025, approximately 35 unique ads were identified as part of the campaign. Each ad redirects users to a phishing site that mimics a legitimate loan application portal. 

Victims are first asked to enter their national ID number, such as a DNI. Although basic checks are applied to the length of the number, any valid-looking input is accepted. This early success builds confidence and encourages users to continue. Once inside the application flow, users are shown personalised loan offers and asked to submit contact information. The process then reaches a critical point: identity verification. Users are offered two options: facial recognition or bank card validation. Facial recognition is deliberately broken and always fails, leaving card entry as the only path forward. Card numbers are verified using the Luhn algorithm, ensuring only genuine cards proceed. After validation, victims are prompted to enter additional sensitive information, including online banking passwords and a 6-digit PIN. At this stage, the credentials are fully monetizable. 

Although Peru is the primary target, the campaign has expanded across Latin America. Financial brands in Colombia, El Salvador, Chile, and Ecuador have also been impersonated using the same infrastructure. This convergence of psychological manipulation and technical precision underscores the importance of threat intelligence in understanding regional scam tactics and developing meaningful countermeasures, warned Group-IB. 

To protect against this and similar threats, cybersecurity experts recommend that financial institutions educate customers on spotting suspicious loan offers, strengthen digital risk monitoring, adopt layered defenses such as multi-factor authentication, and share intelligence with peers. Consumers should use official channels, verify URLs, and avoid sharing sensitive details. Regulators and policymakers are encouraged to foster regional collaboration, support awareness campaigns, and hold digital advertisers accountable for fraudulent activity. 

For the complete article, visit: [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/loan-scam-harvests-cards-pins/)