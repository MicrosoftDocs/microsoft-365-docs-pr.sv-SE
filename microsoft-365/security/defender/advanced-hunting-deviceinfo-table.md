---
title: DeviceInfo-tabell i det avancerade sökschemat
description: Mer information om OS, datornamn och annan maskininformation i tabellen DeviceInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: d56710f4933a8971230c78d7b3570f14b9bda335
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382631"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `DeviceInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om enheter i organisationen, till exempel OS-version, aktiva användare och datornamn. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ClientVersion` | sträng | Version av slutpunktsagenten eller sensorn som körs på datorn |
| `PublicIP` | sträng | Offentlig IP-adress som används av den onboarded machine för att ansluta till Microsoft Defender för Endpoint-tjänsten. Detta kan vara IP-adressen för själva datorn, en NAT-enhet eller en proxy |
| `OSArchitecture` | sträng | Arkitekturen för operativsystemet som körs på datorn |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7 |
| `OSBuild` | sträng | Version av operativsystemet som körs på datorn |
| `IsAzureADJoined` | boolesk | Boolesk indikator om datorn är ansluten till Azure Active Directory |
| `AadObjectId` | sträng | Unikt ID för enheten i Azure AD |
| `LoggedOnUsers` | sträng | Lista över alla användare som är inloggade på datorn vid tiden för händelsen i JSON-matrisformat |
| `RegistryDeviceTag` | sträng | Maskintagg som lagts till i registret |
| `OSVersion` | sträng | Version av operativsystemet som körs på datorn |
| `MachineGroup` | sträng | Datorgruppen på datorn. Den här gruppen används av rollbaserad åtkomstkontroll för att avgöra åtkomsten till datorn |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
|`AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |

Tabellen `DeviceInfo` innehåller enhetsinformation baserad på hjärtslag, som är periodiska rapporter eller signaler från en enhet. Var femtonde minut skickar enheten ett partiellt hjärtslag som innehåller ofta ändrar attribut som `LoggedOnUsers` . En gång om dagen skickas ett fullständigt hjärtslag som innehåller enhetens attribut.

Du kan använda följande exempelfråga för att få den senaste statusen för en enhet:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
