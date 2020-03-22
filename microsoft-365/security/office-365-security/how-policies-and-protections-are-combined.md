---
title: Ordning och prioritet för e-postskydd i Office 365
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
description: Beskriver programordningen för Office 365-skydd och hur prioritetsvärdet i skyddsprinciper avgör vilken princip som tillämpas.
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895341"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Ordning och prioritet för e-postskydd i Office 365

Som Office 365-användare kan din inkommande e-post flaggas av flera former av skydd. Till exempel de inbyggda EOP-principerna mot nätfiske som är tillgängliga för alla Office 365-kunder och de mer robusta ATP-principerna för nätfiske som också är tillgängliga för Office 365 Advanced Threat Protection-kunder. Meddelanden passerar också genom flera upptäckt skanningar för skadlig kod, spam, phishing, etc. Med tanke på all denna verksamhet kan det råda viss förvirring om vilken politik som tillämpas.

I allmänhet identifieras en princip som tillämpas på ett meddelande i **X-Forefront-Antispam-Report-huvudet** i egenskapen **CAT (Category).** Mer information finns i [Rubriker för skräppostmeddelande](anti-spam-message-headers.md).

Det finns två viktiga faktorer som avgör vilken princip som tillämpas på ett meddelande:

- **Prioriteten för e-postskyddstypen**: Den här ordern kan inte konfigureras och beskrivs i följande tabell:

  |||||
  |---|---|---|---|
  |**Priority (prioritet)**|**Skydd av e-post**|**Kategori**|**Var ska man hantera**|
  |1|Malware|KATT:MALW|[Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md)|
  |2|Phishing|KATT:PHSH|[Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)|
  |3|Spam med högt förtroende|KATT:HSPM|[Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)|
  |4|Kapning|CAT:SPOOF|[Konfigurera Office 365 ATP-principer för nätfiske och nätfiske](set-up-anti-phishing-policies.md) <Br/><br/> [Läs mer om falska underrättelser](learn-about-spoof-intelligence.md)|
  |5|Spam|KATT:SPM|[Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)|
  |6|Bulk|CAT:BULK|[Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Personifiering av domän|DIMP|[Konfigurera Office 365 ATP-principer för nätfiske och nätfiske](set-up-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Personifiering av användare|UIMP (UIMP)|[Konfigurera Office 365 ATP-principer för nätfiske och nätfiske](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Dessa funktioner är endast tillgängliga i ATP.

- **Policyns prioritet:** För varje skyddstyp (anti-spam, anti-malware, anti-phishing, etc.), finns det en standardpolicy som gäller för alla, men du kan skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritetsvärde som bestämmer i vilken ordning principerna ska tillämpas i. Standardprincipen tillämpas alltid sist.

  Om en användare definieras i flera anpassade principer tillämpas endast principen med högst prioritet på dem. Återstående principer utvärderas inte för användaren (inklusive standardprincipen).

Tänk dig till exempel följande anti-phishing-principer **som gäller för samma användare**och ett meddelande som identifieras som både användarpersonifiering och förfalskning:

  |||||
  |---|---|---|---|
  |**Policy mot skräppost**|**Priority (prioritet)**|**Personifiering av användare (ATP)**|**Anti-spoofing (EOP)**|
  |Politik A|1|På|Av|
  |Politik B|2|Av|På|
  |

1. Meddelandet markeras och behandlas som parodi, eftersom förfalskning har högre prioritet (4) än användarens personifiering (8).
2. Princip A tillämpas på användarna eftersom den har högre prioritet än prioritet B.
3. Baserat på inställningarna i princip A vidtas ingen åtgärd för meddelandet, eftersom anti-förfalskning är inaktiverat i principen.
4. Behandling av anti-spam-policystopp, så policy B tillämpas aldrig på användarna.

Eftersom det finns en potential att ha många användare i många anpassade principer av samma typ bör du tänka på följande designriktlinjer för anpassade principer:

- Tilldela en högre prioritet till principer som gäller för ett litet antal användare och en lägre prioritet för principer som gäller för ett stort antal användare. Kom ihåg att standardprincipen alltid tillämpas sist.
- Konfigurera principerna med högre prioritet så att de har striktare eller mer specialiserade inställningar än principer med lägre prioritet.
- Överväg att använda färre anpassade principer (använd endast anpassade principer för användare som behöver striktare eller fler specialiserade inställningar).
