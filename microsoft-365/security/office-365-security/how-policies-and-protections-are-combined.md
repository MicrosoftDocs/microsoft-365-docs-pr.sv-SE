---
title: Ordning och prioritet för e-postskydd
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
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
description: Administratörer kan läsa mer om skyddsordningen för program i Exchange Online Protection (EOP) och hur prioritetsvärdet i skyddsprinciperna avgör vilken princip som används.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec21be03280a8b7da122569d51186efc1f756a69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286843"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordning och prioritet för e-postskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan inkommande e-post flaggas med flera olika skyddsformer. Till exempel de inbyggda principer för skydd mot nätfiske i EOP som är tillgängliga för alla Microsoft 365-kunder och de robustare principerna för nätfiske som är tillgängliga för Microsoft Defender för Office 365-kunder. Meddelanden passerar också genom flera söksökningar efter skadlig kod, skräppost, nätfiske och så vidare. Mot den här aktiviteten kan det uppstå viss förvirring vad gäller vilken princip som tillämpas.

I allmänhet identifieras en princip som tillämpas på ett meddelande i **rubriken X-Forefront-Antispam-Report** i **EGENSKAPEN CAT (Kategori).** Mer information finns i [Rubriker för skräppostskydd.](anti-spam-message-headers.md)

Det finns två viktiga faktorer som avgör vilken princip som ska tillämpas på ett meddelande:

- **Prioriteten för e-postskyddstypen:** Den här ordningen kan inte konfigureras och beskrivs i följande tabell:

  ****

  |Prioritet|E-postskydd|Kategori|Här hanterar du|
  |---|---|---|---|
  |1|Skadlig programvara|CAT:MALW|[Konfigurera principer för skydd mot skadlig programvara i EOP](configure-anti-malware-policies.md)|
  |2|Fiske|CAT:PHSH|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |3|Skräppost med hög konfidens|CAT:HSPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |4|Förfalskning|CAT:SPOOF|[Konfigurera förfalskningsinformation i EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Användarpersonifiering (skyddade användare)|UIMP|[Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domänpersonifiering (skyddade domäner)|DIMP|[Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |7|Skräppost|CAT:SPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |8|Massutskick|CAT:BULK|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> De här funktionerna är bara tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.

- **Principens** prioritet: För varje skyddstyp (skydd mot skräppost, skadlig programvara, nätfiske och så vidare) finns det en standardprincip som gäller för alla, men du kan skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritetsvärde som bestämmer i vilken ordning principerna tillämpas. Standardprincipen används alltid sist.

  Om en användare har definierats i flera principer av samma typ tillämpas endast principen med högst prioritet på dem. Eventuella återstående principer av den typen utvärderas inte för användaren (inklusive standardprincipen).

Tänk på följande policyer mot nätfiske i Microsoft Defender för Office 365 som gäller för samma användare och ett meddelande som identifieras som både användarpersonifiering och förfalskning:

  ****

  |Principnamn|Prioritet|Användarpersonifiering|Förfalskningskydd|
  |---|---|---|---|
  |Princip A|1|På|Av|
  |Princip B|2|Av|På|
  |

1. Meddelandet markeras och hanteras som en förfalskning, eftersom förfalskning har högre prioritet (4) än användarpersonifiering (5).
2. Princip A används för användarna eftersom den har högre prioritet än princip B.
3. Baserat på inställningarna i princip A vidtas inga åtgärder på meddelandet, eftersom förfalskning inte är aktiverat i principen.
4. Principbearbetningen avbryts så att princip B aldrig tillämpas för användarna.

Eftersom det är möjligt att samma användare avsiktligt eller oavsiktligt ingår i flera anpassade principer av samma typ, kan du använda följande designriktlinjer för anpassade principer:

- Tilldela högre prioritet till principer som gäller för ett litet antal användare och lägre prioritet till principer som gäller för ett stort antal användare. Kom ihåg att standardprincipen alltid används sist.
- Konfigurera principer med högre prioritet så att du har striktare eller mer specialiserade inställningar än principer med lägre prioritet.
- Överväg att använda färre anpassade principer (använd bara anpassade principer för användare som behöver striktare eller mer specialiserade inställningar).
