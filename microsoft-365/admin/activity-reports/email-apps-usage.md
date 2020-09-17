---
title: Microsoft 365-rapporter i administrations Center – användning av e-postprogram
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
description: Lär dig hur du får information om användning av e-postappar som ansluter till Exchange Online och vilken Outlook-version du använder.
ms.openlocfilehash: c6ee72390f0b9e9ead0f07c41d64bf5b7264fc1b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948250"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporter i administrations Center – användning av e-postprogram

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I rapporten e-postappar kan du se hur många e-postappar som ansluter till Exchange Online. Du kan även se versionsinformationen för Outlook-program som användarna använder, så att du kan följa upp med dem som använder versioner som inte stöds och installera versioner av Outlook som stöds.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Så här kommer du till rapporten e-postappar

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du **Exchange** \> **Använd e-postprogrammet**för Exchange.
  
## <a name="interpret-the-email-apps-report"></a>Tolka rapporten om e-postappar

Du kan få en vy i e-postappar genom att titta på diagrammen **användare** och **klienter** . 
  
![E-postklienter som används](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |**Användnings rapporten för e-postappar** kan ses för trender under de senaste 7, 30, 90 eller 180 dagar. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |I vyn **Användare** visas antalet unika användare som har anslutit till Exchange Online med ett e-postprogram.  <br/> |
|4.  <br/> |I vyn **Appar** visas antalet unika användare per app under den valda tidsperioden.  <br/> |
|5.  <br/> |I vyn **versioner** visas antalet unika användare för varje version av Outlook i Windows.  <br/> |
|18.6.  <br/> | I diagrammet **Användare** är Y-axeln det totala antalet unika användare som har anslutit till ett program någon dag under rapporteringsperioden.  <br/>  I diagrammet **Användare** är X-axeln antalet unika användare som har använt programmet under rapporteringsperioden.  <br/>  I diagrammet **Appar** är Y-axeln det totala antalet unika användare som har använt ett visst program under rapporteringsperioden.  <br/>  I diagrammet **Appar** är X-axeln listan över program i organisationen.  <br/>  I diagrammet **Versioner** är Y-axeln det totala antalet unika användare med en viss version av Outlook för skrivbordet. Om det inte går att lösa versions numret för Outlook i rapporten visas antalet som ej **fastställt**.  <br/>  I diagrammet **Versioner** är X-axeln listan över program i organisationen.  <br/> |
|borttagning.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **användare** väljer du till exempel **Mac Mail** eller Outlook- **Outlook** ![ lista över e-postklienter. Välj e-postklienten för att få mer rapporterings data för klienten.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) för att bara visa information om det objektet. När du ändrar det här valet ändras inte informationen i rutnätstabellen. Mac Mail, Outlook för Mac, Outlook Mobile, Outlook för skrivbordet och Outlook på webben är exempel på e-postprogram som du kan ha i organisationen.  <br/> |
|8.2.  <br/> | Du kan kanske inte se alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/> **Username** är namnet på e-postappens ägare.  <br/> **Datum för senaste aktivitet** är det senaste datumet som användaren läst eller skickat ett e-postmeddelande.  <br/> **Mac Mail**, **Outlook för Mac** och **Outlook**, **Outlook Mobile** och **Outlook på webben** är exempel på e-postprogram som du kan ha i organisationen.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Välj **Hantera kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport över användning av e-postappar – Välj kolumner](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.3.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
