---
title: DeviceInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om operativ system, dator namn och annan information om datorn i DeviceInfo-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, machineinfo, DeviceInfo, enhet, maskin, OS, plattform, användare
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
ms.openlocfilehash: 1fa093798b4e7704d5c6c5368dce7cb4081df48b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413240"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`DeviceInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om datorerna i organisationen, inklusive OS-version, aktiva användare och dator namn. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ClientVersion` | strängvärdet | Version av slut punkts agenten eller sensorn som körs på datorn |
| `PublicIP` | strängvärdet | Offentlig IP-adress som används av den inbyggda datorn för att ansluta till Microsoft Defender ATP-tjänsten. Det här kan vara IP-adressen till själva datorn, en NAT-enhet eller en proxy |
| `OSArchitecture` | strängvärdet | Arkitekturen för operativ systemet som körs på datorn |
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på datorn. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7 |
| `OSBuild` | strängvärdet | Version av operativ systemet som körs på datorn |
| `IsAzureADJoined` | returtyp | Boolesk indikator för om datorn är ansluten till Azure Active Directory |
| `LoggedOnUsers` | strängvärdet | Lista över alla användare som är inloggade på datorn när händelsen inträffar i JSON-mat ris format |
| `RegistryDeviceTag` | strängvärdet | Dator tag gen läggs till genom registret |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `OSVersion` | strängvärdet | Version av operativ systemet som körs på datorn |
| `MachineGroup` | strängvärdet | Dator grupp. Den här gruppen används av rollbaserad åtkomst kontroll för att bestämma åtkomst till datorn |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
