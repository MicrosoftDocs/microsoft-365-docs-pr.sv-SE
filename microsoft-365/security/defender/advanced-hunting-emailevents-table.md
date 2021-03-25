---
title: Tabellen EmailEvents i det avancerade sökschemat
description: Läs mer om händelser som är associerade med e-postmeddelanden från Microsoft 365 i tabellen EmailEvents i den avancerade tabellen för sökning
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, bifogade filer, skadlig kod, skadlig kod, nätfiske, antal bifogade filer, antal länkar, antal url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 086d3ef8777685d17fdcdfdcd937cb120810c78a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073954"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

Tabellen i det avancerade schemat för sökning innehåller information om händelser som innefattar bearbetning `EmailEvents` av e-postmeddelanden på Microsoft Defender för Office 365. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Microsoft 365 |
| `InternetMessageId` | sträng | Offentlig identifierare för det e-postmeddelande som konfigureras av det avsändande e-postsystemet |
| `SenderMailFromAddress` | sträng | Avsändarens e-postadress i sidhuvudet E-POST FRÅN, som även kallas kuvertavsändaren eller Return-Path postadressen |
| `SenderFromAddress` | sträng | Avsändarens e-postadress i sidhuvudet FRÅN, som visas för e-postmottagare i deras e-postklienter |
| `SenderDisplayName` | sträng | Namnet på avsändaren som visas i adressboken, vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn |
| `SenderObjectId` | sträng |Unik identifierare för avsändarens konto i Azure AD |
| `SenderMailFromDomain` | sträng | Sender domain in the MAIL FROM header, also known as the envelope sender or the Return-Path address |
| `SenderFromDomain` | sträng | Sender domain in the FROM header, which is visible to email recipients on their email clients |
| `SenderIPv4` | sträng | IPv4-adress till den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `SenderIPv6` | sträng | IPv6-adress till den senast identifierade e-postservern som vidarebefordrade meddelandet |
| `RecipientEmailAddress` | sträng | Mottagarens e-postadress eller e-postadress efter att distributionslistan expanderat |
| `RecipientObjectId` | sträng | Unikt ID för e-postmottagaren i Azure AD |
| `Subject` | sträng | E-postmeddelandets ämne |
| `EmailClusterId` | sträng | Identifierare för gruppen av liknande e-postmeddelanden grupperade baserat på heuristisk analys av innehållet |
| `EmailDirection` | sträng | E-postriktning i förhållande till ditt nätverk: Inkommande, utgående, årsorganisation |
| `DeliveryAction` | sträng | Leveransåtgärd för e-postmeddelandet: Levererad, Skräppost, Blockerad eller Ersatt |
| `DeliveryLocation` | sträng | Plats där e-postmeddelandet levererades: Inkorg/mapp, Lokal/Extern, Skräppost, Karantän, Misslyckades, Nedsl ett, Borttaget |
| `ThreatTypes` | sträng | Bedömning av e-postfiltreringsstacken utifrån om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot |
| `ThreatNames` | sträng |Namn för identifiering av skadlig programvara eller andra hot som hittas |
| `DetectionMethods` | sträng | Metoder som används för att identifiera skadlig kod, nätfiske eller andra hot som påträffas i e-postmeddelandet |
| `ConfidenceLevel` | sträng | Lista över konfidensnivåer för skräppost- och nätfiskeförsök. För skräppost visar den här kolumnen konfidensnivån för skräppost (SCL), som anger om e-postmeddelandet hoppades över (-1), som hittades inte vara skräppost (0,1), som hittades som skräppost med måttligt förtroende (5,6) eller som hittades vara skräppost med hög konfidens (9). Vid nätfiske visas i den här kolumnen om konfidensnivån är "Hög" eller "Låg". |
| `EmailAction` | sträng | Slutåtgärd för e-postmeddelandet baserat på filterbekräftelse, principer och användaråtgärder: Flytta meddelandet till skräppostmappen, Lägg till X-sidhuvud, Ändra ämne, Omdirigera meddelande, Ta bort meddelande, skicka till karantän, Ingen åtgärd vidtas, Hemlig kopia |
| `EmailActionPolicy` | sträng | Åtgärdspolicy som verkställde: Skräppostskydd med hög säkerhet, skräppostskydd, skräppostskydd, nätfiskeskydd, personifiering mot nätfiske, personifiering mot nätfiske, personifiering av användare mot nätfiske, förfalskning mot nätfiske, personifiering mot nätfiske, Program mot skadlig programvara, Säkra bifogade filer, ETR-regler (Enterprise Transport Rules) |
| `EmailActionPolicyGuid` | sträng | Unikt ID för principen som avgör den slutliga e-poståtgärden |
| `AttachmentCount` | int | Antal bifogade filer i e-postmeddelandet |
| `UrlCount` | int | Antal inbäddade URL:er i e-postmeddelandet |
| `EmailLanguage` | sträng | Upptäckt språk för e-postinnehållet |
| `Connectors` | sträng | Anpassade instruktioner som definierar organisationens e-postflöde och hur e-posten har dirigerats |
| `OrgLevelAction` | sträng | Åtgärder som vidtas på e-postmeddelandet som svar på matchningar mot en princip som definierats på organisationsnivå |
| `OrgLevelPolicy` | sträng | Organisationsprincip som utlöste e-postmeddelandets åtgärd |
| `UserLevelAction` | sträng | Åtgärd som vidtas på e-postmeddelandet som svar på matchningar mot en postlådeprincip som definieras av mottagaren |
| `UserLevelPolicy` | sträng | Postlådeprincip för slutanvändare som utlöste åtgärden för e-postmeddelandet |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
