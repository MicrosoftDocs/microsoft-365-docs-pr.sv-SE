---
title: Skapa e-postregler för utpressningstrojan
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skapar e-postregler för att förhindra utpressningstrojaner.
ms.openlocfilehash: 0d8b4a9de881f47752ac0bfbf778453d6ee73046
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422261"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Skapa e-postregler för att förhindra utpressningstrojaner

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 hjälper till att skydda företaget mot utpressningstrojaner genom att förhindra att filer som potentiellt är skadliga, som JavaScript, batchfiler och körbara filer, öppnas i Outlook. Följ de här stegen om du vill öka den här skyddsnivån genom att lägga till regler som blockerar eller varnar för ytterligare typer av filer.

## <a name="try-it"></a>Prova!

1. I administrationscentret väljer [https://admin.microsoft.com](https://admin.microsoft.com) du **Exchange** under **Administrationscenter.**
1. Välj e-postflöde på menyn **till vänster.**
1. På fliken Regler väljer du pilen bredvid plustecknet (+) och väljer sedan **Skapa en ny regel.**
1. På den **nya regelsidan** anger du ett namn för regeln, bläddrar längst ned och väljer **Sedan Fler alternativ.**
1. Under **Använd den här regeln om,** välj **Valfri** bifogad fil och välj **sedan filnamnstillägget innehåller följande ord.**
1. I rutan under ange ord eller fraser anger du de filnamnstillägg som du vill att regeln ska tillämpas på, till exempel **filnamnstillägg** som kan innehålla makron. Använd plustecknet (+) om du vill lägga till ett i taget.

    Läs mer om filtyper genom att läsa [Skydda mot utpressningstrojaner.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Rulla nedåt för att granska listan och välj **sedan OK.**
1. På den **nya regelsidan** väljer **du Lägg till** villkor och väljer sedan ett villkor under Gör **följande.**
1. Det finns många regelalternativ att välja bland, men i det här exemplet väljer vi att **meddela mottagaren med ett meddelande.**
1. Ange meddelandetext för aviseringen och välj sedan **OK.**
1. Valfritt: Välj **Lägg** till undantag på den nya regelsidan och ange information om undantag för regeln, till exempel meddelanden från betrodda avsändare.
1. På den nya regelsidan väljer du **Spara och** granskar den sammanfattande informationen för regeln.