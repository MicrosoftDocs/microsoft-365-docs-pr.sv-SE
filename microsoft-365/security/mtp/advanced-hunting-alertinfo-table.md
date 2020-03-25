---
title: AlertInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om händelser för aviseringsgenerering i alertinfo-tabellen i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, allvarlighetsgrad, kategori, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929522"
---
# <a name="alertinfo"></a>AlertInfo (varningInfo)

**Gäller:**
- Microsofts hotskydd



Tabellen `AlertInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `AlertId` | Sträng | Unik identifierare för aviseringen |
| `Title` | Sträng | Registreringens namn |
| `Category` | Sträng | Typ av hotindikator eller överträdelseaktivitet som identifierats av registreringen |
| `Severity` | Sträng | Anger den potentiella påverkan (hög, medel eller låg) av hotindikatorn eller brottsaktiviteten som identifierats av |
| `ServiceSource` | Sträng | Produkt eller tjänst som tillhandahöll varningsinformationen |
| `DetectionSource` | Sträng | Detektionsteknik eller sensor som identifierade den anmärkningsvärda komponenten eller aktiviteten |
| `AttackTechniques` | Sträng | MITRE ATT&CK-tekniker som är associerade med aktiviteten som utlöste aviseringen |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
