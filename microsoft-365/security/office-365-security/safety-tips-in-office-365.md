---
title: Säkerhetstips i e-postmeddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur EOP och Office 365 skyddar dig mot skräp post, nätfiske och dataexekveringsskydd genom att lägga till ett säkerhets tips längst upp i e-postmeddelandena.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e204021bfd79dabd4abdeefaa990da50915eaf0
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948463"
---
# <a name="safety-tips-in-email-messages"></a>Säkerhetstips i e-postmeddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) och Microsoft 365 skyddar dig mot skräp post, nätfiske och skadlig program vara. I dag är vissa av dessa attacker så väl utformade att de ser äkta ut. Det räcker inte med att skicka meddelanden till mappen skräp post. När du sedan checkar in din e-post i Outlook eller Outlook på webben eller en e-postklient kontrollerar EOP automatiskt avsändaren och lägger till ett säkerhets tips längst upp i e-postmeddelandet.

Säkerhets tips i Outlook är inte beroende av vilken version av Outlook du använder eftersom säkerhets tipset är knäckt och infogat direkt i meddelande texten. Det innebär att säkerhets tipset visas i den e-postklient som du använder. Den är klar på e-postfilter nivån och återges inte på e-postklientnivå, så den visas också i alla e-postklienter.

Säkerhets tipset – ett färgkodat meddelande – varnar dig om potentiellt skadliga meddelanden. De flesta meddelanden i Inkorgen har ingen säkerhets tips. Du kan bara se dem när EOP och Microsoft 365 har information som du behöver för att förhindra skräp post, nätfiske och skadlig program vara. Om säkerhets tips visas i Inkorgen kan du använda följande exempel för att lära dig mer om olika typer av säkerhets tips.

- Misstänkt e-post (rött säkerhets tips).

    ![Skärm bild som visar ett rött säkerhets tips.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Ett rött säkerhets tips i ett e-postmeddelande betyder att meddelandet du fick innehåller något misstänkt, till exempel ett phishing-bedrägeri. Vi rekommenderar att du tar bort e-postmeddelandet från inkorgen utan att öppna det.

- Säker e-post (grönt säkerhets tips).

    ![Skärm bild som visar ett grönt säkerhets tips.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Förutom osäkra meddelanden berättar vi också om giltiga meddelanden från avsändare som vi litar på med ett grönt säkerhets tips. Ett grönt säkerhets tips i ett e-postmeddelande innebär att vi kontrollerade avsändaren av meddelandet och kontrollerat att det är säkert. Microsoft bevarar den här listan över betrodda avsändare som innehåller ekonomiska organisationer och andra som ofta är falska eller personifierade.

## <a name="working-with-safety-tips"></a>Arbeta med säkerhets tips

Säkerhets tips är alltid aktiverade för Outlook på webben, även om inte alla meddelanden kommer att ta emot något. Administratörer kan stänga av säkerhets tips för andra e-postklienter, till exempel Outlook. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

Om du inte samtycker till hur EOP kategoriserade ett meddelande (det vill säga att meddelandet inte är skräp post eller om det har marker ATS som skräp post) kan du skicka meddelanden till Microsoft för analys för att förbättra upplevelsen. Anvisningar finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md). Du kan också klicka på länken feedback i säkerhets tipset och skicka kommentarer direkt till Microsoft för att hjälpa oss att förbättra.
