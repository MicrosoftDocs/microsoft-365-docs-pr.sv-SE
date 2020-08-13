---
title: EmailUrlInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om URL-eller länk information i EmailUrlInfo-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, EmailUrlInfo, nätverks meddelande-ID, URL, länk
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
ms.openlocfilehash: aa81628368cbaac121e2930bde9d5498f8d71f17
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649337"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Gäller för:**
- Microsoft Hotskydd

`EmailUrlInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om URL: er för e-postmeddelanden och bifogade filer som bearbetas av Office 365 ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `UrlId` | strängvärdet | Unik identifierare för URL: en i e-postämnet, bröd texten eller bilagan |
| `NetworkMessageId` | strängvärdet | Unik identifierare för e-postmeddelandet, genererat av Microsoft 365 |
| `Url` | strängvärdet | Fullständig URL i e-postämnet, bröd texten eller bilagan |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
