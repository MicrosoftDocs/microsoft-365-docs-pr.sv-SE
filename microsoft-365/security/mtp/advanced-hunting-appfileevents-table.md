---
title: AppFileEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om filrelaterade händelser som är kopplade till moln program och-tjänster i tabellen AppFileEvents i det avancerade Antivirus schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App-säkerhet, MCAS
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
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430157"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`AppFileEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om filrelaterade aktiviteter i moln program och tjänster som övervakas av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `FileName` | strängvärdet | Namnet på filen som den inspelade åtgärden tillämpades för |
| `FolderPath` | strängvärdet | Mapp som innehåller filen som den inspelade åtgärden tillämpades för |
| `PreviousFileName` | strängvärdet | Ursprungligt namn på den fil som har bytt namn som resultat av åtgärden |
| `PreviousFolderPath` | strängvärdet | Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades |
| `Protocol` | strängvärdet | Använda nätverks protokoll |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountUpn` | strängvärdet | Kontots huvud namn (UPN) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten |
| `DeviceType` | strängvärdet | Enhets typ | 
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på enheten. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | strängvärdet | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | strängvärdet | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | strängvärdet | IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `Location` | strängvärdet | Ort, land eller annan geografisk plats som är kopplad till evenemanget |
| `Isp` | strängvärdet | Internet leverantör (ISP) associerad med slut punktens IP-adress |
| `ReportId` | tids | Unik identifierare för händelsen |
| `AdditionalFields` | strängvärdet | Ytterligare information om enheten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
