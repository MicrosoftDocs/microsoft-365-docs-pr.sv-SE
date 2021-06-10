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
description: Lär dig mer om hur EOP och Office 365 skyddar dig med skydd mot skräppost, nätfiske och skadlig kod genom att lägga till en e-säkerhetstips överst i e-postmeddelanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994991"
---
# <a name="safety-tips-in-email-messages"></a>Säkerhetstips i e-postmeddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) och Microsoft 365 skydda dig mot skräppost, nätfiske och skadlig kod. Vissa av dessa attacker är i dag så väl utformade att de ser legitima ut. Att skicka meddelanden till mappen Skräppost räcker inte alltid. När du kontrollerar din e-post i Outlook eller Outlook på webben eller någon annan e-postklient kontrollerar EOP automatiskt avsändaren och lägger till en säkerhetstips överst i e-postmeddelandet.

Säkerhetstips i Outlook beror inte på vilken version av Outlook du använder eftersom säkerhetstips är sprucken öppen och infogad direkt i meddelandets brödtext. Det innebär att säkerhetstips visas i den e-postklient som du använder. Det görs på e-postfilternivå och återges inte på e-postklientnivå, så det visas inte bara i någon version av Outlook, det visas också på alla e-postklienter.

Den säkerhetstips –ett färgkodat meddelande – varnar om eventuellt skadliga meddelanden. De flesta meddelanden i inkorgen har inte någon säkerhetstips. Du kan bara se dem när EOP och Microsoft 365 har information som du behöver för att förhindra attacker i skräppost, nätfiske och skadlig kod. Om säkerhetstips visas i Inkorgen kan du använda följande exempel för att lära dig mer om varje typ av säkerhetstips.

- Misstänkt e-postmeddelande (säkerhetstips).

    ![Skärmbild som visar en röd säkerhetstips.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    En röd säkerhetstips i ett e-postmeddelande innebär att meddelandet du har fått innehåller något misstänkt, till exempel ett försök till nätfiske. Vi rekommenderar att du tar bort den här typen av e-postmeddelanden från Inkorgen utan att öppna dem.

- Valv e-post (grön säkerhetstips).

    ![Skärmbild som visar en grön säkerhetstips.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Vi kommer även att berätta om giltiga meddelanden från betrodda avsändare, förutom osäkra meddelanden, med en grön säkerhetstips. En grön säkerhetstips i ett e-postmeddelande innebär att vi kontrollerat avsändaren till meddelandet och verifierat att det är säkert. Microsoft har en lista över betrodda avsändare som bland annat omfattar finansiella företag och andra som bedragare ofta kapar eller utger sig för att vara.

## <a name="working-with-safety-tips"></a>Arbeta med säkerhetstips

Administratörer kan aktivera eller inaktivera säkerhetstips i principer mot skräppost. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

Om du inte tycker att EOP har kategoriserat ett meddelande (det vill säga om meddelandet inte är skräppost eller om det borde ha markerats som skräppost) kan du skicka meddelandena till Microsoft för analys för att förbättra upplevelsen. Anvisningar finns i [Artikeln om att rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md) Du kan också klicka på länken Feedback i länken säkerhetstips skicka kommentarer direkt till Microsoft för att hjälpa oss att förbättra.
