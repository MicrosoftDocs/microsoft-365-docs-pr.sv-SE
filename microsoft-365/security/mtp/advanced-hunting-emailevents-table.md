---
title: Tabellen EmailEvents i det avancerade jaktschemat
description: Lär dig mer om händelser som är associerade med Microsoft 365-e-postmeddelanden i tabellen EmailEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-posthändelser, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, bifogad filnamn, dom för skadlig kod, phishing-dom, antal bilagor, antal länkar, url-antal
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
ms.openlocfilehash: be86f446e05952f7e88dc32e12a6a0d05e380afd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515861"
---
# <a name="emailevents"></a>EmailEvents

**Gäller:**
- Microsoft Hotskydd



`EmailEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om händelser som involverar bearbetning av e-postmeddelanden på Office 365 ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `EmailId` | Sträng | Unik e-post- och mottagaridentifierare |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, som genereras av Microsoft 365 |
| `InternetMessageId` | Sträng | Offentlig identifierare för e-postmeddelandet som anges av det sändande e-postsystemet |
| `SenderMailFromAddress` | Sträng | Avsändaradress i MAIL FROM-huvudet, även känd som kuvertavsändaren eller retursökvägsadressen |
| `SenderFromAddress` | Sträng | Avsändare e-postadress i FRÅN-huvudet, som är synlig för e-postmottagare på deras e-postklienter |
| `SenderMailFromDomain` | Sträng | Avsändardomän i MAIL FROM-huvudet, även känd som kuvertavsändaren eller retursökvägsadressen |
| `SenderFromDomain` | Sträng | Avsändaredomän i FRÅN-huvudet, som är synlig för e-postmottagare på deras e-postklienter |
| `SenderIPv4` | Sträng | IPv4-adressen för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `SenderIPv6` | Sträng | IPv6-adressen för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `RecipientEmailAddress` | Sträng | Mottagarens e-postadress eller mottagarens e-postadress efter utvidgning av distributionslistan |
| `Subject` | Sträng | Ämnet för e-postmeddelandet |
| `EmailClusterId` | Sträng | Identifierare för gruppen av liknande e-postmeddelanden klustrade baserat på heuristisk analys av deras innehåll |
| `EmailDirection` | Sträng | E-postmeddelandets riktning i förhållande till nätverket: Inkommande, Utgående, Intra-org |
| `DeliveryAction` | Sträng | Leveransåtgärd för e-postmeddelandet: Levererad, skräppost, blockerad eller ersatt |
| `DeliveryLocation` | Sträng | Plats där e-postmeddelandet levererades: Inkorg/mapp, lokalt/externt, Skräppost, Karantän, Misslyckades, Tappade, Borttagna objekt |
| `PhishFilterVerdict` | Sträng | Dom av e-filtrering stack på om e-post är phish: Phish eller inte Phish |
| `PhishDetectionMethod` | Sträng | Metod som används för att upptäcka e-post som en phish: Skadlig URL rykte, ATP Säkra länkar URL Detonation, Avancerad phish filter, Allmänt phish filter, Anti-Spoof: Intra-org, Anti-parodi: extern domän, Domän personifiering, Användare personifiering, Brand personifiering |
| `MalwareFilterVerdict` | Sträng | Dom av e-filtrering stack på om e-post innehåller skadlig kod: Malware, Inte skadlig kod |
| `MalwareDetectionMethod` | Sträng | Metod som används för att upptäcka skadlig kod i e-post: Antimalware motor, File rykte, ATP säkra bilagor |
| `FinalEmailAction` | Sträng | Slutliga åtgärder som vidtas på e-postmeddelandet baserat på filterutlåtande, principer och användaråtgärder: Flytta meddelande till skräppostmappen, Lägg till X-header, Ändra ämne, Omdirigera meddelande, Ta bort meddelande, skicka till karantän, Ingen åtgärd vidtas, Hemlig meddelande |
| `FinalEmailActionPolicy` | Sträng | Åtgärdspolicy som trädde i kraft: Antispam högt förtroende, Antispam, Antispam bulkpost, Antispam phishing, Anti-phishing domän personifiering, Anti-phishing användare personifiering, Anti-phishing parodi, Anti-phishing graf personifiering, Antimalware, Säkra bilagor, Enterprise Transport Rules (ETR) |
| `FinalEmailActionPolicyGuid` | Sträng | Unik identifierare för den princip som fastställde den slutliga e-poståtgärden |
| `AttachmentCount` | Int | Antal bifogade filer i e-postmeddelandet |
| `UrlCount` | Int | Antal inbäddade url:er i e-postmeddelandet |
| `EmailLanguage` | Sträng | Det identifierade språket i e-postinnehållet |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
