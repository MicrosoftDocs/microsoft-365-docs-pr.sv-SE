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
ms.openlocfilehash: 1a68c14a2d37f1fc3bfb032c4d3ca34c09a89890
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527775"
---
# <a name="secure-by-default-in-office-365"></a>Säkra som standard i Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Säkra som standard" är en term som används för att definiera de standardinställningar som är mest säkra.

Säkerheten måste dock bal anse ras. Detta kan vara en balans mellan:

- Användbarhet: inställningarna ska inte komma i vägen för användar produktivitet.
- Risk: säkerheten kan blockera viktiga aktiviteter.
- Äldre inställningar: vissa konfigurationer för äldre produkter och funktioner kan behöva bevaras av företags skäl, även om nya, moderna inställningar förbättras.

Microsoft 365-organisationer med post lådor i Exchange Online skyddas av Exchange Online Protection (EOP). Detta skydd inkluderar:

1. E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande. Se [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).
1. Nät fiske meddelande som identifieras som "hög exakthet" hanteras i enlighet med åtgärd för att förhindra skräp post. Se [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

Eftersom Microsoft vill hålla våra kunder säkra som standard, tillämpas vissa klient organisationer inte på skadlig program vara eller nätfiske med hög exakthet. Dessa åsidosättningar inkluderar:

- Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)
- Säkra avsändare i Outlook
- Lista över tillåtna IP-adresser (anslutnings filter)

Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md).

Alternativet säker som standard är inte en inställning som kan aktive ras eller avaktiveras, men det är så att vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor. Malware och högkonfidens nätfiske bör skickas till karantänen. Endast administratörer kan hantera meddelanden som satts i karantän som skadlig eller högsäker nätfiske och de kan också rapportera falska positiva positiv till Microsoft därifrån. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Undanta

Den enda åsidosättning som möjliggör högsäker nät fiske meddelande för att kringgå filtrering är regler för Exchange-flöden (kallas även transport regler). Om du vill använda regler för e-postflöde för att kringgå filtrering läser du [använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Åsidosättningar ska endast användas för:

- Nät fiske simulering: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt). Teams kan sedan granska för att se om de innehåller skadligt innehåll.
- Filter från tredje part: vissa tredjepartsleverantörer rekommenderar att du inaktiverar EOP (SCL =-1) när filtret för tredje part hanterar e-postfiltreringen. Microsoft rekommenderar inte att du inaktiverar EOP eftersom EOP krävs för Defender för Office 365. I stället är rekommendationen att aktivera [utökad filtrering för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) i stället.
- Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md). Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.
