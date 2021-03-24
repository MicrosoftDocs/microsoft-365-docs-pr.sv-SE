---
title: Tabellen AppFileEvents i det avancerade sökschemat
description: Läs mer om filrelaterade händelser som är associerade med molnappar och -tjänster i tabellen AppFileEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071641"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `AppFileEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!WARNING]
>Den här tabellen kommer att dras tillbaka snart. Den 7 mars 2021 är tabellen inte `AppFileEvents` längre loggningsposter. Användare som vill söka igenom filrelaterade aktiviteter i molntjänster på och efter det datum som det är sagt bör använda [CloudAppEvents-tabellen](advanced-hunting-cloudappevents-table.md) i stället. <br><br>Se till att söka efter frågor och anpassade identifieringsregler som fortfarande använder `AppFileEvents` tabellen och redigera dem för att använda `CloudAppEvents` tabellen. Mer information om hur du konverterar påverkade frågor finns i Sök efter [molnappaktiviteter med avancerad sökning i Microsoft 365 Defender.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `PreviousFileName` | sträng | Det ursprungliga namnet på filen som ändrades till följd av åtgärden |
| `PreviousFolderPath` | sträng | Originalmapp som innehåller filen innan den inspelade åtgärden tillämpats |
| `Protocol` | sträng | Nätverksprotokoll som används |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | sträng | Typ av enhet | 
| `OSPlatform` | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | sträng | IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation |
| `Port` | sträng | TCP-port som används under kommunikation  |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationIPAddress` | sträng | IP-adress för den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationPort` | sträng | Målport för relaterad nätverkskommunikation |
| `Location` | sträng | Stad, land eller annan geografisk plats som är kopplad till händelsen |
| `Isp` | sträng | Internetleverantör (ISP) som är kopplad till slutpunktens IP-adress |
| `ReportId` | long | Unikt ID för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
