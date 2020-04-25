---
title: Säkerhetstips i e-postmeddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/6/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Introducerar säkerhetstips för e-postmeddelanden som filtrerats av EOP och skräppostfiltret.
ms.openlocfilehash: c7d7e6819e1374fd941d6eeb992ecf63726d4127
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809020"
---
# <a name="safety-tips-in-email-messages"></a>Säkerhetstips i e-postmeddelanden

Exchange Online Protection (EOP) och Microsoft 365 skyddar dig med skräppost, nätfiske och förebyggande av skadlig kod. Idag är några av dessa attacker så välutformad att de ser legitima. Det räcker inte alltid att skicka meddelanden till mappen Skräppost. Nu, när du kontrollerar din e-post i Outlook eller Outlook på webben eller någon e-postklient, EOP automatiskt kontrollerar avsändaren och lägger till ett säkerhetstips till toppen av e-postmeddelandet.

Säkerhetstips i Outlook beror inte på vilken version av Outlook du använder eftersom säkerhetstipset är sprucket öppet och infogat direkt i meddelandetexten. Detta innebär att säkerhetstipset kommer att dyka upp i vilken e-postklient du använder. Det görs på e-filternivå och inte återges på e-postklientnivå, så det visas inte bara i någon version av Outlook, det dyker också upp i någon e-postklient.

Säkerhetstipset – ett färgkodat meddelande – varnar dig om potentiellt skadliga meddelanden. De flesta meddelanden i inkorgen har inget säkerhetstips. Du ser dem bara när EOP och Microsoft 365 har information som du behöver för att förhindra attacker mot skräppost, nätfiske och skadlig programvara. Om säkerhetstips visas i inkorgen kan du använda följande exempel för att lära dig mer om varje typ av säkerhetstips.

- Misstänkt post (röd säkerhetsspets).

    ![Skärmdump som visar ett rött säkerhetstips.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Ett rött säkerhetstips i ett e-postmeddelande innebär att meddelandet du fick innehåller något misstänkt, till exempel ett nätfiskebedrägeri. Vi rekommenderar att du tar bort den här typen av e-postmeddelanden från inkorgen utan att öppna det.

- Spam (gul säkerhetsspets).

    ![Skärmdump som visar en gul säkerhetsspets.](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    Ett gult säkerhetstips i ett e-postmeddelande innebär att meddelandet har markerats som skräppost. Om du inte känner igen och litar på meddelandets avsändare ska du inte hämta några bifogade filer eller bilder och klicka inte på några länkar i meddelandet. I Outlook på webben kan du klicka på **Det är inte skräppost** i det gula fältet i ett skräppostobjekt för att flytta meddelandet till inkorgen. Om det gula säkerhetstipset visas i ett meddelande som levererades till inkorgen finns det förmodligen där eftersom du har inaktiverat att flytta skräppost till mappen Skräppost.

- Säker post (grön säkerhetsspets).

    ![Skärmdump som visar ett grönt säkerhetstips.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Förutom osäkra meddelanden får vi även berätta om giltiga meddelanden från avsändare som vi litar på med ett grönt säkerhetstips. Ett grönt säkerhetstips i ett e-postmeddelande innebär att vi har kontrollerat meddelandets avsändare och verifierat att det är säkert. Microsoft har den här listan över betrodda avsändare som innehåller ekonomiska organisationer och andra som ofta förfalskas eller personifieras.

- Ofiltrerad post (grå säkerhetsspets).

    ![Skärmbild som visar ett grått säkerhetstips.](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    Vi berättar också när vi hoppade över att kontrollera ett e-postmeddelande eftersom det är från en avsändare som du litar på på listan Betrodda avsändare eller om det finns en regel för e-postflöde för att kringgå filtrering.

    Den grå säkerhetstipset visas också när externa bilder blockeras, det vill säga meddelandet finns i inkorgen och verkar inte vara skräppost, men innehåller externa bilder som du inte har valt att ladda ned.
    

## <a name="working-with-safety-tips"></a>Arbeta med säkerhetstips

Säkerhetstips är alltid aktiverade för Outlook på webben, även om inte alla meddelanden kommer att få ett. Administratörer kan inaktivera säkerhetstips för andra e-postklienter som Outlook. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

Om du inte håller med om hur EOP kategoriserade ett meddelande (det vill säga meddelandet är inte skräppost eller om det borde ha markerats som skräppost) kan du skicka meddelandena till Microsoft för analys för att göra din upplevelse bättre. Instruktioner finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md). Du kan också klicka på länken Feedback i säkerhetstipset för att skicka kommentarer direkt till Microsoft för att hjälpa oss att förbättra.
