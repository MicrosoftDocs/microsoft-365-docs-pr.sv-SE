---
title: Skapa e-postregler för utpressningstrojan
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580504"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Skapa e-postregler för att förhindra utpressningstrojaner

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 hjälper till att skydda företaget mot utpressningstrojaner genom att förhindra att filer som potentiellt är skadliga, som JavaScript, batchfiler och körbara filer, öppnas i Outlook. Följ de här anvisningarna om du vill öka den här skyddsnivån genom att lägga till regler som blockerar eller varnar för ytterligare typer av filer.

## <a name="try-it"></a>Prova!

1. Från administrationscentret i [https://admin.microsoft.com](https://admin.microsoft.com) väljer du **Exchange** under **Administrationscenter**.
1. I menyn till vänster väljer du **E-postflöde**.
1. På fliken Regler väljer du pilen bredvid plustecknet (+) och väljer sedan **Skapa en ny regel.**
1. På sidan **ny regel** anger du ett namn för regeln, bläddrar till slutet och väljer sedan **Fler alternativ**.
1. Under **Använd den här regeln om** väljer du Valfri **bifogad** fil och väljer sedan **filnamnstillägget innehåller följande ord**.
1. I rutan under ange ord eller fraser anger du de filnamnstillägg som du vill att regeln ska tillämpas på, till exempel **filnamnstillägg** som kan innehålla makron. Använd plustecknet (+) för att lägga till ett i taget.

    Mer information om filtyper finns i [Skydda mot utpressningstrojaner.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)

1. Rulla nedåt för att granska listan och välj sedan **OK.**
1. På sidan **ny regel** väljer du Lägg **till villkor** och sedan ett villkor under **Gör följande.**
1. Det finns många regelalternativ att välja bland, men i det här exemplet väljer vi **att meddela mottagaren med ett meddelande**.
1. Ange meddelandetext för meddelandet och välj sedan **OK.**
1. Valfritt: På **sidan ny** regel väljer du lägg till undantag **och** anger all information om undantag för regeln, till exempel meddelanden från betrodda avsändare.
1. På sidan ny regel väljer du Spara **och granskar** den sammanfattande informationen för regeln.