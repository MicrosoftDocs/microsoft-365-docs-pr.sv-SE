---
title: AppFileEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser som är associerade med molnappar och molntjänster i tabellen AppFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204761"
---
# <a name="appfileevents"></a>AppFileEvents

**Gäller:**
- Microsoft Hotskydd

`AppFileEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `Application` | Sträng | Ansökan som utförde den inspelade åtgärden |
| `FileName` | Sträng | Namnet på den fil som den registrerade åtgärden tillämpades på |
| `FolderPath` | Sträng | Mapp som innehåller filen som den inspelade åtgärden tillämpades på |
| `PreviousFileName` | Sträng | Det ursprungliga namnet på filen som har bytt namn till följd av åtgärden |
| `PreviousFolderPath` | Sträng | Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades |
| `Protocol` | Sträng | Nätverksprotokoll som används |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Användarens huvudnamn (UPN) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | Sträng | Typ av enhet | 
| `OSPlatform` | Sträng | Plattform för operativsystemet som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | Sträng | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | Sträng | IP-adressen för den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |
| `Isp` | Sträng | Internet-leverantör (ISP) som är associerad med IP-adressen för slutpunkten |
| `ReportId` | Lång | Unik identifierare för händelsen |
| `AdditionalFields` | Sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
