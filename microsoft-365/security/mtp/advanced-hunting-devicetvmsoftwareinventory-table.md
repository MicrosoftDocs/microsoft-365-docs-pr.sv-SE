---
title: DeviceTvmSoftwareInventory-tabell i det avancerade sökschemat
description: Läs mer om lagret av programvara på dina enheter i tabellen DeviceTvmSoftwareInventory i det avancerade schemat för sökning.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0bdd3b8564a01b36d1c21d0f49a29ce1afd98348
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907334"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Viss information handlar om en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.


Tabellen i det avancerade sökschemat innehåller inventeringen av & Sårbarhetshantering för programvara som är installerad på enheter i nätverket, inklusive information om slutet `DeviceTvmSoftwareInventory` på supporten. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Du kan till exempel leta efter händelser som innefattar enheter som installeras med en för närvarande sårbar programvaruversion. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

>[!NOTE]
> Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen. Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av trådlöst arbete eller för att leta efter sårbara enheter.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `OSVersion` | sträng | Version av operativsystemet som körs på datorn |
| `OSArchitecture` | sträng | Arkitekturen för operativsystemet som körs på datorn |
| `SoftwareVendor` | sträng | Namnet på programvaruleverantören |
| `SoftwareName` | sträng | Namnet på programvaruprodukten |
| `SoftwareVersion` | sträng | Versionsnummer för programvaran |
| `EndOfSupportStatus` | sträng | Visar livscykelfasen för programvaruprodukten i förhållande till dess angivna datum för support (EOS) eller slutet av livscykeln (EOL) |
| `EndOfSupportDate` | sträng | Supportdatum (EOS) eller slutet på livscykeln (EOL) för programvaran |



## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)