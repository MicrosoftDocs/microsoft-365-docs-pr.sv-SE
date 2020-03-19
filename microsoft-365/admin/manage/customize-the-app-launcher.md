---
title: Lägga till anpassade paneler i startprogrammet
f1.keywords:
- CSH
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
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Skapa snabblänkar till e-post, dokument, appar, SharePoint-webbplatser, externa webbplatser och andra resurser genom att lägga till anpassade paneler i startprogrammet. '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809769"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Lägga till anpassade paneler i startprogrammet

I Office 365 kan du snabbt och enkelt öppna e-post, kalendrar, dokument och program med hjälp av Office 365-startprogrammet ([läs mer](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Dessa är program som du får i Office 365 samt de anpassade program som du lägger till via [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) eller [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
Du kan lägga till egna paneler i startprogrammet som pekar på SharePoint-webbplatser, externa webbplatser, äldre program och mycket mer. De anpassade panelerna visas under **Alla** appar i startprogrammet, men du kan fästa dem under **Start**-appar och instruera användarna att göra samma sak. Det här gör det enkelt att hitta de webbplatser, program och resurser som ni behöver i arbetet. I exemplet nedan används en egen panel som heter "Contoso-portalen" för att nå ett företags SharePoint-intranätwebbplats. 
  
![Startprogram för Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Lägga till en anpassad panel i startprogrammet

1. Gå till fliken**Inställningar** **i** > administrationscentret och välj **organisationsprofil.**
    
2. Välj Paneler för **anpassad startprogram**på fliken **Organisationsprofil** .
  
3. Välj **Lägg till en anpassad panel**. 
  
4. Ange ett **Panelnamn** för den nya panelen. Namnet visas sedan i panelen. 
    
5. Ange en **webbadress** för panelen. Det här är den plats där du vill att användarna ska gå när de väljer panelen i startprogrammet. Använd HTTPS i webbadressen.<br/>TIPS: Om du skapar en panel för en SharePoint-webbplats navigerar du till den webbplatsen, kopierar webbadressen och klistrar in den här. Webbadressen till din standardgruppwebbplats ser ut så här:`https://<company_name>.sharepoint.com` 
  
6. Ange en **URL till bilden** för panelen. Bilden visas på sidan Mina program och i startprogrammet.<br/>TIPS: Bilden ska vara 60x60 pixlar och vara tillgänglig för alla i organisationen utan att behöva autentisering.

7. Ange en **beskrivning** för panelen. Det ser du när du väljer panelen på sidan Mina appar och väljer **Appinformation**. 
  
8. Välj **Spara ändringar** om du vill skapa den anpassade panelen. 
    
Den anpassade panelen visas nu i startprogrammet på fliken **Alla** för dig och dina användare. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Befordra panelen till Startprogrammet

1. Välj ikonen för startprogrammet och välj **alla appar**. 
    
2. Leta reda på den nya panelen för din app, välj ellips och välj **Fäst för att starta**.
  
    > [!NOTE]
    > Om du inte ser länken till den anpassade panelen du skapade i föregående steg bör du kontrollera att du har tilldelats en Exchange Online-postlåda och att du loggat in till postlådan minst en gång. De här stegen krävs för anpassade paneler i Office 365. 
  
> [!IMPORTANT]
> Både du och användarna måste utföra de här åtgärderna när ni vill att anpassade paneler från Mina program-sidan ska fästas i startprogrammet. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Gå till<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">profilsidan</a> **Inställningar** > organisation i administrationscentret.
    
2. Välj **Redigera**bredvid Lägg till **anpassade paneler för organisationen**på sidan Organisations **profilprofil.**

3. Uppdatera **panelnamnet**, **URL:en**, **beskrivningen** och **bild-URL:en** för den anpassade brickan (se den [Lägga till en anpassad panel i startprogrammet](#add-a-custom-tile-to-the-app-launcher)).
    
4. Välj **Uppdatera** \> **Stäng**. 
    
Om du vill ta bort en anpassad panel markerar du panelen i fönstret **Anpassade paneler** och väljer Ta **bort panel** > **bort**. 
  
## <a name="whats-next"></a>Hur går jag vidare?

Förutom att lägga till paneler i startprogrammet kan du lägga till startprogramspanelerna i Office 365-navigeringsfältet ([läs mer](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Information om hur du anpassar utformningen av Office 365 så att den matchar organisationens varumärke finns i [Anpassa Office 365-temat](../setup/customize-your-organization-theme.md).
  

