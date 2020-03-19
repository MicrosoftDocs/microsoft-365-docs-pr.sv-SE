---
title: E-postUrlInfo-tabellen i det avancerade jaktschemat
description: Läs mer om URL- eller länkinformation i tabellen EmailUrlInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailUrlInfo, nätverksmeddelande-ID, url, länk
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
ms.openlocfilehash: 7f5912306700efa0db704fe8d0c0db006105fda6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808133"
---
# <a name="emailurlinfo"></a>E-postUrlInfo

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `EmailUrlInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om webbadresser för e-postmeddelanden och bilagor som bearbetas av Office 365 ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `UrlId` | Sträng | Unik identifierare för webbadressen i e-postämnet, brödtexten eller bilagan |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, genererad av Office 365 |
| `Url` | Sträng | Fullständig URL i e-postämnet, brödtexten eller bilagan |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
