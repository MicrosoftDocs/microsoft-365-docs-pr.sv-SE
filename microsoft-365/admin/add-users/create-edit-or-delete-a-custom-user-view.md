---
title: Skapa, redigera eller ta bort en anpassad användarvy
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Lär dig hur du använder filter för att skapa, redigera eller ta bort anpassad användarvy i Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759936"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Skapa, redigera eller ta bort en anpassad användarvy

Om du är global administratör eller användarhanteringsadministratör för en Microsoft 365 för företag-prenumeration kan du skapa anpassade användarvyer för att visa en viss delmängd av användarna. Dessa vyer är ett tillägg till standarduppsättningen med vyer. Du kan skapa, redigera eller ta bort anpassade användarvyer, och de anpassade vyer som du skapar är tillgängliga för alla administratörer.
  
## <a name="custom-user-views-in-the-admin-center"></a>Anpassade användarvyer i administrationscentret

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i **listan Filter** som alla administratörer i företaget ser när de går till **sidan** Användare. Du kan skapa upp till 50 anpassade vyer. 

> [!TIP]
>  Standardvyer visas som standard i **listrutan** Filter. Standardfiltren omfattar Alla användare **,** Licensierade användare **,** Gästanvändare **,** Tillåtna inloggningar, Inloggning blockerade **,** Ej **licensierade** användare , Användare med fel , **Faktureringsadministratörer**, **Globala** administratörer , **Supportadministratörer**, **Tjänstadministratörer** och Användarhanteringsadministratörer.  Du kan inte redigera eller ta bort standardvyer. 

Några saker att tänka på om standardvyer: 

- I vissa standardvyer visas en osorterad lista om det finns fler än 2 000 användare i listan. Använd sökrutan för att hitta specifika användare i listan. 
- Om du inte köpte Microsoft 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan. Mer information finns i [Tilldela administratörsroller.](assign-admin-roles.md) 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Välja filter för den anpassade användarvyn

Du kan skapa och redigera dina anpassade vyer i **fönstret Anpassat** filter. Om du markerar flera filteralternativ visas resultat som innehåller användare som matchar alla de valda villkoren. I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare i en viss domän som finns i Kanada. 

  
 **A - Domän** Om du har flera domäner för organisationen kan du välja i en listrutan med domäner som är tillgängliga. 
  
 **B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade. 
  
 **C - Plats** Välj en plats i en listrutan över länder. 
  
 **D – Tilldelad produktlicens** Välj från en listrutan med licenser som är tillgängliga i din organisation. Använd det här filtret för att visa användare som har den licens du valde tilldelad. Användare kan också ha ytterligare licenser. 
  
Du kan också filtrera efter ytterligare användarprofilinformation som används i organisationen, till exempel avdelning, ort, region, land eller region eller befattning.
  
 **Övriga villkor:**
  
- **Endast synkroniserade användare** Markera den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte. 
    
- **Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel. 
    
- **Olicensierade användare** Markera den här rutan om du vill hitta alla användare som inte har tilldelats en licens. Resultatet för den här vyn kan också omfatta användare som har en Exchange-postlåda men inte har en licens. Om du vill spåra de användarna specifikt använder du **filtret Ej licensierade användare med Exchange-postlådor eller Exchange-arkiv.** Resultatet för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men inte har en licens.
    
- **Olicensierade användare med Exchange-postlådor eller Exchange-arkiv** Markera den här rutan om du vill visa användarkonton som skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats någon Microsoft 365-licens. Resultaten av det här filtret omfattar användare som har eller har tilldelats ett Exchange-arkiv. 

> [!NOTE]
> Filtret **Olicensierade användare med Exchange-postlådor** fungerar när:
1. Postlådan har nyligen konverterats från **delad** **till användare** och den har ingen licens.
2. Postlådan har nyligen migrerats till Microsoft 365 men ingen licens har tilldelats.
3. Postlådan har skapats med PowerShell och ingen licens har tilldelats.
4. En ny postlåda som har skapats lokalt med en New-RemoteMailbox-cmdlet tillhandahålls för användaren.
    
> [!TIP]
> Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan. I så fall kan du använda sökrutan för att hitta användare eller redigera den anpassade vyn för att förfina sökningen. 
  
## <a name="create-a-custom-user-view"></a>Skapa en anpassad användarvy

::: moniker range="o365-worldwide"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">administrationscentret.</a>
    
2. På sidan **Aktiva användare** väljer du **Filter** och sedan **Nytt filter**.
  
3. På sidan **Anpassat filter** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**. Den anpassade vyn ingår nu i listrutan med filter.
    
::: moniker-end

::: moniker range="o365-germany"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">administrationscentret.</a>  

2. På sidan **Aktiva användare** väljer du Vyer **och** sedan Lägg till **anpassad vy.**
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end


::: moniker range="o365-21vianet"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">administrationscentret.</a> 

2. På sidan **Aktiva användare** väljer du Vyer **och** sedan Lägg till **anpassad vy.**
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för ditt anpassade filter och väljer sedan Lägg **till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Redigera eller ta bort en anpassad användarvy

::: moniker range="o365-worldwide"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">administrationscentret.</a>
    
2. På sidan **Aktiva** användare väljer du **Filter**, väljer filtret du vill ändra och väljer sedan **Redigera filter**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassat filter** redigerar du informationen efter behov och väljer sedan **Spara**. Eller välj Ta bort längst ned på sidan om du vill ta **bort filtret.** 
    
::: moniker-end

::: moniker range="o365-germany"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">administrationscentret.</a>  

2. På sidan **Aktiva användare** väljer du **Vyer**, väljer filtret du vill ändra och väljer sedan Redigera den **här vyn.** 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. Redigera **informationen efter behov** på sidan Anpassad vy och välj sedan **Spara**. Om du vill ta bort filtret väljer du Ta bort anpassad vy längst **ned på sidan.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till Användare aktiva användare **i** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">administrationscentret.</a> 

2. På sidan **Aktiva användare** väljer du **Vyer**, väljer filtret du vill ändra och väljer sedan Redigera den **här vyn.** 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. Redigera **informationen efter behov** på sidan Anpassad vy och välj sedan **Spara**. Om du vill ta bort filtret väljer du Ta bort anpassad vy längst **ned på sidan.** 

::: moniker-end


     