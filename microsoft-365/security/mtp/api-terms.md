---
title: Licens och användningsvillkor för Microsoft 365 Defender API:er
description: Beskrivning av licensen och användningsvillkoren för API:er i Microsoft 365 Defender
keywords: api, apis, licens, villkor, apis, juridiskt, meddelanden, uppförandekod
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930960"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licens och användningsvillkor för Microsoft 365 Defender API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="official-terms"></a>Officiella villkor

Microsoft 365 Defender API:er styrs av [MicrosoftS API-licens och användningsvillkor.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Juridiska meddelanden

Microsoft och alla deltagare ger dig en licens till [](https://github.com/MicrosoftDocs/microsoft-365-docs)Microsofts dokumentation och annat innehåll på den här lagringsplatsen under den internationella Creative Commons Attribution 4.0-licensen. Mer information finns i [FILEN](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) LICENS.

Microsoft, Windows, Microsoft Azure och/eller andra produkter och tjänster från Microsoft som refereras i dokumentationen kan vara varumärken eller registrerade varumärken som tillhör Microsoft i USA och/eller andra länder.

Licenserna för det här projektet ger dig inte rättigheter att använda namn, logotyper eller varumärken från Microsoft. Microsofts allmänna riktlinjer för varumärken finns för [Microsofts varumärken.](https://go.microsoft.com/fwlink/?LinkID=254653)

Information om sekretess finns under [Sekretess på Microsoft.](https://privacy.microsoft.com)

Microsoft och alla deltagare förbehåller sig alla övriga rättigheter, oavsett om de omfattas av respektive copyright, patent eller varumärken, vare sig underför tiden, genom estoppel eller på annat sätt.

## <a name="other-restrictions"></a>Andra begränsningar

Api:t för avancerad sökning [har](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) vissa begränsningar av antalet resultat som returneras och vilka data som kan efterfrågas.

1. Du kan bara fråga data från de senaste 30 dagarna.
1. Resultatet kommer att omfatta högst 100 000 rader.

### <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Tröskelvärden för Microsoft 365 Defender-API:er har begränsningströskel.

- **API för** incidenter: Upp till 50 samtal per minut eller 1 500 samtal per timme.
- **Advanced Hunting API:** Upp till 15 samtal per minut, 10 minuters körning per timme och 4 timmars körtid per dag.

HTTP-svarsstatuskoden som anger begränsning `429` är.

Om din begäran har begränsats anger svarstexten tiden då du kan börja göra begäranden igen.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över API:er för Microsoft 365 Defender](api-overview.md)
- [Microsoft 365 Defender API: er som stöds](api-supported.md)
- [Få åtkomst till API:er för Microsoft 365 Defender](api-access.md)
