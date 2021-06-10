---
title: Lägga till din Google Workspace-domän
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Lär dig hur du flyttar din domän från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578777"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Lägg till Google Workspace-domänen i Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Lägg till Google Workspace-domänen i Microsoft 365 för företag så att du kan fortsätta använda din e-postadress för företaget.

## <a name="try-it"></a>Prova själv!

1. Gå till [Microsoft 365 administrationscentret.](https://admin.microsoft.com)
1. I det Microsoft 365 navigeringscentret i vänstra navigeringsfältet väljer du Visa alla **,** **Inställningar** och sedan **Domäner.**
1. Välj **Add domain**, enter your domain name och select Use this **domain**. 
1. Välj Add **a TXT record to the domains DNS records**, select **Continue** och copy the TXT value. 
1. Gå tillbaka till administratörskonsolen för [Google](https://admin.google.com), välj **Domäner** **,** Hantera domäner **,** Visa information , Hantera **domän,** **DNS** och rulla ned till **Anpassade resursposter**. 
1. Öppna listrutan record type, välj **TXT**, klistra in TXT-värdet du kopierade och välj sedan **Add**. 

    Uppdateringen tar normalt ett faktum inom några minuter men kan ta upp till 48 timmar. 
1. Återgå till Microsoft 365, välj **Verifiera** och sedan **Stäng.** 
1. Om du vill ange din domän som primär e-postadress för användarna väljer du Användare aktiva användare i **det**  >  **vänstra navigeringsfältet.** 
1. Välj en användare, välj **Hantera användarnamn och e-post** **,** Redigera , välj din domän i listrutan och välj sedan **Klar** och **Spara ändringar.** 
1. Upprepa proceduren för varje användare. 

    När du är klar är du redo att installera Office och migrera dina e-post- och kalenderobjekt till Microsoft 365. 