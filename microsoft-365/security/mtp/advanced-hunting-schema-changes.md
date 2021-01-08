---
title: Namnge ändringar i Microsoft 365 Defender Advanced jakt-schemat
description: Spåra och granska namn ändrings tabeller och kolumner i det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, data, namn ändringar, Byt namn, Microsoft Threat Protection
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780827"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Avancerat schema för att ändra namn på ändringar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Det [avancerade jakt schemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner. I vissa fall byts namn på befintliga kolumn namn eller ersättas för att förbättra användar upplevelsen. I den här artikeln finns information om hur du granskar namn ändringar som kan påverka dina frågor.

Namn ändringar används automatiskt för frågor som sparas i säkerhets Center, inklusive frågor som används av anpassade identifierings regler. Du behöver inte uppdatera dessa frågor manuellt. Men du måste uppdatera följande frågor:
- Frågor som körs med API
- Frågor som sparas någonstans utanför säkerhets Center

## <a name="december-2020"></a>December 2020

| Tabellnamn | Ursprungligt kolumn namn | Nytt kolumn namn | Orsak till ändring
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Feedback från kunder |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Feedback från kunder |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Feedback från kunder |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)