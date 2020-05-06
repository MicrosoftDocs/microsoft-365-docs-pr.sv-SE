---
title: Ordning och prioritet för e-postskydd
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer om programordningen för Office 365-skydd och hur prioritetsvärdet i skyddsprinciper avgör vilken princip som tillämpas.
ms.openlocfilehash: 856b3bc39cd971e605cd9f1c0f31554a853c1b67
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036722"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordning och prioritet för e-postskydd

Som Microsoft 365-användare kan din inkommande e-post flaggas av flera former av skydd. Till exempel de inbyggda EOP-principerna mot nätfiske som är tillgängliga för alla Microsoft 365-kunder och de mer robusta ATP-principerna för nätfiske som också är tillgängliga för Office 365 Advanced Threat Protection-kunder. Meddelanden passerar också genom flera upptäckt skanningar för skadlig kod, spam, phishing, etc. Med tanke på all denna verksamhet kan det råda viss förvirring om vilken politik som tillämpas.

I allmänhet identifieras en princip som tillämpas på ett meddelande i **X-Forefront-Antispam-Report-huvudet** i egenskapen **CAT (Category).** Mer information finns i [Rubriker för skräppostmeddelande](anti-spam-message-headers.md).

Det finns två viktiga faktorer som avgör vilken princip som tillämpas på ett meddelande:

- **Prioriteten för e-postskyddstypen**: Den här ordern kan inte konfigureras och beskrivs i följande tabell:

  |||||
  |---|---|---|---|
  |**Prioritet**|**Skydd av e-post**|**Kategori**|**Var ska man hantera**|
  |1|Malware|KATT:MALW|[Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md)|
  |2|Phishing|KATT:PHSH|[Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md)|
  |3|Skräppost med hög konfidens|KATT:HSPM|[Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md)|
  |4|Kapning|CAT:SPOOF|[Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md)|
  |5|Skräppost|KATT:SPM|[Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md)|
  |6|Bulk (Massutskick)|CAT:BULK|[Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Domänpersonifiering (skyddade användare)|DIMP|[Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Användaren personifiering (skyddade domäner)|UIMP (UIMP)|[Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Dessa funktioner är endast tillgängliga i ATP:s principer för nätfiske.

- **Policyns prioritet:** För varje skyddstyp (anti-spam, anti-malware, anti-phishing, etc.), finns det en standardpolicy som gäller för alla, men du kan ofta skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritetsvärde som bestämmer i vilken ordning principerna ska tillämpas i. Standardprincipen tillämpas alltid sist.

  Om en användare definieras i flera principer av samma typ tillämpas endast principen med högsta prioritet på dem. Återstående principer av den typen utvärderas inte för användaren (inklusive standardprincipen).

Tänk dig till exempel följande ATP-principer för nätfiske **som gäller för samma användare**och ett meddelande som identifieras som både användarpersonifiering och förfalskning:

  |||||
  |---|---|---|---|
  |**ATP:s policy för phishing-phishing**|**Prioritet**|**Användarens personifiering**|**Anti-spoofing**|
  |Politik A|1|På|Av|
  |Politik B|2|Av|På|
  |

1. Meddelandet markeras och behandlas som parodi, eftersom förfalskning har högre prioritet (4) än användarens personifiering (8).
2. Princip A tillämpas på användarna eftersom den har högre prioritet än princip B.
3. Baserat på inställningarna i princip A vidtas ingen åtgärd för meddelandet, eftersom anti-förfalskning är inaktiverat i principen.
4. Principbearbetningen stoppas, så princip B tillämpas aldrig på användarna.

Eftersom samma användare avsiktligt eller oavsiktligt ingår i flera anpassade principer av samma typ använder du följande designriktlinjer för anpassade principer:

- Tilldela en högre prioritet till principer som gäller för ett litet antal användare och en lägre prioritet för principer som gäller för ett stort antal användare. Kom ihåg att standardprincipen alltid tillämpas sist.
- Konfigurera principerna med högre prioritet så att de har striktare eller mer specialiserade inställningar än principer med lägre prioritet.
- Överväg att använda färre anpassade principer (använd endast anpassade principer för användare som behöver striktare eller mer specialiserade inställningar).
