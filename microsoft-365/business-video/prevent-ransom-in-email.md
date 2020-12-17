---
title: Skapa e-postregler för utpressnings tro Jan
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Lär dig hur du skapar e-postregler för att förhindra utpressnings tro Jan.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702446"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Skapa e-postregler för att förhindra utpressnings tro Jan

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 hjälper till att skydda ditt företag mot utpressningar genom att förhindra farliga filer, till exempel Java Script, batch och körbar, från att öppnas i Outlook. Följ de här stegen om du vill öka den här skydds nivån genom att lägga till regler som blockerar eller varnar för ytterligare typer av filer.

## <a name="try-it"></a>Prova!

1. I administrations centret [https://admin.microsoft.com](https://admin.microsoft.com) går du till och väljer **Exchange** under **administrations Center**.
1. I menyn till vänster väljer du **e-postflöde**.
1. På fliken regler väljer du pilen bredvid plus tecknet (+) och väljer sedan **skapa en ny regel**.
1. Ange ett namn för regeln på sidan **ny regel** , rulla längst ned och välj sedan **fler alternativ**.
1. Under **Använd den här regeln om** markerar du **en bifogad** fil och väljer sedan **fil namns tillägget**.
1. I rutan under **Ange ord eller fraser** anger du det fil namns tillägg som du vill att regeln ska tillämpas på, till exempel fil namns tillägg som kan innehålla makron. Använd plus tecknet (+) för att lägga till ett i taget.

    Läs mer om filtyper genom att läsa [skydda mot utpressnings tro Jan](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).

1. Bläddra nedåt och välj **OK**.
1. På sidan **ny regel** väljer du **Lägg till villkor** och väljer sedan ett villkor under **gör följande**.
1. Du har många regel alternativ att välja bland, men i det här exemplet väljer vi att **meddela mottagaren med ett meddelande**.
1. Ange meddelande text för din avisering och välj sedan **OK**.
1. Valfritt: Välj **Lägg till undantag** på sidan **ny regel** och ange eventuellt information för undantag till din regel, till exempel meddelanden från betrodda avsändare.
1. På sidan ny regel väljer du **Spara** och läser den sammanfattade regel informationen.