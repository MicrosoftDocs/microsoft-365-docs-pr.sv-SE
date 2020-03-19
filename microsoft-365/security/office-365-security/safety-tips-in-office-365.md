---
title: Säkerhetstips i e-postmeddelanden i Office 365
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
description: Introducerar säkerhetstips för e-postmeddelanden som filtrerats av skräppostfiltret EOP och Office 365.
ms.openlocfilehash: 1fddb38be711a9d43e85adea34fe14eb9e7a85ef
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810056"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a>Säkerhetstips i e-postmeddelanden i Office 365

Exchange Online Protection (EOP) och Office 365 skyddar dig med skräppost, nätfiske och förebyggande av skadlig kod. Idag är några av dessa attacker så välutformade att de ser legitima ut. Det räcker inte alltid att skicka meddelanden till mappen Skräppost. Nu, när du kontrollerar din e-post i Outlook eller Outlook på webben, kontrollerar EOP automatiskt avsändaren och lägger till ett säkerhetstips högst upp i e-postmeddelandet.

Säkerhetstipset – ett färgkodat meddelande – varnar dig för potentiellt skadliga meddelanden. De flesta meddelanden i inkorgen har inget säkerhetstips. Du ser dem bara när EOP och Office 365 har information som du behöver för att förhindra skräppost, nätfiske och malware-attacker. Om säkerhetstips visas i inkorgen kan du använda följande exempel för att lära dig mer om varje typ av säkerhetstips.

- Misstänkt post (röd säkerhetstips).

    ![Skärmbild som visar ett rött säkerhetstips.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Ett rött säkerhetstips i ett e-postmeddelande innebär att meddelandet du fick innehåller något misstänkt, till exempel ett nätfiskebedrägeri. Vi rekommenderar att du tar bort den här typen av e-postmeddelande från inkorgen utan att öppna det.

- Spam (gul säkerhetsspets).

    ![Skärmbild som visar ett gult säkerhetstips.](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    Ett gult säkerhetstips i ett e-postmeddelande innebär att meddelandet har markerats som skräppost. Om du inte känner igen och litar på meddelandets avsändare ska du inte hämta några bilagor eller bilder och klicka inte på några länkar i meddelandet. I Outlook på webben kan du klicka på **Det är inte skräppost** i det gula fältet i ett skräppostobjekt för att flytta meddelandet till inkorgen. Om det gula säkerhetstipset visas på ett meddelande som levererades till inkorgen finns det förmodligen där eftersom du har inaktiverat att flytta skräppost till mappen Skräppost.

- Säker post (grön säkerhetstips).

    ![Skärmbild som visar ett grönt säkerhetstips.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Förutom osäkra meddelanden berättar vi även om giltiga meddelanden från avsändare som vi litar på med ett grönt säkerhetstips. Ett grönt säkerhetstips i ett e-postmeddelande innebär att vi har kontrollerat meddelandets avsändare och verifierat att det är säkert. Microsoft underhåller den här listan över betrodda avsändare som innehåller ekonomiska organisationer och andra som ofta förfalskas eller personifieras.

- Ofiltrerad e-post (grå säkerhetstips).

    ![Skärmbild som visar ett grått säkerhetstips.](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    Vi berättar också när vi hoppade över att kontrollera ett e-postmeddelande eftersom det kommer från en avsändare som du litar på i listan Betrodda avsändare eller om det finns en e-postflödesregel för att kringgå filtreringen.

    Den grå säkerhetstipset visas också när externa bilder blockeras, det vill säga meddelandet finns i inkorgen och verkar inte vara skräppost, men innehåller externa bilder som du inte har valt att hämta.

## <a name="working-with-safety-tips"></a>Arbeta med säkerhetstips

Säkerhetstips är alltid aktiverade för Outlook på webben, även om inte alla meddelanden kommer att få ett. Office 365-administratörer kan inaktivera säkerhetstips för andra e-postklienter, till exempel Outlook. Mer information finns i [Aktivera eller inaktivera säkerhetstips i Office 365](enable-or-disable-safety-tips.md).

Om du inte håller med om hur Office 365 och EOP kategoriserade ett meddelande (det vill säga det är inte skräppost eller inte legitimt) kan du skicka meddelanden för analys för att göra din upplevelse bättre. Mer information finns i [Rapportera skräppost och nätfiskebedrägerier i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Du kan också klicka på länken Feedback i säkerhetstipset för att skicka kommentarer direkt till Microsoft för att hjälpa oss att förbättra.

## <a name="see-also"></a>Se även

[Aktivera eller inaktivera säkerhetstips i Office 365](enable-or-disable-safety-tips.md)

