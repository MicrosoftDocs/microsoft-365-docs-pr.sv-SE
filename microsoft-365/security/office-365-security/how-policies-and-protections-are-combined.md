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
description: Administratörer kan lära sig mer om tillämpningsordningen för skydd i Exchange Online Protection (EOP) och hur prioritetsvärdet i skyddsprinciper avgör vilken princip som tillämpas.
ms.openlocfilehash: 176d39a240d49e0118b4bb8e8cee52a6e7c61b0e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209445"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordning och prioritet för e-postskydd

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan inkommande e-post flaggas av flera former av skydd. Till exempel de inbyggda EOP-principerna mot nätfiske som är tillgängliga för alla Microsoft 365-kunder och de mer robusta ATP-principerna för nätfiske som också är tillgängliga för Office 365 Advanced Threat Protection (Office 365 ATP) kunder. Meddelanden passerar också genom flera upptäckt skanningar för skadlig kod, spam, phishing, etc. Med tanke på all denna verksamhet kan det råda viss förvirring om vilken politik som tillämpas.

I allmänhet identifieras en princip som tillämpas på ett meddelande i **X-Forefront-Antispam-Report-huvudet** i egenskapen **CAT (Category).** Mer information finns i [Rubriker för skräppostmeddelande](anti-spam-message-headers.md).

Det finns två viktiga faktorer som avgör vilken princip som tillämpas på ett meddelande:

- **Prioriteten för e-postskyddstypen**: Den här ordern kan inte konfigureras och beskrivs i följande tabell:

  |||||
  |---|---|---|---|
  |**Prioritet**|**Skydd av e-post**|**Kategori**|**Var ska man hantera**|
  |1|Malware|KATT:MALW|[Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md)|
  |2|Phishing|KATT:PHSH|[Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md)|
  |3|Skräppost med hög konfidens|KATT:HSPM|[Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md)|
  |4|Kapning|CAT:SPOOF|[Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md)|
  |5|Skräppost|KATT:SPM|[Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md)|
  |6|Bulk (Massutskick)|CAT:BULK|[Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Domänpersonifiering (skyddade användare)|DIMP|[Konfigurera principer för ATP-skydd mot nätfiske](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Användaren personifiering (skyddade domäner)|UIMP (UIMP)|[Konfigurera principer för ATP-skydd mot nätfiske](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Dessa funktioner är endast tillgängliga i ATP:s principer för nätfiske.

- **Policyns prioritet:** För varje skyddstyp (anti-spam, anti-malware, anti-phishing, etc.), finns det en standardpolicy som gäller för alla, men du kan skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritetsvärde som bestämmer i vilken ordning principerna ska tillämpas i. Standardprincipen tillämpas alltid sist.

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
