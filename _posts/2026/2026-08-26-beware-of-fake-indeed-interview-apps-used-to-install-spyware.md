---
title: Beware of Fake Indeed Interview Apps Used to Install Spyware
date: 2026-08-26
categories: [SECURITY]
tags: [SPYWARE,MALWARE,JOB SCAMS,ANDROID APPS]
---

## Beware of Fake Indeed Interview Apps Used to Install Spyware 🚨

From several independent reports, we've seen evidence of scammers using fake Android "interview" apps to target job seekers on the Indeed platform. Indeed is one of the world's largest employment websites, giving scammers access to a huge pool of potential victims, especially in a competitive job market. Users reported being instructed by a supposed employer on Indeed to install an "Interview App" or an APK named MyInterview from a link shared during a job interview. The victim who installed the MyInterview APK said their phone began closing apps by itself after installation.

### Common Scams Include:
- "Complete your interview by installing the Indeed app"
- "Update your Indeed application"
- "Identity verification required"
- "Download our recruitment portal"
- "Salary agreement available after app installation"

An analysis by Malwarebytes Android Malware Researcher Nazeeh Sulaiman showed that these Android apps impersonate Indeed's login page before creating a VPN connection after an applicant enters an email address. Static analysis identified the apps as Trojan.Droppers, capable of installing additional untrusted apps. At the time of writing, the final payload was spyware, although we initially expected a banking Trojan. Once the malware is granted the Accessibility permission, it effectively takes over the device. The interesting thing here is that it can prevent users from uninstalling the malicious app; when the user taps Uninstall in Android Settings, the malware simply forces the screen back, preventing removal.

### Malicious Workflow:
A VPN can give an app substantial influence over the device's network traffic, allowing attackers to route communications through systems they control, hide what the app is doing, or support later stages of the attack.

This malicious app is not affiliated with Indeed. The company's official Android app, Indeed Job Search, is distributed through Google Play, not through an APK supplied in a recruitment message or an unfamiliar interview website. An Indeed spokesperson confirmed: "Interviewing through Indeed's platform happens entirely in a browser and never requires downloading a special app. Any message asking a job seeker to download an app to participate in an interview is not legitimate. We encourage job seekers to avoid clicking links or downloading files from any message directing them to do so." A job interview should not require you to sideload an Android app, enable a VPN connection, or install software from an unknown source. Don't install apps just because someone tells you to, especially if you have to install them outside Google Play. Verify job offers through independent channels.

In this campaign, the supposed interview app is simply the lure: it impersonates Indeed, establishes a suspicious network connection, and is designed to deliver additional malware. Indicators of compromise (IOCs) associated with this activity include the domain: start[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]org, linked to Trojan droppers and dropped malware payloads.

[Read full article](https://www.malwarebytes.com/blog/scams/2026/08/beware-of-fake-indeed-interview-apps-used-to-install-spyware)