---
title: AlertInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om händelser för aviseringsgenerering i alertInfo-tabellen i det avancerade jaktschemat
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
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899023"
---
# <a name="alertinfo"></a>AlertInfo

**Gäller:**
- Microsoft Hotskydd



`AlertInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `AlertId` | Sträng | Unik identifierare för aviseringen |
| `Title` | Sträng | Varningens namn |
| `Category` | Sträng | Typ av hotindikator eller överträdelseaktivitet som identifierats av registreringen |
| `Severity` | Sträng | Anger den potentiella påverkan (hög, medel eller låg) av hotindikatorn eller överträdelseaktiviteten som identifierats av |
| `ServiceSource` | Sträng | Produkt eller tjänst som tillhandahöll varningsinformationen |
| `DetectionSource` | Sträng | Detektionsteknik eller sensor som identifierade den anmärkningsvärda komponenten eller aktiviteten |
| `AttackTechniques` | Sträng | MITRE ATT&CK-tekniker som är associerade med aktiviteten som utlöste aviseringen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
