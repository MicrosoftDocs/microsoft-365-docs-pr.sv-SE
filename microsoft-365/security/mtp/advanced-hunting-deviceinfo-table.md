---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Läs mer om OS, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, maskininfo, Enhetsinfo, enhet, dator, OS, plattform, användare
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145373"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `DeviceInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om maskiner i organisationen, inklusive OS-version, aktiva användare och datornamn. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ClientVersion` | sträng | Version av slutpunktsagenten eller sensorn som körs på datorn |
| `PublicIP` | sträng | Offentlig IP-adress som används av den onboarded machine för att ansluta till Tjänsten Microsoft Defender för slutpunkt. Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxyserver |
| `OSArchitecture` | sträng | Arkitekturen för operativsystemet som körs på datorn |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7 |
| `OSBuild` | sträng | Version av operativsystemet som körs på datorn |
| `IsAzureADJoined` | boolesk | Boolesk indikator om datorn är ansluten till Azure Active Directory |
| `DeviceObjectId` | sträng | Unikt ID för enheten i Azure AD |
| `LoggedOnUsers` | sträng | Lista över alla användare som är inloggade på datorn vid tidpunkten för händelsen i JSON-matrisformat |
| `RegistryDeviceTag` | sträng | Maskintagg som lagts till i registret |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
|`AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `OSVersion` | sträng | Version av operativsystemet som körs på datorn |
| `MachineGroup` | sträng | Datorgruppen på datorn. Den här gruppen används av rollbaserad åtkomstkontroll för att fastställa åtkomsten till datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
