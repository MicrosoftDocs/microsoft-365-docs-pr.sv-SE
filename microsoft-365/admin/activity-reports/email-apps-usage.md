---
title: Microsoft 365-rapporter i administrationscentret – användning av e-postappar
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Läs om hur du får användningsrapport för e-postappar för att få reda på om e-postappar som ansluter till Exchange Online och outlook-versionanvändarna använder.
ms.openlocfilehash: bfd8a911652283685486202203d0302479a8270e
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005758"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporter i administrationscentret – användning av e-postappar

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användningsrapporten för e-postappar kan du se hur många e-postappar som ansluter till Exchange Online. Du kan även se versionsinformationen för Outlook-program som användarna använder, så att du kan följa upp med dem som använder versioner som inte stöds och installera versioner av Outlook som stöds.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Så här kommer du till rapporten e-postappar

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj Användning av **appen Välj** en rapport i listrutan Välj **en rapport** \> **Email app usage**.
  
## <a name="interpret-the-email-apps-report"></a>Tolka rapporten e-postappar

Du kan få en vy över aktiviteten för e-postappar genom att titta på diagrammen **Användare** **och klienter.** 
  
![E-postklienter som används](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |Användningsrapporten för **e-postappar** kan visas för trender under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |I vyn **Användare** visas antalet unika användare som har anslutit till Exchange Online med ett e-postprogram.  <br/> |
|4.  <br/> |I vyn **Appar** visas antalet unika användare per app under den valda tidsperioden.  <br/> |
|5.  <br/> |I **vyn Versioner** visas antalet unika användare för varje version av Outlook i Windows.  <br/> |
|6.  <br/> | I diagrammet **Användare** är Y-axeln det totala antalet unika användare som har anslutit till ett program någon dag under rapporteringsperioden.  <br/>  I diagrammet **Användare** är X-axeln antalet unika användare som har använt programmet under rapporteringsperioden.  <br/>  I diagrammet **Appar** är Y-axeln det totala antalet unika användare som har använt ett visst program under rapporteringsperioden.  <br/>  I diagrammet **Appar** är X-axeln listan över program i organisationen.  <br/>  I diagrammet **Versioner** är Y-axeln det totala antalet unika användare med en viss version av Outlook för skrivbordet. Om rapporten inte kan matcha versionsnumret för Outlook visas kvantiteten som **Obestämd**.  <br/>  I diagrammet **Versioner** är X-axeln listan över program i organisationen.  <br/> |
|7.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **Användare** väljer du till exempel **Mac-e-post** eller **Outlook** ![ Outlook-lista över e-postklienter. Välj e-postklienten för att få mer rapporteringsdata om den klienten.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) för att bara visa information om det objektet. När du ändrar det här valet ändras inte informationen i rutnätstabellen. Mac Mail, Outlook för Mac, Outlook Mobile, Outlook för skrivbordet och Outlook på webben är exempel på e-postprogram som du kan ha i organisationen.  <br/> |
|8.  <br/> | Du kan kanske inte se alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/> **Användarnamn** är namnet på e-postappens ägare.  <br/> **Senaste aktivitetsdatum** är det senaste datumet då användaren läste eller skickade ett e-postmeddelande.  <br/> **Mac Mail**, **Outlook för Mac** och **Outlook**, **Outlook Mobile** och **Outlook på webben** är exempel på e-postprogram som du kan ha i organisationen.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Välj **Hantera kolumner** om du vill lägga till eller ta bort kolumner från rapporten.  <br/> ![Användningsrapport för e-postappar – välj kolumner](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
