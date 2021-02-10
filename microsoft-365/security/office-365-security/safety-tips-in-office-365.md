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
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur EOP och Office 365 skyddar dig med skydd mot skräppost, nätfiske och skadlig kod genom att lägga till säkerhetstips överst i e-postmeddelanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c37eba07b306ff47e14640e494e468b63b358726
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166621"
---
# <a name="safety-tips-in-email-messages"></a>Säkerhetstips i e-postmeddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online Protection (EOP) och Microsoft 365 skyddar dig med skydd mot skräppost, nätfiske och skadlig kod. Vissa av dessa attacker är i dag så väl utformade att de ser legitima ut. Det räcker inte alltid att skicka meddelanden till mappen Skräppost. När du kontrollerar din e-post i Outlook eller Outlook på webben eller någon annan e-postklient kontrollerar EOP nu automatiskt avsändaren och lägger till ett säkerhetstips högst upp i e-postmeddelandet.

Säkerhetstips i Outlook beror inte på vilken version av Outlook du använder eftersom säkerhetstipset är sprucket och infogade direkt i meddelandets brödtext. Det innebär att säkerhetstipset visas i den e-postklient du använder. Det görs på e-postfilternivån och återges inte på e-postklientnivån, så det visas inte bara i någon version av Outlook, det visas också i alla e-postklienter.

Säkerhetstipset är ett färgkodat varningsmeddelande om eventuellt skadliga meddelanden. De flesta meddelanden i Inkorgen har inte något säkerhetstips. Du kan bara se dem när EOP och Microsoft 365 har information som du behöver för att förhindra attacker i skräppost, nätfiske och skadlig kod. Om det dyker upp säkerhetstips i Inkorgen kan du använda följande exempel för att lära dig mer om de olika säkerhetstipsen.

- Misstänkt e-postmeddelande (rött säkerhetstips).

    ![Skärmbild som visar ett rött säkerhetstips.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Ett rött säkerhetstips i ett e-postmeddelande innebär att meddelandet som du har fått innehåller något misstänkt, till exempel ett försök till nätfiske. Vi rekommenderar att du tar bort den här typen av e-postmeddelanden från Inkorgen utan att öppna dem.

- Säker e-post (grönt säkerhetstips).

    ![Skärmbild som visar ett grönt säkerhetstips.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Förutom osäkra meddelanden kommer vi också att berätta om giltiga meddelanden från betrodda avsändare med ett grönt säkerhetstips. Ett grönt säkerhetstips i ett e-postmeddelande innebär att vi kontrollerat avsändaren till meddelandet och verifierat att det är säkert. Microsoft har en lista över betrodda avsändare som bland annat omfattar finansiella företag och andra som ofta kapas eller utger sig för att vara.

## <a name="working-with-safety-tips"></a>Arbeta med säkerhetstips

Säkerhetstips är alltid aktiverade för Outlook på webben, även om inte alla meddelanden får något. Administratörer kan inaktivera säkerhetstips för andra e-postklienter, till exempel Outlook. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

Om du inte håller med om hur EOP kategoriserat ett meddelande (det vill säga om meddelandet inte är skräppost eller om det borde ha markerats som skräppost) kan du skicka meddelandena till Microsoft för analys för att förbättra din upplevelse. Instruktioner finns i Rapportera [meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md) Du kan också klicka på länken Feedback i säkerhetstipset och skicka kommentarer direkt till Microsoft för att hjälpa oss att bli bättre.
