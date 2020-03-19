---
title: Tabellen E-posthändelser i det avancerade jaktschemat
description: Läs mer om händelser som är kopplade till Office 365-e-postmeddelanden i tabellen E-posthändelser i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-posthändelser, nätverksmeddelande-ID, avsändare, mottagare, bilaga id, bilaga namn, malware dom, phishing dom, bilaga räkna, länk räkna, url räkna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 690618bb6379532598e60a4e6664df070dd7e5cb
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811145"
---
# <a name="emailevents"></a>E-postHändelser

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `EmailEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om händelser som innebär bearbetning av e-postmeddelanden på Office 365 ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `EmailId` | Sträng | Unik e-post- och mottagaridentifierare |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, genererad av Office 365 |
| `InternetMessageId` | Sträng | Offentlig identifierare för e-postmeddelandet som har angetts av det sändande e-postsystemet |
| `SenderMailFromAddress` | Sträng | Avsändarens e-postadress i posthuvudet FRÅN, även känd som kuvertavsändaren eller retursökvägen |
| `SenderFromAddress` | Sträng | Avsändarens e-postadress i FRÅN-huvudet, som är synlig för e-postmottagare på sina e-postklienter |
| `SenderMailFromDomain` | Sträng | Avsändarei posthuvudet, även känd som kuvertavsändare eller retursökvägsadress |
| `SenderFromDomain` | Sträng | Avsändarens domän i FRÅN-huvudet, som är synlig för e-postmottagare på sina e-postklienter |
| `SenderIPv4` | Sträng | IPv4-adressen för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `SenderIPv6` | Sträng | IPv6-adressen för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `RecipientEmailAddress` | Sträng | Mottagarens e-postadress eller mottagarens e-postadress efter distributionen sã¤r utvidgning av distributionslistan |
| `Subject` | Sträng | Föremål för e-postmeddelandet |
| `EmailClusterId` | Sträng | Identifierare för gruppen av liknande e-postmeddelanden som är grupperade baserat på heuristisk analys av deras innehåll |
| `EmailDirection` | Sträng | Riktning för e-postmeddelandet i förhållande till ditt nätverk: Inkommande, utgående, Intra-org |
| `DeliveryAction` | Sträng | Leveransåtgärd för e-postmeddelandet: Levererad, Skräppost, Blockerad eller utbytt |
| `DeliveryLocation` | Sträng | Plats där e-postmeddelandet levererades: Inkorg/mapp, lokalt/externt, Skräppost, Karantän, Misslyckades, Tappade, Borttagna objekt |
| `PhishFilterVerdict` | Sträng | Dom av e-filtrering stack på om e-post är phish: Phish eller inte Phish |
| `PhishDetectionMethod` | Sträng | Metod som används för att upptäcka e-postmeddelandet som en phish: Malicious URL rykte, ATP Safe Links URL Detonation, Advanced phish filter, General phish filter, Anti-Spoof: Intra-org, Anti-parodi: extern domän, Domän personifiering, Användare personifiering, Brand Personifiering |
| `MalwareFilterVerdict` | Sträng | Dom av e-filtrering stack på om e-postmeddelandet innehåller skadlig kod: Malware, Inte malware |
| `MalwareDetectionMethod` | Sträng | Metod som används för att upptäcka skadlig kod i e-post: Antimalware motor, Fil rykte, ATP Säkra bilagor |
| `FinalEmailAction` | Sträng | Slutlig åtgärd som vidtas på e-postmeddelandet baserat på filterdom, principer och användaråtgärder: Flytta meddelande till skräppostmapp, Lägg till X-header, Ändra ämne, Omdirigera meddelande, Ta bort meddelande, skicka till karantän, Inga åtgärder som vidtagits, Hemlig meddelande |
| `FinalEmailActionPolicy` | Sträng | Åtgärdspolicy som trädde i kraft: Antispam hög förtroende, Antispam, Antispam bulk post, Antispam phishing, Anti-phishing domän personifiering, Anti-phishing användare personifiering, Anti-phishing parodi, Anti-phishing graf personifiering, Antimalware, Säker Bilagor, Regler för företagstransport (ETR) |
| `FinalEmailActionPolicyGuid` | Sträng | Unik identifierare för principen som fastställde den slutliga e-poståtgärden |
| `AttachmentCount` | Int | Antal bilagor i e-postmeddelandet |
| `UrlCount` | Int | Antal inbäddade webbadresser i e-postmeddelandet |
| `EmailLanguage` | Sträng | Upptäckt språk för e-postinnehållet |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
