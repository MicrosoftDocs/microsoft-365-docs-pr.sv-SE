---
title: Admin inlagor, inlagor, spam problem, falskt negativt, skicka phish, skicka e-post för skanning, misstänkt e-post i Office 365, skanna ett mail, har Microsoft söka efter phish, har Microsoft söka efter spam, skicka e-post, skicka e-post, skumma e-post, dålig skådespelare post, misstänkt, opålitlig e-post, rapportera phish e-post till Microsoft, rapportera phish e-post till Microsoft, rapportera skadlig e-post till Microsoft, rapportera bluff e-post till Microsoft , rapportera skadlig kod i e-post till Microsoft, skräppost i inkorgen, virus i e-post
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Läs om hur du skickar misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer från företaget till Microsoft för skanning.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631387"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft

Om du är administratör i en Microsoft 365-organisation med postlådor i Exchange Online kan du använda portalen Inlämningar i Security & Compliance Center för att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft för skanning.

När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av eventuella webbadresser och bilagor med posten. Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer på klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).

Andra sätt att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft finns i 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill **Submission** gå direkt <https://protection.office.com/reportsubmission>till sidan Inlämning använder du .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare.** Mer information om rollgrupper i Security & Compliance Center finns [i Behörigheter i Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns [i Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a>Så här dirigerar du misstänkt innehåll till Microsoft-skanning

Om du vill skicka innehåll till Microsoft klickar du på knappen **Ny inlämning** längst upp till vänster på inlämningssidan. Ett utfällbart till höger på sidan visas med möjlighet att skicka antingen ett e-postmeddelande, en URL eller en fil.

### <a name="submit-a-questionable-email-to-microsoft"></a>Skicka ett tvivelaktigt e-postmeddelande till Microsoft

![Exempel på skicka e-post](../../media/submission-flyout-email.PNG)

1. Om du vill skicka ett e-postmeddelande väljer du **e-post** och anger **e-postnätverksmeddelande-ID** eller laddar upp e-postfilen.

2. Ange vilka mottagare som du vill köra principkontrollen mot. Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av principer på användar- eller klientnivå.

3. Ange om e-postmeddelandet ska ha blockerats eller inte. Om e-postmeddelandet skulle ha blockerats anger du om det ska ha blockerats som skräppost, nätfiske eller skadlig kod. Om du inte är säker på vilken typ det kan vara, använd ditt bästa omdöme.

   - Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.

   - Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter. Du ser ytterligare information om inlämningen genom att klicka på statuslänken. Detta inkluderar resultaten av policykontrollen och återscan dom. Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell rescan baserat på vissa attribut för e-post, URL eller fil.

4. Klicka på knappen **Skicka.**

### <a name="send-a-suspect-url-to-microsoft"></a>Skicka en misstänkt WEBBADRESS till Microsoft

![Exempel på skicka e-post](../../media/submission-url-flyout.png)

1. Om du vill skicka in en URL väljer du **URL** från utfällbara. Skriv in den fullständiga URL:en inklusive protokollet (**https://**).

   Om du har valt **Ska ha filtrerats**anger du om webbadressen är nätfiske eller skadlig kod.

2. Klicka på knappen **Skicka.**

### <a name="submit-a-suspected-file-to-microsoft"></a>Skicka en misstänkt fil till Microsoft

![Exempel på skicka e-post](../../media/submission-file-flyout.PNG)

1. Om du vill skicka en fil väljer du **Arkiv** från det utfällbara fönstret och överför filen som du vill skanna.

2. Klicka på knappen **Skicka.**
