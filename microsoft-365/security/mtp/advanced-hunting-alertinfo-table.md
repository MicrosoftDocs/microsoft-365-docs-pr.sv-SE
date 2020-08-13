---
title: AlertInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser för aviseringar i AlertInfo-tabellen för det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, varning, allvarlighets grad, kategori, MITRE, att&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS och Azure ATP
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
ms.openlocfilehash: 36e76ae097dc31c6d7eb7eeff18dd2128ff0cc5c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649493"
---
# <a name="alertinfo"></a>AlertInfo

**Gäller för:**
- Microsoft Hotskydd



`AlertInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `AlertId` | strängvärdet | Unik identifierare för aviseringen |
| `Title` | strängvärdet | Aviseringens rubrik |
| `Category` | strängvärdet | Typ av hot indikator eller överträdelse aktivitet som identifieras av aviseringen |
| `Severity` | strängvärdet | Anger den potentiella effekten (hög, medel eller lågt) för hotets indikatorn eller överträdelse aktiviteten som identifieras av varningen |
| `ServiceSource` | strängvärdet | Produkt eller tjänst som tillhandahöll aviserings informationen |
| `DetectionSource` | strängvärdet | Identifierings teknik eller sensor som identifierar den mest viktiga komponenten eller aktiviteten |
| `AttackTechniques` | strängvärdet | MITRE to&CK tekniker som är kopplade till aktiviteten som utlöste aviseringen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
