---
title: Administratörsinlämningar i Office 365, O365-inlagor, office 365-skräppostproblem, O365 falskt negativt, skicka in phish i Office 365, skicka e-post för skanning, misstänkt e-post i Office 365, skanna ett e-postmeddelande, låta Microsoft söka efter phish, låta Microsoft söka efter skräppost, skicka in e-post, skicka e-post, skumma e-post, dålig skådespelare post, misstänkt, opålitlig e-post, rapportera phish e-post till Microsoft, rapportera phish e-post till Microsoft, rapportera skadlig e-post till Microsoft, rapportera bluff e-post till Microsoft, rapportera skadlig kod i e-post till Microsoft, spam e-post i inkorgskontoret 365, virus i e-postkonto 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Läs om hur du skickar misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer från office 365-klienten till Microsoft för skanning.
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812261"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Så här skickar du in misstänkt skräppost, phish, URL:er och filer till Microsoft för Office 365-skanning

Administratörer kan skicka e-postmeddelanden med hjälp av fil- eller nätverksmeddelande-ID, webbadresser och filer för skanning av Microsoft i Office 365.
Avsnittet uppdaterade inlämningar innehåller fortfarande användarrapporterade meddelanden och tillgängliga för alla kunder som använder EOP.

När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av eventuella webbadresser och bilagor med posten. Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer på klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Så här dirigerar du misstänkt innehåll till Microsoft för Office 365-skanning

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

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 Avancerat hotskyddsplan 2](office-365-ti.md)

[Skydda mot hot i Office 365](protect-against-threats.md)

[Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)
