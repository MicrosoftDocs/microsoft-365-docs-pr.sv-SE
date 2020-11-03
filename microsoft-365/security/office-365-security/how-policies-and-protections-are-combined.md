---
title: Prioritetsordning för e-postskydd
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, säkerhets Center, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om program ordningen för skydd i Exchange Online Protection (EOP) och hur prioritet svärdet i skydds principer bestämmer vilken princip som tillämpas.
ms.openlocfilehash: 9bff44a0c9964c60f5b8b5c0afdfe6d29ee6da93
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843618"
---
# <a name="order-and-precedence-of-email-protection"></a>Prioritetsordning för e-postskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan inkommande e-post flaggas med flera former av skydd. Till exempel de inbyggda skydds reglerna för EOP som är tillgängliga för alla Microsoft 365-kunder och de stabilare Antivirus principer som är tillgängliga för Microsoft Defender för Office 365-kunder. Meddelanden passerar också genom flera identifierings sökningar för skadlig program vara, spam, nätfiske etc. Allt detta kan vara en del av vilken princip som tillämpas.

I allmänhet identifieras en policy som tillämpas på ett meddelande i huvudet **X-Forefront-antispam-Report** i avsnittet **Cat (Category)** . Mer information finns i [meddelande rubriker med skräp post](anti-spam-message-headers.md).

Det finns två huvud faktorer som avgör vilken princip som tillämpas på ett meddelande:

- **Prioriteten för e-postskyddet** : den här ordningen är inte konfigurerbar och beskrivs i följande tabell:

  ****

  |Priority|E-postskydd|Kategori|Plats att hantera|
  |---|---|---|---|
  |9.1|Program|KAT: MALW|[Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md)|
  |två|Fiske|KAT: PHSH|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |amp;3D|Skräppost med hög konfidens|KAT: HSPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |9.4|Förfalskning|KAT: FALSKA IDENTITETER|[Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md)|
  |T5<sup>\*</sup>|Användarens personifiering (skyddade domäner)|UIMP|[Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |18.6<sup>\*</sup>|Domän personifiering (skyddade användare)|DIMP|[Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)|
  |borttagning|Skräppost|KAT: SPM|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |8.2|Massutskick|KAT: BULK|[Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> De här funktionerna är bara tillgängliga i policy mot nätfiske i Microsoft Defender för Office 365.

- **Prioriteten för principen** : för varje skydds typ (anti-spam, mot skadlig kod, anti-nätfiske etc.) finns det en standard princip som gäller för alla, men du kan skapa anpassade principer som gäller för specifika användare. Varje anpassad princip har ett prioritets värde som anger i vilken ordning principerna tillämpas. Standard principen tillämpas alltid sist.

  Om en användare har definierats i flera principer av samma typ tillämpas bara principen med den högsta prioriteten. Eventuella kvarvarande principer av den typen utvärderas inte för användaren (inklusive standard principen).

Du kan till exempel ta med följande anti-nätfiske-principer i Microsoft Defender för Office 365 **som gäller för samma användare** och ett meddelande som identifieras som både användar förfalskning och förfalskning:

  ****

  |Principnamn|Priority|Användar personifiering|Skydd mot förfalskning|
  |---|---|---|---|
  |Princip A|9.1|På|Av|
  |Princip B|två|Av|På|
  |

1. Meddelandet är markerat och behandlas som förfalskning eftersom förfalskning har högre prioritet (4) än User-personifiering (8).
2. Princip A tillämpas på användarna eftersom den har högre prioritet än princip B.
3. Baserat på inställningarna i princip A vidtas ingen åtgärd för meddelandet eftersom funktionen för att förhindra förfalskning är inaktive rad i principen.
4. Princip bearbetning stoppas, så policy B används aldrig för användarna.

Eftersom samma användare oavsiktligt och oavsiktligt ingår i flera anpassade principer av samma typ bör du använda följande rikt linjer för anpassade principer:

- Tilldela en högre prioritet till principer som gäller för ett fåtal användare och en lägre prioritet för principer som gäller för många användare. Kom ihåg att standard principen tillämpas alltid sist.
- Konfigurera dina högre prioriterade principer för att få striktare eller mer specialiserade inställningar än lägre prioritets principer.
- Överväg att använda färre anpassade principer (Använd endast anpassade principer för användare som kräver striktare eller fler specialiserade inställningar).
