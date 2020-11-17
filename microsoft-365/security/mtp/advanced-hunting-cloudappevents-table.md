---
title: CloudAppEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser från moln program och-tjänster i CloudAppEvents-tabellen för avancerat jakt schema
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, CloudAppEvents, Cloud App-säkerhet, MCAS
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087776"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

För närvarande tillgänglig i förhands granskningen `CloudAppEvents` innehåller tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat information om aktiviteter i olika moln program och-tjänster, särskilt Microsoft Teams och Exchange Online. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Denna tabell expanderar för att omfatta fler aktiviteter som övervakas av Microsoft Cloud App Security. Till sist kommer den här tabellen att innehålla fil aktivitet som lagras i tabellen [AppFileEvents](advanced-hunting-appfileevents-table.md) . Microsoft tillhandahåller ytterligare vägledning när mer data flyttas till den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `ApplicationId` | strängvärdet | Unik identifierare för programmet |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure Active Directory |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `IsAdminOperation` | strängvärdet | Anger om aktiviteten utfördes av en administratör |
| `DeviceType` | strängvärdet | Typ av enhet baserat på syfte och funktioner, till exempel "nätverks enhet", "arbets Station", "Server", "mobil", "spel konsol" eller "skrivare" | 
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på enheten. I den här kolumnen anges specifika operativ system, inklusive varianter inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | strängvärdet | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation |
| `IsAnonymousProxy` | strängvärdet | Anger om IP-adressen tillhör en känd anonym proxyserver |
| `CountryCode` | strängvärdet | Kod med två bokstäver som anger det land där klient-IP-adressen finns |
| `City` | strängvärdet | Ort där klient-IP-adressen finns |
| `Isp` | strängvärdet | Internet leverantör (ISP) associerad med IP-adressen |
| `UserAgent` | strängvärdet | Information om användar agent från webbläsaren eller andra klient program |
| `ActivityType` | strängvärdet | Typ av aktivitet som utlöste händelsen |
| `ActivityObjects` | strängvärdet | Lista över objekt, till exempel filer och mappar, som ingick i den registrerade aktiviteten |
| `ObjectName` | strängvärdet | Namnet på det objekt som den inspelade åtgärden tillämpades på |
| `ObjectType` | strängvärdet | Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpades på |
| `ObjectId` | strängvärdet | Unik identifierare för det objekt som den inspelade åtgärden tillämpades på |
| `ReportId` | strängvärdet | Unik identifierare för händelsen |
| `RawEventData` | strängvärdet | Information om rå händelser från käll programmet eller tjänsten i JSON-format |
| `AdditionalFields` | strängvärdet | Ytterligare information om enheten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
