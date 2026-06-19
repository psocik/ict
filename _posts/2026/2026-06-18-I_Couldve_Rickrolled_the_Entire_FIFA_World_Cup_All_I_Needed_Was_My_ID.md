---
title: I Could've Rickrolled the Entire FIFA World Cup. All I Needed Was My ID.
date: 2026-06-18
categories: [CYBERSECURITY]
tags: [FIFA,CYBERSECURITY,VULNERABILITY,HACK]
---

## I Could've Rickrolled the Entire FIFA World Cup! 🎉

When you register on [agents.fifa.org](https://agents.fifa.org), FIFA adds your account to their Microsoft Entra tenant (formerly Azure AD). This tenant powers all of FIFA's internal platforms. After registration, a researcher navigated to [fdp.fifa.org](https://fdp.fifa.org) - FIFA's Football Data Platform. The app authenticated through the shared Entra tenant, checked roles, found none, and displayed: **"Sorry, you do not have any FIFA Football Data Platform role assigned to your account."** This was client-side only; the Angular app checked the JWT for a NO_ROLES marker and rendered the access-denied page. However, the backend APIs didn't check anything. They just served whatever was requested.

After bypassing the client-side guards, the researcher landed on the live production Streaming Management panel for the FIFA World Cup 2026. It exposed every match, camera angle, RTMP ingest URL, and stream key. The streaming infrastructure, hosted on MediaKind, FIFA's streaming technology partner, comprised production endpoints receiving live camera feeds from stadiums. A live tactical camera feed was confirmed playing in VLC. The Streaming Management panel had full controls: Start, stop, schedule for every match and camera angle. If an attacker pushed video to one of those RTMP endpoints with the stream key, they could replace the camera feed. An attacker could have rickrolled the entire FIFA World Cup or played Subway Surfers gameplay live on every TV network worldwide during an active match.

The Streaming Management panel wasn't the only thing exposed. The NO_ROLES account had access to the entire platform, including Competitions, Matches, Teams, Tools, Exchange Platform, Analysis Dashboard, Commentator Information System, FIFA AI Pro, and Admin. The Management tab on [fdp.fifa.org](https://fdp.fifa.org) had write operations accepted by the backend. An attacker could modify editorial commentary notes, adjust the official kick-off moment, send tactical lineup data, and change scores and match statistics, which feeds into the Commentator Information System and gets displayed on live television. This system ([cis.fifa.org](https://cis.fifa.org)) was also accessible, allowing access to every editorial note, pre-match stats kit, and talking point. Additionally, an Azure Function App returned metadata and direct Azure Blob Storage download URLs for 23 internal FIFA files, including transfer reports, revenue comparisons, board-level representation data, and referee and coach statistics.

The discovery occurred during the World Cup, with RTMP URLs active and stream keys exposed. FIFA had no bug bounty program, security.txt, or published security contact. The researcher reported the issue to MediaKind, and CISA (the federal lead on cybersecurity for the FIFA World Cup 2026, including broadcast systems) was successfully contacted via their 24/7 operations center, as was the FBI. The whole situation boils down to one architectural mistake: client-side authorization with no backend validation.

[Read full article](https://bobdahacker.com/blog/fifa-hack)