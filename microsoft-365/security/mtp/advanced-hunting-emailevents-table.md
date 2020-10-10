---
title: EmailEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om de händelser som är kopplade till Microsoft 365-e-postmeddelanden i tabellen EmailEvents i det avancerade jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, EmailEvents, nätverks meddelande-ID, avsändare, mottagare, bifogade filer
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 17a7e2ed8e2124bc3ca820cedee7c4f89403d717
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413144"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`EmailEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om händelser som rör bearbetning av e-post i Office 365 ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `EmailId` | strängvärdet | Unikt ID för e-post och mottagare |
| `NetworkMessageId` | strängvärdet | Unik identifierare för e-postmeddelandet, genererat av Microsoft 365 |
| `InternetMessageId` | strängvärdet | Public-Facing ID för e-postmeddelandet som anges i det sändande e-postsystemet |
| `SenderMailFromAddress` | strängvärdet | Avsändarens e-postadress i e-postmeddelandet från huvudet, även kallat kuvert avsändare eller Return-Path adress |
| `SenderFromAddress` | strängvärdet | Avsändarens e-postadress i formuläret från som visas för e-postmottagare på sina e-postklienter |
| `SenderMailFromDomain` | strängvärdet | Avsändarens domän i e-post från huvudet, kallas även för kuvert avsändaren eller Return-Path adress |
| `SenderFromDomain` | strängvärdet | Avsändarens domän i formuläret från som visas för e-postmottagare på sina e-postklienter |
| `SenderIPv4` | strängvärdet | IPv4-adress för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `SenderIPv6` | strängvärdet | IPv6-adress för den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `RecipientEmailAddress` | strängvärdet | E-postadress till mottagaren eller e-postadressen till mottagaren efter expansion av distributions lista |
| `Subject` | strängvärdet | Ämne för e-postmeddelandet |
| `EmailClusterId` | strängvärdet | ID för gruppen med likartade e-postmeddelanden grupperade baserat på heuristisk analys av innehållet |
| `EmailDirection` | strängvärdet | E-postmeddelandets riktning i förhållande till ditt nätverk: inkommande, utgående, inom organisationen |
| `DeliveryAction` | strängvärdet | Leverans åtgärd för e-postmeddelandet: levererat, mottaget, blockerat eller ersatt |
| `DeliveryLocation` | strängvärdet | Plats där e-postmeddelandet levererades: Inkorgen/mapp, lokal/extern, skräp, karantän, misslyckad, avbruten, borttaget |
| `PhishFilterVerdict` | strängvärdet | Verdict av e-postfiltrerings stacken på om e-postmeddelandet är Phish: Phish eller icke-Phish |
| `PhishDetectionMethod` | strängvärdet | Metod som används för att hitta e-post som en Phish: skadlig URL-rykte, säkerhet för säkert Internet ATP URL-Sprängat, Avancerat Phish-filter, Allmänt Phish-filter, programförfalskningar: intra-org, stöldskydd: extern domän, domän användning |
| `MalwareFilterVerdict` | strängvärdet | Verdict av e-postfiltrerings stack på om e-postmeddelandet innehåller skadlig kod: skadlig kod, inte skadlig kod |
| `MalwareDetectionMethod` | strängvärdet | Metod som används för att upptäcka skadlig program vara i e-postmeddelandet: Antiskadlig kod, fil rykte, säkra filer för ATP |
| `FinalEmailAction` | strängvärdet | Slutgiltig åtgärd som vidtas på e-postmeddelandet baserat på filter Verdict, principer och användar åtgärder: flytta meddelande till mappen skräp post, lägga till X-rubrik, ändra ämne, omdirigera meddelande, ta bort meddelande, skicka till karantän, ingen åtgärd vidtogs, hemlig kopia |
| `FinalEmailActionPolicy` | strängvärdet | Åtgärds policy som vidtogs: antispam hög exakthet, antispam, antispam Mass utskick, antispam nätfiske, icke-nätfiske-domän-personifiering, Antinätfiske-användare, förfalskning mot nätfiske, skydd mot nätfiske, antiskadligt, säkra bifogade filer för företags transport (Exchange) |
| `FinalEmailActionPolicyGuid` | strängvärdet | Unik identifierare för den policy som avgjorde den slutgiltiga e-poståtgärden |
| `AttachmentCount` | signera | Antal bilagor i e-postmeddelandet |
| `UrlCount` | signera | Antal inbäddade URL-adresser i e-postmeddelandet |
| `EmailLanguage` | strängvärdet | Identifierat språk för e-postinnehållet |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
