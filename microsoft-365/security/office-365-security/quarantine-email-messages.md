---
title: E-postmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om karantän i Exchange Online Protection (EOP) som innehåller potentiellt farliga eller oönskade meddelanden.
ms.openlocfilehash: f4e3f668ac94abfea6dc19f6f256141b2a7b9915
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616038"
---
# <a name="quarantined-email-messages-in-eop"></a>E-postmeddelanden i karantän i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor är det möjligt att hålla farliga eller oönskade meddelanden.

Principer mot skadlig program vara automatiskt karantän ett meddelande *om en* bifogad fil hittas för att innehålla skadlig kod. Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).

Som standard bevarar antivirus program nät fiske meddelanden och skickar skräp post och Mass utskick via e-post till användarens mapp för skräp post. Men du kan också skapa och anpassa principer för skräp post till skräp post och Mass utskick via e-post. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Både användare och administratörer kan arbeta med meddelanden i karantän:

- Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare. Endast administratörer kan arbeta med meddelanden som satts i karantän som skadlig program vara, högsäker nät fiske eller resultat av regler för e-postflöde (kallas även transport regler). Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

- Användarna kan arbeta med meddelanden i karantän när de är en mottagare om meddelandet sattes i karantän som skräp post, Mass utskick eller (från april 2020) nätfiske. Mer information finns i [hitta och släppa meddelanden i karantän som en användare i EOP](find-and-release-quarantined-messages-as-a-user.md).

  Administratörer kan konfigurera en annan åtgärd för Verdict för att förhindra att användare hanterar sina egna **nät fiske meddelanden** . Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

- Administratörer och användare kan rapportera falska positiva positiv till Microsoft i karantän.

Mer information om karantän finns i [vanliga frågor om karantän](quarantine-faq.md).
