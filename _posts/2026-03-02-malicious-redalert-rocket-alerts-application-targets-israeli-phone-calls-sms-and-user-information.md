---
title: Malicious RedAlert - Rocket Alerts Application Targets Israeli Phone Calls, SMS, and User Information
date: 2026-03-02
categories: [SECURITY]
tags: [MALICIOUS,REDALERT,ROCKET,ALERTS,ISRAEL,USER,INFORMATION]
---

## Malicious RedAlert - Rocket Alerts Application

🚨 **Overview**: On October 13, 2023, Cloudflare’s Cloudforce One Threat Operations Team became aware of a website hosting a Google Android Application (APK) impersonating the legitimate RedAlert - Rocket Alerts application. Since the attacks from Hamas began on October 7, 2023, more than 5,000 rockets have been launched into Israel. Applications that alert users of incoming airstrikes have become targets. Recently, the Pro-Palestinian hacktivist group AnonGhost exploited a vulnerability in another application, “Red Alert: Israel.”

### Recent Developments

In the last two days, a new malicious website ([hxxps://redalerts[.]me](https://redalerts.me)) has advertised the download of the well-known open-source application RedAlert by Elad Nava. The malicious website differs from the legitimate one ([hxxps://redalert[.]me](https://redalert.me)) by only one letter. It hosted links to both the iOS and Android versions of the RedAlert app, but the link for the Android version directly downloads a malicious APK file. This incident highlights the dangers of sideloading applications from the Internet rather than using approved app stores.

### Impact and Recommendations

The malicious RedAlert version imitates the legitimate application while simultaneously collecting sensitive user data. Users who installed the Android version from this specific website are urged to delete the app immediately. The malicious application requests excessive permissions, including:
- `android.permission.GET_ACCOUNTS`
- `android.permission.QUERY_ALL_PACKAGES`
- `android.permission.READ_CALL_LOG`
- `android.permission.READ_CONTACTS`
- `android.permission.READ_PHONE_NUMBERS`
- `android.permission.READ_PHONE_STATE`
- `android.permission.READ_PRIVILEGED_PHONE_STATE`
- `android.permission.READ_SMS`

Upon opening the app, a malicious service starts in the background to gather data from victims’ phones and upload it to the actor’s secure server. The data collected includes:
- SIM information (IMEI and IMSI numbers)
- Full contact list
- All SMS messages (content and metadata)
- List of accounts associated with the device
- All phone calls and conversation details
- Logged-in email and app accounts
- List of installed applications

### Conclusion

If you have installed RedAlert on your device, check for the extraneous permissions added by the actor. The presence of permissions such as Call Logs, Contacts, Phone, and SMS indicates compromise. Users should delete the RedAlert application and reinstall the legitimate version directly from the Play Store. To avoid similar attacks, keep your mobile device updated with the latest software version at all times.

For further details, please read the complete article: [Read full article](https://www.cloudflare.com/threat-intelligence/research/report/malicious-redalert-rocket-alerts-application-targets-israeli-phone-calls-sms-and-user-information/)