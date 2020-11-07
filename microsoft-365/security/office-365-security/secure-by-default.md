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
description: Lär dig hur du hittar och använder e-postsäkerhets rapporter för organisationen. Säkerhets rapporter för e-post finns i säkerhets & Compliance Center.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944543"
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
1. E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande. Se [Konfigurera principer för skydd mot skadlig program vara i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).
1. Nät fiske meddelande som identifieras som "hög exakthet" hanteras i enlighet med åtgärd för att förhindra skräp post. Se [Konfigurera principer för skräp post i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).

Eftersom Microsoft vill hålla våra kunder säkra som standard, används vissa klient organisationer inte för skadlig program vara eller Phish. Dessa åsidosättningar inkluderar:
- Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)
- Säkra avsändare i Outlook
- Lista över tillåtna IP-adresser (anslutnings filter)

Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Alternativet säker som standard är inte en inställning som kan aktive ras eller avaktiveras, men det är så att vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor. Skadlig program vara och Phish med hög exakthet bör skickas till karantän. Endast administratörer kan hantera meddelanden som satts i karantän som skadlig eller högsäker nätfiske och de kan också rapportera falska positiva positiv till Microsoft därifrån. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Undanta
De enda åsidosättningar som kommer att kringgå alla filter är:
- Regler för Exchange-Exchange (/mail).  Använd regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden i EOP.
- Tillåt/blockera i klient organisation: hantera URL-adresser och filer i listan Tillåt/blockera för klient organisation.


Dessa typer av åsidosättningar är användbara för:
- Phish simuleringar: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt). Teams kan sedan granska för att se om de innehåller skadligt innehåll.
- Filter från tredje part: vissa leverantörer av tredje part rekommenderar att du inaktiverar EOP (SCL =-1) när filtret för tredje part hanterar e-postfiltreringen.  Microsoft rekommenderar inte att du inaktiverar EOP eftersom EOP krävs för Defender för Office 365. 
- Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md). Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.
