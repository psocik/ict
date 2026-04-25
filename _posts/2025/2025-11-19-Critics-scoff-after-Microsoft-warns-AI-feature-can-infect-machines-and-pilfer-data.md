---
title: Critics scoff after Microsoft warns AI feature can infect machines and pilfer data
date: 2025-11-19
categories: [RESEARCH]
tags: [MICROSOFT,AI,SECURITY]
---

Microsoft has issued a warning about its experimental AI agent, Copilot Actions, integrated into Windows, stating that it can potentially infect devices and compromise sensitive user data. This announcement has sparked criticism from security experts questioning the rush to deploy new AI features before fully understanding and mitigating their inherent risks.

Copilot Actions are designed to perform "everyday tasks like organizing files, scheduling meetings, or sending emails," acting as a digital collaborator to boost efficiency. The primary concerns stem from known vulnerabilities present in large language models (LLMs) like Copilot, specifically hallucinations and prompt injection.

Hallucinations refer to the LLM's tendency to provide inaccurate or illogical responses, making it difficult to trust its output without independent verification. Prompt injection is a more severe bug that allows attackers to embed malicious instructions within seemingly benign content like websites or emails. LLMs, programmed to follow instructions indiscriminately, can be tricked into executing these malicious commands, potentially leading to data exfiltration, malware installation, or cryptocurrency theft.

Microsoft acknowledges that "AI models still face functional limitations in terms of how they behave and occasionally may hallucinate and produce unexpected outputs." The company also points to "novel security risks, such as cross-prompt injection (XPIA), where malicious content embedded in UI elements or documents can override agent instructions, leading to unintended actions like data exfiltration or malware installation."

Microsoft advises that only experienced users should enable Copilot Actions, which is currently in beta. However, the company has not provided specific guidance on the type of training or experience required to mitigate the risks. Critics have drawn parallels to Microsoft's long-standing warnings about the dangers of macros in Office apps, which continue to be exploited by attackers despite repeated cautions.

Some experts question whether Microsoft will offer adequate tools for administrators to restrict Copilot Actions or identify affected machines on a network. A Microsoft spokesperson stated IT admins will be able to enable or disable an agent workspace at both account and device levels, using Intune or other Mobile Device Management (MDM) apps.

The core of Microsoft's strategy for securing these agentic features revolves around concepts like non-repudiation (actions must be "observable and distinguishable from those taken by a user"), data confidentiality, and user approval before accessing data or taking actions. However, the effectiveness of these safeguards hinges on users carefully reviewing and understanding permission prompts, a reliance that many critics find inadequate. As Earlence Fernandes, a University of California, San Diego professor specializing in AI security, noted, users might "not fully understand what is going on, or they might just get habituated and click 'yes' all the time," rendering the security boundary ineffective.

To read the complete article see: [Full Article](https://arstechnica.com/security/2025/11/critics-scoff-after-microsoft-warns-ai-feature-can-infect-machines-and-pilfer-data/) 