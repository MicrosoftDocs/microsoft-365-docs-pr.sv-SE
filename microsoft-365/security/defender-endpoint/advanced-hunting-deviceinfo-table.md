---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Mer information om OS, datornamn och annan enhetsinformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceinfo, device, OS, platform, users, DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500835"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Tabellen i det avancerade sökschemat innehåller information om enheter i organisationen, bland annat `DeviceInfo` deras OS-version, aktiva användare och datornamn. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `ClientVersion` | sträng | Version av slutpunktsagenten eller sensorn som körs på enheten |
| `PublicIP` | sträng | Offentlig IP-adress som används av den onboarded enheten för att ansluta till Defender för Slutpunkt-tjänsten. Detta kan vara IP-adressen för enheten själv, en NAT-enhet eller en proxy |
| `OSArchitecture` | sträng | Arkitekturen för operativsystemet som körs på enheten |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7 |
| `OSBuild` | sträng | Version av operativsystemet som körs på enheten |
| `IsAzureADJoined` | boolesk | Boolesk indikator om enheten är ansluten till Azure Active Directory |
| `LoggedOnUsers` | sträng | Lista över alla användare som är inloggade på enheten vid tiden för händelsen i JSON-matrisformat |
| `RegistryDeviceTag` | sträng | Enhetstagg som lagts till i registret |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `OSVersion` | sträng | Version av operativsystemet som körs på enheten |
| `MachineGroup` | sträng | Datorgruppen på datorn. Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
