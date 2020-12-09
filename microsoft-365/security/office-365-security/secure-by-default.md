---
title: Säkra som standard i Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Lär dig mer om inställningen säker med standardinställningen i Exchange Online Protection (EOP)
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602047"
---
# <a name="secure-by-default-in-office-365"></a>Säkra som standard i Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Säkra som standard" är en term som används för att definiera de standardinställningar som är mest säkra.

Säkerheten måste dock bal anse ras. Detta kan vara en balans mellan:

- **Användbarhet**: inställningarna ska inte komma i vägen för användar produktivitet.
- **Risk**: säkerheten kan blockera viktiga aktiviteter.
- **Äldre inställningar**: vissa konfigurationer för äldre produkter och funktioner kan behöva bevaras av företags skäl, även om nya, moderna inställningar förbättras.

Microsoft 365-organisationer med post lådor i Exchange Online skyddas av Exchange Online Protection (EOP). Detta skydd inkluderar:

- E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande. Se [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).
- E-postmeddelanden som identifieras som ett högkonfidens nät fiske hanteras enligt policyn för skydd mot skräp post. Se [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

Mer information om EOP finns i [Översikt över Exchange Online-skydd](exchange-online-protection-overview.md).

Eftersom Microsoft vill hålla våra kunder säkra som standard, tillämpas vissa klient organisationer inte på skadlig program vara eller nätfiske med hög exakthet. Dessa åsidosättningar inkluderar:

- Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)
- Säkra avsändare i Outlook
- Lista över tillåtna IP-adresser (anslutnings filter)

Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md).

Säkra som standard är inte en inställning som kan sättas på eller av, men är det sätt på vilket vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor. Nätfiske och högsäker nät fiske meddelanden bör vara i karantän. Endast administratörer kan hantera meddelanden som är i karantän som skadlig eller högkonfidens nätfiske, och de kan också rapportera falska positiva positiv till Microsoft. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Mer om varför vi gör detta

Den anda som är säker som standard är: Vi utför samma åtgärd på meddelandet som du skulle vidta om du kände till att meddelandet är skadligt, även om det var något möjligt. Det här är samma metod som vi har använt på skadlig program vara och nu utökas samma sak med högsäker nät fiske meddelanden. I våra data anges att den felaktiga positiva taxan för nät fiske samtal är väldigt svag och administratörer kan lösa eventuella falska positiva godkännanden med administratörs inlämningar. I våra data anges också att listan Tillåtna avsändare och tillåtna domän listor i principer för skräp post och betrodda avsändare i Outlook var för omfattande och vållar mindre skada.

Så här lägger du till det på ett annat sätt: som en säkerhets tjänst, agerar vi för din räkning för att förhindra att användarna angrips. Dessutom är säkra som standard inte ett fullständigt övertag ande av dina tillgängliga alternativ för nät fiske meddelanden med skydd mot skräp post. Även om vi rekommenderar karantän är de andra åtgärderna som alltid är tillgängliga fortfarande tillgängliga (flytta till mappen skräp post eller omdirigera till en e-postadress).

## <a name="exceptions"></a>Undanta

Den enda åsidosättning som möjliggör högsäker nät fiske meddelande för att kringgå filtrering är regler för Exchange-flöden (kallas även transport regler). Om du vill använda regler för e-postflöde för att kringgå filtrering läser du [använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Du bör bara använda åsidosättningar i följande fall:

- Nät fiske simulering: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt). Teams kan sedan granska för att se om de innehåller skadligt innehåll.
- Filter från tredje part: vissa tredjepartsleverantörer rekommenderar att du inaktiverar EOP (SCL =-1) när filtret för tredje part hanterar e-postfiltreringen. Microsoft rekommenderar inte att du inaktiverar EOP eftersom EOP krävs för [Microsoft Defender för Office 365](office-365-atp.md). I stället är rekommendationen att aktivera [utökad filtrering för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md). Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.
