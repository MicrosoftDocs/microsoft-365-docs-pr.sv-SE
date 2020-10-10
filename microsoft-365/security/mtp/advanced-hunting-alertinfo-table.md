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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ca89630a940ea56fd7ad968d1cba8a50dd9f4fa0
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413192"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



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
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
