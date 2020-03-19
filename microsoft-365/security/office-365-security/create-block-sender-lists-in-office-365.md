---
title: Skapa blockeringsavsändningslistor i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Alternativ för blockavsändare inkluderar Outlook-blockerade avsändare, blockerings-/domänblocklistor mot skräppost, IP-blockeringslistor och regler för e-postflöde för Exchange (transportregler).
ms.openlocfilehash: fb5228bca7ac0c98a2aafd9d7b582e370698649a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808994"
---
# <a name="create-block-sender-lists-in-office-365"></a>Skapa blockeringsavsändningslistor i Office 365

Ibland är det nödvändigt att blockera oönskad e-post från avsändare. Det finns flera metoder att välja mellan. Dessa alternativ inkluderar Outlook-blockerade avsändare, blockerings-/domänblocklistor mot skräppost, IP-blockeringslistor och regler för e-postflöde för Exchange (kallas även transportregler).

> [!NOTE]
> Även om organisationsblocklistor kan användas för att åtgärda falska negativ (missad skräppost), bör dessa kandidater också skickas till Microsoft för analys. Om du hanterar falska negativ genom att använda blockeringslistor ökar dina administrativa kostnader avsevärt. Om du ska använda en blockeringslista för detta ändamål måste du också behålla artikeln för att skicka in meddelanden om [skräppost, icke-skräppost och nätfiske till Microsoft för analys](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), i klar ordning.

Rätt metod för att konfigurera blockerade avsändande listor varierar beroende på omfattningen av effekten. För en enskild användarpåverkan kan rätt lösning vara att använda Outlook-blockerade avsändare, men om flera användare eller alla användare påverkas skulle ett av de andra alternativen vara lämpligare.

## <a name="options-from-least-to-broadest-scope"></a>Alternativ från minst till bredaste omfattning

När du skapar en blockeringslista är det viktigt att välja lämplig metod baserat på omfattningen av effekten (hur många personer som kommer att påverkas), så att den matchar bredden på blockeringsmetoden. Alternativen nedan rangordnas efter både omfattning och bredd. Listan går från smal till bred, men *läs detaljerna* för fullständiga rekommendationer.

- Blockerade avsändare i Outlook
- Policy mot skräppost: Listor över avsändare/domänblock
- Regler för utbyta e-postflöde
- Policy mot skräppost: IP-blockeringslistor

## <a name="use-outlook-blocked-senders"></a>Använda Outlook-blockerade avsändare

När endast ett litet antal användare påverkas bör det vara då avsändare med blockerade Outlook-program ska användas, eftersom detta bara påverkar att e-post skickas till dem.

> [!IMPORTANT]
> Om oönskade meddelanden är nyhetsbrev från en ansedd och igenkännlig källa, avregistrerar sig från e-postmeddelandet är ett annat alternativ för att stoppa användaren från att få e-post i framtiden.

Stegen för att konfigurera detta skiljer sig mellan [Outlook på webben](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) och [Outlook-klienten](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **När meddelanden har blockerats på grund av blockerade avsändare ser du SFV:BLK i X-Forefront-Antispam-rapporten** som anger att meddelandet blockeras.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Använda listor över avsändare/domänblock för skräppostpolicy

När flera användare påverkas är omfattningen bredare och du måste använda en företagsomfattande avsändare/domänblocklista Anti-Spam-policy. De detaljerade stegen finns i [Konfigurera dina principer för skräppostfilter](configure-your-spam-filter-policies.md). Alla meddelanden som blockeras med den här metoden följer skräppoståtgärden som konfigurerats i principen.

Den maximala gränsen för dessa listor är cirka 1000 poster. även om du bara kan ange 30 poster i portalen. Du måste använda PowerShell för att lägga till fler än 30 poster.

## <a name="use-exchange-mail-flow-rules-specific-senders"></a>Använda Exchange-regler för e-postflödesspecifika avsändare

Om du behöver blockera meddelanden från att skickas till specifika användare eller i hela organisationen kan du använda regler för e-postflöde. Reglerna för e-postflöde är mer flexibla eftersom de kan utlösa avsändarens e-postadress eller domän samt nyckelord och andra egenskaper i meddelandet. Denna flexibilitet gör att du kan skapa partiella för att slutföra block. Mer information om regler för e-postflöde finns i [Använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Det är enkelt att skapa regler som är *alltför* aggressiva, vilket gör att det är viktigt att de kriterier som används är så specifika som möjligt. Se också till att du aktiverar granskning av regeln du skapar och gör tester för att säkerställa att allt fungerar som förväntat.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Använda IP-blockeringslistor för anti-spampolicy

När det inte är möjligt att använda något av de andra alternativen för att blockera en avsändare kan *du* använda IP-blockeringslistan mot skräppostprincip. Mer information finns i [Konfigurera anslutningsfilterprincipen](configure-the-connection-filter-policy.md). Det är viktigt att hålla antalet blockerade IP-adresser till ett minimum, så att blockera hela IP-adressintervall rekommenderas *inte.*

Du bör *särskilt* undvika att lägga till IP-adressintervall som tillhör konsumenttjänster eller delade infrastrukturer, och även se till att du granskar listan över tillåtna IP-adresser som en del av regelbundet underhåll. **Eftersom tillåt-poster kan öppna vägar för angrepp, måste du noggrant hantera den här listan och regelbundet ta bort de tillåts-poster som inte längre behövs.** Om du kommer att göra det möjligt i en säker avsändare lista se till att läsa och förstå risker och försiktighetsåtgärder i *[Skapa safe-Sender listor i Office 365](create-safe-sender-lists-in-office-365.md)*.
