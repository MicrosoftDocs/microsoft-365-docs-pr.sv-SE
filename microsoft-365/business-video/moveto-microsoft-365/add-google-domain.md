---
title: Lägga till din Google Workspace-domän
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
description: Lär dig hur du flyttar din domän från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794747"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Lägga till din Google Workspace-domän i Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Lägg till din Google Workspace-domän till Microsoft 365 för företag så att du kan fortsätta att använda din företags e-postadress.

## <a name="try-it"></a>Prova!

1. Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).
1. I administrations centret för Microsoft 365 väljer du **Visa alla**, **Inställningar** och sedan **domäner** i det vänstra navigerings fältet.
1. Välj **Lägg till domän**, ange ditt domän namn och välj sedan **Använd denna domän**. 
1. Välj, **Lägg till en TXT-post till domänernas DNS-poster**, Välj **Fortsätt** och kopiera värdet txt. 
1. Gå tillbaka till [Google Admin Console](https://admin.google.com), Välj **domäner**, **hantera domäner**, **Visa information**, **Hantera domän**, **DNS** och sedan bläddra ned till **anpassade resurs poster**. 
1. Öppna List rutan Record Type, Välj **txt**, klistra in det txt-värde som du kopierade och välj sedan **Lägg till**. 

    Det tar vanligt vis några minuter att uppdatera uppdateringen, men det kan ta upp till 48 timmar. 
1. Gå tillbaka till administrations centret för Microsoft 365, Välj **Verifiera** och sedan **Stäng**. 
1. Om du vill ange din domän som primär e-postadress för dina användare väljer du **användare**  >  **aktiva användare** i det vänstra navigerings fältet. 
1. Välj en användare, Välj **hantera användar namn och e-post**, **Redigera**, välj din domän i list rutan och välj sedan **klar** och **Spara ändringar**. 
1. Upprepa proceduren för varje användare. 

    När du är klar kan du installera Office-apparna och migrera dina e-post-och Kalender objekt till Microsoft 365. 