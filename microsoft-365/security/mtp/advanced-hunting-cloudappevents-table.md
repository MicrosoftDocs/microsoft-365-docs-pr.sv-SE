---
title: CloudAppEvents-tabellen i det avancerade sökschemat
description: Läs mer om händelser från molnappar och -tjänster i tabellen CloudAppEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, CloudAppEvents, Cloud App Security, MCAS
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928459"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Tabellen i det avancerade sökschemat, som för närvarande finns i förhandsversion, innehåller information om aktiviteter i olika molnappar och -tjänster, särskilt `CloudAppEvents` Microsoft Teams och Exchange Online. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Den här tabellen utökas med fler aktiviteter som övervakas av Microsoft Cloud App Security. Så småningom kommer den här tabellen att innehålla filaktivitet som för närvarande lagras i [tabellen AppFileEvents.](advanced-hunting-appfileevents-table.md) Microsoft ger ytterligare vägledning när mer information flyttas till den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `ApplicationId` | sträng | Unikt ID för programmet |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure Active Directory |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn. |
| `IsAdminOperation` | sträng | Anger om aktiviteten utfördes av en administratör |
| `DeviceType` | sträng | Typ av enhet baserat på syfte och funktionalitet, till exempel "Nätverksenhet", "Arbetsstation", "Server", "Mobil", "Spelkonsol" eller "Skrivare" | 
| `OSPlatform` | sträng | Operativsystemets plattform som körs på enheten. Den här kolumnen anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `IsAnonymousProxy` | sträng | Anger om IP-adressen tillhör en känd anonym proxy |
| `CountryCode` | sträng | Kod med två bokstäver som anger landet där klient-IP-adressen är geolokal |
| `City` | sträng | Ort där klient-IP-adressen är geolokal |
| `Isp` | sträng | Internet tjänstprovider (ISP) som är kopplat till IP-adressen |
| `UserAgent` | sträng | Information om användaragenter från webbläsaren eller ett annat klientprogram |
| `ActivityType` | sträng | Typ av aktivitet som utlöste händelsen |
| `ActivityObjects` | sträng | Lista över objekt, till exempel filer eller mappar, som var inblandade i den inspelade aktiviteten |
| `ObjectName` | sträng | Namnet på det objekt som den inspelade åtgärden tillämpats på |
| `ObjectType` | sträng | Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpats på |
| `ObjectId` | sträng | Unikt ID för det objekt som den inspelade åtgärden tillämpats på |
| `ReportId` | sträng | Unikt ID för händelsen |
| `RawEventData` | sträng | Obearbetad händelseinformation från källprogrammet eller källtjänsten i JSON-format |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
