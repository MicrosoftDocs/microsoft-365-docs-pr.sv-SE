---
title: Konfidensnivå för skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om nivån för skräppostförtroende (SCL) som gäller för meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05faec8101bfb13265d3cca7c661f2e86ac21c8d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290411"
---
# <a name="spam-confidence-level-scl-in-eop"></a>SCL (Spam Confidence Level) i EOP

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tilldelas inkommande meddelanden skräppostfiltrering i EOP och tilldelas ett skräppostresultat. Poängen mappas till en enskild nivå för skräppostförtroende (SCL) som läggs till i meddelandet i ett X-sidhuvud. En högre SCL anger att ett meddelande är mer troligt att det är skräppost. EOP vidtar åtgärder för meddelandet baserat på SCL.

Vad SCL innebär och standardåtgärderna som vidtas på meddelanden beskrivs i följande tabell. Mer information om åtgärder du kan vidta på meddelanden baserat på skräppostfiltreringens bedömning finns i Konfigurera principer för skydd mot [skräppost i EOP.](configure-your-spam-filter-policies.md)

****

|SCL|Definition|Standardåtgärd|
|:---:|---|---|
|-1|Meddelandet hoppade över skräppostfiltrering. Meddelandet kommer till exempel från en betrodd avsändare, skickades till en betrodd mottagare eller kommer från en e-postkälla på listan över tillåtna IP-adresser. Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)|Skicka meddelandet till mottagarnas inkorg.|
|0, 1|Skräppostfiltreringen gjorde att meddelandet inte var skräppost.|Skicka meddelandet till mottagarnas inkorg.|
|5, 6|Skräppostfiltrering har markerat meddelandet som **skräppost**|Leverera meddelandet till mottagarnas skräppostmapp.|
|9|Skräppostfiltrering markerade meddelandet som **skräppost med hög konfidens**|Leverera meddelandet till mottagarnas skräppostmapp.|
|

Du kommer att märka att SCL 2, 3, 4, 7 och 8 inte används av skräppostfiltrering.

Du kan använda e-postflödesregler (kallas även transportregler) för att stämpla SCL på meddelanden. Om du använder en e-postflödesregel för att ange SCL utlöser värdena 5 eller 6 skräppostfiltreringen för skräppost, och värdena 7, 8 eller 9 utlöser skräppostfiltreringsåtgärden för skräppost med hög konfidens.  Mer information finns i Använda [e-postflödesregler för att ange](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)nivån för skräppostförtroende (SCL) i meddelanden.

På liknande sätt som SCL identifierar gruppklagomålsnivån (BCL) felaktig massutskick (kallas även _grå_ post). En högre BCL anger att ett Mass utskick innebär att det är mer troligt att vi skapar klagomål (och är därför förmodligen mer sannolikt att få skräp post). Du konfigurerar BCL-tröskelvärdet i principer för skydd mot skräppost. Mer information finns i Konfigurera principer för skräppostskydd i [EOP,](configure-your-spam-filter-policies.md)Nivå för gruppklagomål [(BCL)](bulk-complaint-level-values.md)i EOP och Vad är skillnaden mellan skräppost och [massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![Den korta ikonen för LinkedIn ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Learning, ny för Microsoft 365?** Upptäck kostnadsfria videokurser **för Microsoft 365-administratörer och IT-proffs** från LinkedIn Learning.
