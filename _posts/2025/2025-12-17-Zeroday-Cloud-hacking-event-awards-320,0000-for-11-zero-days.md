---
title: Zeroday Cloud hacking event awards $320,0000 for 11 zero days
date: 2025-12-17
categories: [SECURITY]
tags: [HACKING,VULNERABILITIES,CLOUD,COMPETITION,CYBERSECURITY]
---

The Zeroday Cloud hacking competition in London has awarded researchers $320,000 for demonstrating critical remote code execution vulnerabilities in components used in cloud infrastructure. The first hacking event focused on cloud systems, the competition is hosted by Wiz Research in partnership with Amazon Web Services, Microsoft, and Google Cloud. The researchers were successful in 85% of the hacking attempts across 13 hacking sessions, demonstrating 11 zero-day vulnerabilities.

A blog post summarizing the event notes $200,000 was awarded during the first day for successful exploitation of issues in Redis, PostgreSQL, Grafana, and the Linux kernel. During the second day, researchers earned another $120,000, showing exploits in Redis, PostgreSQL, and MariaDB, the most popular databases used by cloud systems to store critical information (e.g., credentials, secrets, sensitive user information). Researchers at cybersecurity companies Zellic and DEVCORE were awarded $40,000 for their success.

The Linux kernel was compromised through a container escape flaw, which allowed attackers to break isolation between cloud tenants, undermining a core cloud security guarantee. Artificial Intelligence was also a topic, with hacking attempts targeting the vLLM and Ollama models, which could have exposed private AI models, datasets, and prompts, but both attempts failed due to time exhaustion.

The end of the first Zeroday Cloud competition found Team Xint Code crowned champion for successfully exploiting Redis, MariaDB, and PostgreSQL. For its three exploits, Team Xint Code received $90,000. Despite the positive outcome, the amount awarded is only a small fraction of the total prize pool of $4.5 million available for researchers showcasing exploits for various targets. The eligible categories and products that didn't see any exploits in the competition include AI (Ollama, vLLM, Nvidia Container Toolkit), Kubernetes, Docker, web servers (nginx, Apache Tomcat, Envoy, Caddy), Apache Airflow, Jenkins, and GitLab CE.

[Read the full article here](https://www.bleepingcomputer.com/news/security/zeroday-cloud-hacking-event-awards-320-0000-for-11-zero-days/)
