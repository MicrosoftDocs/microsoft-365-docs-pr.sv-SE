---
title: Lägga till en Google Workspace-domän
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du flyttar din domän från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925008"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Lägga till en Google Workspace-domän i Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Lägg till din Google Workspace-domän i Microsoft 365 för företag så att du kan fortsätta använda din e-postadress för företaget.

## <a name="try-it"></a>Prova!

1. Gå till [administrationscentret för Microsoft 365.](https://admin.microsoft.com)
1. I det vänstra navigeringsfältet i administrationscentret för Microsoft 365 väljer du **Visa alla** inställningar **och** sedan **Domäner.**
1. Välj **Lägg till domän,** ange domännamnet och välj Använd **den här domänen.** 
1. Välj Lägg **till en TXT-post i domänerna DNS-poster,** **välj Fortsätt** och kopiera TXT-värdet. 
1. Gå tillbaka till [Googles administratörskonsol](https://admin.google.com)och välj **Domäner,** Hantera **domäner,** Visa **information,** Hantera **domän,** **DNS** och bläddra ned till **Anpassade resursposter.** 
1. Öppna listrutan posttyp, välj **TXT,** klistra in TXT-värdet du kopierade och välj Sedan **Lägg till.** 

    Uppdateringen tar vanligtvis ett faktum inom några minuter men kan ta upp till 48 timmar. 
1. Gå tillbaka till administrationscentret för Microsoft 365, **välj** Verifiera och stäng **sedan.** 
1. Om du vill ange din domän som primär e-postadress för användarna väljer du Användare aktiva användare **i** det  >  **vänstra navigeringsfältet.** 
1. Välj en användare, välj **Hantera användarnamn och e-post,** Redigera, välj din domän i listrutan och välj sedan **Klar** och Spara **ändringar.** 
1. Upprepa proceduren för varje användare. 

    När du är klar är du redo att installera Office-program och migrera dina e-post- och kalenderobjekt till Microsoft 365. 