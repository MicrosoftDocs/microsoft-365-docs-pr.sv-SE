---
title: Ordning och prioritet för e-postskydd
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Defender för identitet
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om programordningen för skydd i Exchange Online Protection (EOP), och hur prioritetsvärdet i skyddsprinciperna avgör vilken princip som används.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24d43aeb70e2cdef4bdf65fd3943cdfda9ec3862
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539017"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordning och prioritet för e-postskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan inkommande e-post flaggas med flera olika skyddsformer. Till exempel finns de inbyggda principer för skydd mot nätfiske i EOP som är tillgängliga för alla Microsoft 365-kunder, och de robustare principerna för skydd mot nätfiske som är tillgängliga för Microsoft Defender för Office 365 kunder. Meddelanden passerar även genom flera identifieringssökningar för skadlig kod, skräppost, nätfiske osv. Med hänsyn till all den här aktiviteten kan det finnas viss förvirring kring vilken princip som tillämpas.

I allmänhet identifieras en princip som tillämpas på ett meddelande i rubriken **X-Forefront-Antispam-Report** i **egenskapen CAT (Kategori).** Mer information finns i [Rubriker för skräppostmeddelanden.](anti-spam-message-headers.md)

Det finns två viktiga faktorer som avgör vilken princip som ska tillämpas på ett meddelande:

- **Prioriteten för e-postskyddstypen:** Den här ordningen kan inte konfigureras och beskrivs i följande tabell:

  <br>

  ****

  |Prioritet|E-postskydd|Kategori|Här kan du hantera|
  |---|---|---|---|
  |1|Skadlig programvara|CAT:MALW|[Konfigurera principer för skydd mot skadlig programvara i EOP](configure-anti-malware-policies.md)|
  |2|Fiske|CAT:PHSH|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |3|Skräppost med hög konfidens|CAT:HSPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |4|Förfalskning|CAT:SPOOF|[Falska intelligensinsikter i EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Användarpersonifiering (skyddade användare)|UIMP|[Konfigurera principer mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domänpersonifiering (skyddade domäner)|DIMP|[Konfigurera principer mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |7|Skräppost|CAT:SPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |8|Massutskick|CAT:BULK|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup>De här funktionerna är endast tillgängliga i principer för skydd mot nätfiske i Microsoft Defender för Office 365.

- **Prioriteten** för principen: För varje typ av policy (skydd mot skräppost, skadlig programvara, skydd mot nätfiske osv.) finns det en standardprincip som gäller för alla, men du kan skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritetsvärde som bestämmer i vilken ordning principerna ska tillämpas. Standardprincipen används alltid sist.

  Om en användare har definierats i flera principer av samma typ tillämpas endast principen med högst prioritet på dem. Eventuella återstående principer av den typen utvärderas inte för användaren (inklusive standardprincipen).

Tänk på följande principer mot nätfiske i Microsoft Defender för Office 365 som gäller för samma användare och ett meddelande som identifieras som både personifiering och förfalskning:

<br>

****

|Principnamn|Prioritet|Personifiering av användare|Förfalskningsskydd|
|---|---|---|---|
|Princip A|1|På|Av|
|Policy B|2|Av|På|
|

1. Meddelandet markeras och behandlas som förfalskning, eftersom förfalskning har högre prioritet (4) än användarpersonifiering (5).
2. Princip A tillämpas på användarna eftersom den har högre prioritet än princip B.
3. Baserat på inställningarna i Princip A vidtas inga åtgärder på meddelandet, eftersom skydd mot förfalskning är inaktiverat i principen.
4. Principbearbetningen avbryts så att princip B aldrig tillämpas för användarna.

Eftersom det är möjligt att samma användare avsiktligt eller oavsiktligt ingår i flera anpassade principer av samma typ kan du använda följande designriktlinjer för anpassade principer:

- Tilldela principer som gäller ett litet antal användare högre prioritet och lägre prioritet för principer som gäller för ett stort antal användare. Kom ihåg att standardprincipen alltid används sist.
- Konfigurera principer med högre prioritet så att du har striktare eller mer specialiserade inställningar än principer med lägre prioritet.
- Överväg att använda färre anpassade principer (använd bara anpassade principer för användare som kräver striktare eller mer specialiserade inställningar).
