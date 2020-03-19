---
title: Skapa, redigera eller ta bort en anpassad användarvy i Office 365
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Lär dig att använda filter för att skapa, redigera eller ta bort anpassad användarvy i Office 365.
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42807185"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>Skapa, redigera eller ta bort en anpassad användarvy i Office 365

Om du är en global administratör eller användarhanteringsadministratör för Office 365 kan du skapa anpassade användarvyer för att visa en viss delmängd av användare. Dessa vyer är utöver den standarduppsättning vyer som medföljer Office 365. Du kan skapa, redigera eller ta bort anpassade användarvyer och de anpassade vyer du skapar är tillgängliga för alla administratörer.

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>Anpassade användarvyer i administrationscentret

::: moniker range="o365-worldwide"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i **filterlistan** som alla administratörer i företaget ser när de går till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

::: moniker range="o365-germany"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de går till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

::: moniker range="o365-21vianet"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de går till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

> [!TIP]
>  Standardanvändarvyer visas som standard i listrutan **Filter.** Standardfiltren omfattar **Alla användare,** **licensierade användare,** **Gästanvändare,** **Inloggning tillåten**, **Logga in blockerad,** **Olicensierade användare,** **Användare med fel,** **Faktureringsadministratörer,** **Globala administratörer,** **Helpdesk-administratörer,** **Tjänstadministratörer**och **användarhanteringsadministratörer**. Du kan inte redigera eller ta bort standardvyer. 

Några saker att notera om standardvyer: 

- Vissa standardvyer visar en osorterad lista om det finns fler än 2 000 användare i listan. Om du vill hitta specifika användare i den här listan använder du sökrutan. 
- Om du inte har köpt Office 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan. Mer information finns i [Tilldela administratörsroller](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Välj filter för din anpassade användarvy

Du kan skapa och redigera dina anpassade vyer i **fönstret Anpassat filter.** Om du väljer flera filteralternativ får du resultat som innehåller användare som matchar alla valda villkor. I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare på en viss domän som befinner sig i Kanada. 

  
 **A - Domän** Om du har flera domäner för din organisation kan du välja från en listruta med domäner som är tillgängliga. 
  
 **B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade. 
  
 **C - Plats** Välj en plats i en listruta med länder. 
  
 **D - Tilldelad produktlicens** Välj bland en listruta med licenser som är tillgängliga i din organisation. Använd det här filtret om du vill visa användare som har den licens som du har tilldelat dem. Användare kan också ha ytterligare licenser. 
  
Du kan också filtrera efter ytterligare användarprofilinformation som används i din organisation, till exempel avdelning, stad, stat eller provins, land eller region eller befattning.
  
 **Övriga villkor:**
  
- **Synkroniserade användare** Välj den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte. 
    
- **Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel. 
    
- **Olicensierade användare** Välj den här rutan om du vill söka efter alla användare som inte har tilldelats en licens. Resultaten för den här vyn kan också omfatta användare som har en Exchange-postlåda men som inte har en licens. Om du vill spåra dessa användare specifikt använder du filtret **Olicensierade användare med Exchange-postlådor eller arkiv**. Resultaten för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men som inte har någon licens.
    
- **Olicensierade användare med Exchange-postlådor eller arkiv** Välj den här rutan om du vill visa användarkonton som har skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats en Office 365-licens. Resultatet av det här filtret inkluderar användare som har eller som har tilldelats ett Exchange-arkiv. 
    
> [!TIP]
> Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan. I det här fallet använder du sökrutan för att hitta användare eller redigera den anpassade vyn för att förfina sökningen. 
  
## <a name="create-a-custom-user-view"></a>Skapa en anpassad användarvy

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. På sidan **Aktiva användare** väljer du **Filter** och väljer **Nytt filter**.
  
3. På sidan **Anpassat filter** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.
    
::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  

2. På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end


::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

2. På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Redigera eller ta bort en anpassad användarvy

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. På sidan **Aktiva användare** väljer du **Filter,** markerar det filter som du vill ändra och väljer sedan **Redigera filter**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassat filter** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret väljer du **Ta bort**längst ned på sidan. 
    
::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  

2. På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter du vill ändra och väljer sedan **Redigera den här vyn**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret väljer du **Ta bort anpassad vy**längst ned på sidan . 

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

2. På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter du vill ändra och väljer sedan **Redigera den här vyn**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret väljer du **Ta bort anpassad vy**längst ned på sidan . 

::: moniker-end


     

