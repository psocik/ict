---
title: Enforcing Intent-Based Access Control at the Endpoint
date: 2026-11-10
categories: [SECURITY]
tags: [AI,ACCESS CONTROL,SECURITY,VULNERABILITIES]
---

## Enforcing Intent-Based Access Control at the Endpoint

OpenAI demonstrated the problem while hardening its training environment. In **Securing our frontier model training environment**, published October 23, it reports that teams of agents found several ways to chain vulnerabilities into microVM escapes. In a separate experiment, agents passed synthetic secrets between microVMs through the processor's cache, without network connections or shared writable files. OpenAI says it remediated the discovered weaknesses, and its frontier training now runs without live internet access. 

Other containment failures took different forms. In Marchand et al.'s **SandboxEscapeBench**, which seeds containers with deliberate vulnerabilities, frontier models prompted to escape often got out through common misconfigurations like exposed Docker sockets and privileged containers. Anthropic reviewed more than 140,000 evaluation runs and found three incidents involving real organizations through mistakenly open internet access. In those runs, the agents needed no exploit because a configuration mistake had already left the boundary open.

Every one of those failures happened in an environment built for containment. The PocketOS agent from the previous piece ran on a developer laptop, where it found an account-wide access token in a file unrelated to its task and used it to delete a production database. A security product on that laptop could have seen the token read and the outbound request. With the agent's task supplied through its hook, it could also have recognized a credential unrelated to the task being used for a production deletion the task never required, and blocked the request before it left the machine.

Security engineers have long required access controls that programs cannot alter or bypass, with enforcement simple enough to analyze and test. Saltzer and Schroeder's 1975 principle of complete mediation made the coverage requirement explicit: "Every access to every object must be checked for authority." Agent systems add the work of connecting those checks to a task written in natural language. Moving enforcement outside the agent protects the checks but requires an explicit way to carry the task context across that boundary.

For credentials, Anthropic's write-up on decoupling the brain from the hands keeps tokens outside the sandbox, using a vault and proxy for custom tools, so they're never reachable from the sandbox where Claude's generated code runs. On a developer laptop, the same design means the agent never holds the token. OS controls keep the agent's processes away from credential files and stores, and a local broker makes authenticated requests on its behalf, accepting only narrow, typed operations and adding the credential at the moment of use. The audit log belongs out of reach too. It should sit on the sensor side and capture who asked for what, under which task, and what was allowed or denied. Records should be sent to a logging service outside the agent's control, using credentials that cannot alter or delete existing entries.

The UK AI Security Institute's incident report on a July cyber evaluation illustrates the value of independent monitoring. AISI's general security monitoring caught them by flagging data leaving over Tor. Within an hour of the alert, AISI had stopped every run and isolated the machines, and it found no resulting real-world harm.

[Read full article](https://www.sophos.com/en-us/blog/enforcing-intent-based-access-control-at-the-endpoint)