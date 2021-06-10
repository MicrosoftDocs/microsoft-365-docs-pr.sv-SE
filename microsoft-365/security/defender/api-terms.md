---
title: Microsoft 365 Defender API:s licens och användningsvillkor
description: Beskrivning av licensen och användningsvillkoren för API:er i Microsoft 365 Defender
keywords: api, apis, licens, villkor, apis, juridiska meddelanden, meddelanden, uppförandekod
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070073"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API:s licens och användningsvillkor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

## <a name="official-terms"></a>Officiella villkor

Microsoft 365 Defender-API:er styrs av [Microsofts API:er licens och användningsvillkor.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Juridiska meddelanden

Microsoft och alla deltagare ger dig en licens till [](https://github.com/MicrosoftDocs/microsoft-365-docs)Microsofts dokumentation och annat innehåll på lagringsplatsen under Creative Commons Attribution 4.0 International Public License. Mer information finns i [licensfilen.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure och/eller andra produkter och tjänster från Microsoft som refereras i dokumentationen kan vara varumärken eller registrerade varumärken som tillhör Microsoft i USA och/eller andra länder.

Licenserna för det här projektet ger dig inte rättigheter att använda microsofts namn, logotyper eller varumärken. Microsofts allmänna riktlinjer för varumärken finns på [Microsofts varumärken.](https://go.microsoft.com/fwlink/?LinkID=254653)

Information om sekretess finns under [Sekretess på Microsoft.](https://privacy.microsoft.com)

Microsoft och alla deltagare förbehåller sig alla övriga rättigheter, oavsett om de omfattas av respektive copyright, patent eller varumärken, vare sig underföregen, genom estoppel eller på annat sätt.

## <a name="other-restrictions"></a>Andra begränsningar

Api:t för avancerad sökning [har](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) vissa begränsningar för antalet resultat som returneras och de data som kan efterfrågas.

1. Du kan bara köra frågor för data från de senaste 30 dagarna.
1. Resultatet kommer att innehålla högst 100 000 rader.

### <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Så Microsoft 365 Defender-API:er har tröskelvärden för begränsning.

- **API för** incidenter: Upp till 50 samtal per minut eller 1 500 samtal per timme.
- **Avancerat API** för sökning: Upp till 15 samtal per minut, 10 minuters körning per timme och 4 timmars körningstid per dag.

HTTP-svarsstatuskoden som anger begränsning är `429` .

Om din begäran har begränsats anger svarstexten tiden då du kan börja begära igen.

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Översikt över Defender-API:er](api-overview.md)
- [Microsoft 365 Defender API: er som stöds](api-supported.md)
- [Komma åt Microsoft 365 Defender-API:er](api-access.md)