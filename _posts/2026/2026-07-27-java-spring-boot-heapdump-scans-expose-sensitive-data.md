---
title: Java Spring Boot Heapdump Scans Expose Sensitive Data
date: 2026-07-27
categories: [SECURITY]
tags: [JAVA,SPRING,HEAPDUMP,SECURITY,VULNERABILITY]
---

## Java Spring Boot Heapdump Scans 🚀

Spring Boot exposes the endpoint "/actuator/heapdump" to collect debug information. By default, the endpoint will return a file `heapdump.hprof`, which includes a binary heapdump that can be used to analyze the current state of the application. Non-Java readers may be familiar with a similar concept, core dumps, which are produced by binaries to expose a memory image at the time the software crashes. **Heapdumps** are the Java analog to **core-dumps**. The heapdump often includes secrets used by the application to connect to backend systems. API keys, database passwords, and other sensitive data may be exposed in the heapdump.

The requests we are seeing use a slightly different URL: "/admin-api/actuator/heapdump". I am not sure if the "/admin-api/" prefix is associated with a particular application, but it is a reasonable configuration and may be used by multiple applications. The full request we are seeing:

```
GET /admin-api/actuator/heapdump HTTP/1.1
Host: 68.[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]
User-Agent: python-requests/2.34.2
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
Authorization: Basic YWRtaW46YWRtaW4=
```

The base64-encoded authorization string decodes to "admin:admin," a typical default username and password.

The location of the management endpoints is typically configured in your `application.yml` file with: `management.endpoints.web.base-path=/admin-api/actuator`. Since this is used by Spring Boot, you should be able to restrict access more effectively with **Spring Security**. But the attacker obviously assumes that authentication is configured and just relies on a weak password.

[Read full article](https://isc.sans.edu/forums/diary/Java%20Spring%20Boot%20%22heapdump%22%20scans/33188/)