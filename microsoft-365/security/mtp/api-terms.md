---
title: Microsoft 365 Defender API-licens och användnings villkor
description: 'Beskrivning av licens och användnings villkor för API: er i Microsoft 365 Defender'
keywords: 'API, API: er, licens, villkor, API: er, juridik, meddelanden, uppförandekod'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719304"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API-licens och användnings villkor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

## <a name="official-terms"></a>Officiella villkor

Microsoft 365 Defender API: er lyder under [Microsoft API-licens och användnings villkor](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Juridisk information

Microsoft och alla deltagare tilldelar dig en licens till Microsoft documentation och annat innehåll i [den här databasen](https://github.com/MicrosoftDocs/microsoft-365-docs), under den internationella offentliga licensen för Creative Commons 4,0. Mer information finns i [licens](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) filen.

Microsoft, Windows, Microsoft Azure och/eller andra Microsoft-produkter och-tjänster som hänvisas till i dokumentationen kan vara varumärken eller registrerade varumärken som tillhör Microsoft i USA och andra länder.

Licenserna för det här projektet ger dig inte rättigheterna att använda Microsoft-namn, logo typer eller varumärken. Microsofts allmänna varumärkes rikt linjer finns på [Microsofts varumärken](https://go.microsoft.com/fwlink/?LinkID=254653).

Sekretess information finns på [sekretess på Microsoft](https://privacy.microsoft.com).

Microsoft och alla deltagare förbehåller sig alla andra rättigheter, oavsett om de är under deras respektive upphovs rätt, patent eller varumärken, oavsett om de är implication, estoppel eller på annat sätt.

## <a name="other-restrictions"></a>Andra begränsningar

Det avancerade jakt-API: t har vissa [begränsningar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) för antalet returnerade resultat och vilka data som kan läsas.

1. Du kan bara fråga efter data under de senaste 30 dagarna.
1. Resultaten inkluderar högst 100 000 rader.

### <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Microsoft 365 Defender API: er har begränsningar för begränsning.

- **INCIDENT API**: upp till 50 samtal per minut eller 1500 samtal per timme.
- **Avancerat jakt-API**: upp till 15 samtal per minut, 10 minuters kör tid per timme och 4 timmar med kör tid per dag.

Status koden för HTTP-svar som indikerar begränsning är `429` .

Om din begäran har begränsats visar svars texten den tid när du kan börja göra förfrågningar igen.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Microsoft 365 Defender API: er som stöds](api-supported.md)
- [Gå till API för Microsoft 365 Defender](api-access.md)
