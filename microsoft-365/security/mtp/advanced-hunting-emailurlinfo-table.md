---
title: MailUrlInfo tabellen i det avancerade jaktschemat
description: Lär dig mer om URL eller länkinformation i tabellen EmailUrlInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailUrlInfo, nätverksmeddelande-ID, url, länk
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
ms.openlocfilehash: 47486f34f9926d83e52ba206f63d3e85286527dc
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515825"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Gäller:**
- Microsoft Hotskydd

`EmailUrlInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om webbadresser i e-postmeddelanden och bilagor som bearbetas av Office 365 ATP. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `UrlId` | Sträng | Unik identifierare för webbadressen i e-postämnet, brödtexten eller bilagan |
| `NetworkMessageId` | Sträng | Unik identifierare för e-postmeddelandet, som genereras av Microsoft 365 |
| `Url` | Sträng | Fullständig WEBBADRESS i e-postämnet, brödtexten eller bilagan |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
