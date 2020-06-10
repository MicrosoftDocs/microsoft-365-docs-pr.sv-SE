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
description: Lär dig att använda filter för att skapa, redigera eller ta bort anpassad användarvy i Microsoft 365.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664580"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Skapa, redigera eller ta bort en anpassad användarvy

Om du är global administratör eller användarhanteringsadministratör för en Prenumeration på Microsoft 365 för företag kan du skapa anpassade användarvyer för att visa en viss delmängd användare. Dessa vyer är utöver standarduppsättningen vyer. Du kan skapa, redigera eller ta bort anpassade användarvyer och de anpassade vyer som du skapar är tillgängliga för alla administratörer.
  
## <a name="custom-user-views-in-the-admin-center"></a>Anpassade användarvyer i administrationscentret

::: moniker range="o365-worldwide"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Filter** som alla administratörer i företaget ser när de kommer till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

::: moniker range="o365-germany"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de kommer till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

::: moniker range="o365-21vianet"

När du skapar, redigerar eller tar bort en anpassad användarvy visas ändringarna i listan **Vyer** som alla administratörer i företaget ser när de kommer till sidan **Användare.** Du kan skapa upp till 50 anpassade vyer. 

::: moniker-end

> [!TIP]
>  Standardanvändarvyer visas som standard i **listrutan Filter.** Standardfiltren omfattar **Alla användare**, **Licensierade användare**, **Gästanvändare**, Inloggning tillåten , **Inloggningsblockerad**, **Olicensierade användare**, Användare med **fel,** **Faktureringsadministratörer**, **Globala administratörer**, **Helpdesk-administratörer**, **Tjänstadministratörer**och **Användarhanteringsadministratörer**. **Sign-in allowed** Du kan inte redigera eller ta bort standardvyer. 

Några saker att notera om standardvyer: 

- Vissa standardvyer visar en osorterad lista om det finns fler än 2 000 användare i listan. Om du vill hitta specifika användare i den här listan använder du sökrutan. 
- Om du inte köpte Microsoft 365 från Microsoft visas inte **faktureringsadministratörer** i standardvylistan. Mer information finns i [Tilldela administratörsroller](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Välj filter för din anpassade användarvy

Du kan skapa och redigera anpassade vyer i fönstret **Anpassad filter.** Om du väljer flera filteralternativ får du resultat som innehåller användare som matchar alla valda villkor. I följande exempel visas hur du skapar en anpassad vy med namnet "kanadensiska användare" som visar alla användare på en viss domän som finns i Kanada. 

  
 **A - Domän** Om du har flera domäner för din organisation kan du välja från en listruta med domäner som är tillgängliga. 
  
 **B - Inloggningsstatus** Välj användare som är tillåtna eller blockerade. 
  
 **C - Plats** Välj en plats i en listruta över länder. 
  
 **D - Tilldelad produktlicens** Välj från en listruta med licenser som är tillgängliga i organisationen. Använd det här filtret om du vill visa användare som har den licens som du har valt tilldelats dem. Användare kan också ha ytterligare licenser. 
  
Du kan också filtrera efter ytterligare användarprofilinformation som används i organisationen, till exempel avdelning, ort, delstat eller provins, land eller region eller befattning.
  
 **Övriga villkor:**
  
- **Endast synkroniserade användare** Markera den här rutan om du vill visa alla användare som har synkroniserats med den lokala Active Directory, oavsett om användarna har aktiverats eller inte. 
    
- **Användare med fel** Markera den här rutan om du vill visa användare som kan ha etableringsfel. 
    
- **Olicensierade användare** Markera den här rutan om du vill söka efter alla användare som inte har tilldelats en licens. Resultaten för den här vyn kan också omfatta användare som har en Exchange-postlåda men inte har någon licens. Om du vill spåra dessa användare specifikt använder du filtret **Olicensierade användare med Exchange-postlådor eller arkiv**. Resultaten för den här vyn kan också omfatta användare som har ett Exchange-arkiv, men som inte har någon licens.
    
- **Olicensierade användare med Exchange-postlådor eller arkiv** Markera den här rutan om du vill visa användarkonton som har skapats i Exchange Online och har en Exchange-postlåda, men som inte har tilldelats en Microsoft 365-licens. Resultatet av det här filtret omfattar användare som har eller har tilldelats ett Exchange-arkiv. 

> [!NOTE]
> Filtret **Olicensierade användare med Exchange-postlådor** fungerar när:
1. Postlådan har nyligen konverterats från **delad** till **användare** och den har ingen licens.
2. Postlådan har nyligen migrerats till Microsoft 365 men en licens har inte tilldelats.
3. Postlådan har skapats med PowerShell och en licens har inte tilldelats.
4. En ny postlåda som har skapats lokalt med en Cmdlet New-RemoteMailbox etableras för användaren.
    
> [!TIP]
> Om du skapar en anpassad vy som returnerar fler än 2 000 användare sorteras inte den resulterande användarlistan. I det här fallet använder du sökrutan för att hitta användare eller redigera din anpassade vy för att förfina sökningen. 
  
## <a name="create-a-custom-user-view"></a>Skapa en anpassad användarvy

::: moniker range="o365-worldwide"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.
    
2. På sidan **Aktiva användare** väljer du **Filter** och väljer **Nytt filter**.
  
3. På sidan **Anpassad filter** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.
    
::: moniker-end

::: moniker range="o365-germany"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.  

2. På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end


::: moniker range="o365-21vianet"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>. 

2. På sidan **Aktiva användare** väljer du **Vyer** och väljer Lägg till **anpassad vy**.
  
3. På sidan **Anpassad vy** anger du namnet på filtret, väljer villkoren för det anpassade filtret och väljer sedan **Lägg till**. Den anpassade vyn ingår nu i listrutan med filter.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Redigera eller ta bort en anpassad användarvy

::: moniker range="o365-worldwide"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.
    
2. På sidan **Aktiva användare** väljer du **Filter,** markerar det filter som du vill ändra och väljer sedan **Redigera filter**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassad filter** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.  

2. På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter som du vill ändra och väljer sedan **Redigera den här vyn**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort anpassad vy**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till **Aktiva användare i administrationscentret** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>. 

2. På sidan **Aktiva användare** väljer du **Vyer,** markerar det filter som du vill ändra och väljer sedan **Redigera den här vyn**. 
    
    > [!TIP]
    > Du kan bara redigera anpassade vyer. 
  
3. På sidan **Anpassad vy** redigerar du informationen efter behov och väljer sedan **Spara**. Om du vill ta bort filtret längst ned på sidan väljer du **Ta bort anpassad vy**. 

::: moniker-end


     