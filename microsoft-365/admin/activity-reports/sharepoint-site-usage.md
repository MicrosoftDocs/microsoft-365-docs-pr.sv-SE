---
title: Microsoft 365-rapporter i administrationscentret – Användning av SharePoint-webbplatser
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Hämta sharepoint-webbplatsanvändningsrapporten för att veta hur många filer användare lagrar på SharePoint-webbplatser, hur många som används aktivt och det totala lagringsutrymmet som förbrukas. '
ms.openlocfilehash: 3a7fece8868ceb34cbcf356e23fd13006defa439
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560405"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporter i administrationscentret – Användning av SharePoint-webbplatser

Som Microsoft 365-administratör visar instrumentpanelen **Rapporter** aktivitetsöversikten för olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Du kan till exempel få en överblick på hög nivå av det värde som du får från SharePoint som det totala antalet filer som användare lagrar på SharePoint-webbplatser, hur många filer som används aktivt och hur mycket lagring som används på alla dessa webbplatser. Du kan sedan öka detaljnivån på rapporten om SharePoint-webbplatsanvändningen för att förstå trenderna och information per webbplatsnivå för alla webbplatser. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.
Microsoft 365-rapporter i administrationscentret stöds inte för GCC High- och DoD-klienter.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Så här kommer du till rapporten om SharePoint-webbplatsanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj Användning av **SharePoint-webbplats** i listrutan **Välj en rapport** \> **Site usage**.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Tolka rapporten om SharePoint-webbplatsanvändning

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |I rapporten **SharePoint-webbplatsanvändning** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna. <br/> |
|3.  <br/> |I diagrammet **Webbplatser** visas det totala antalet och antalet aktiva webbplatser. En webbplats där användare har visat, ändrat, laddat upp, laddat ned, delat eller synkroniserat en fil eller visat en sida inom rapporteringsperioden.  <br/> |
|4.  <br/> |I diagrammet **Filer** visas det totala antalet filer på alla webbplatser och antalet aktiva filer. I det totala antalet ingår både användar- och systemfiler. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  <br/> En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data.           |
|5.  <br/> |I diagrammet **Lagring** visas trenden för lagringsutrymme som tilldelats och använts under rapporteringsperioden.  <br/> |
|6.  <br/> |I diagrammet **Sidor** visas antalet sidor som visats på alla webbplatser.  <br/> |
|7.  <br/> |Du kan filtrera diagram som du ser genom att markera ett objekt i förklaringen. Välj filer **eller** **Aktiva filer**i diagrammet **Filer** . I **diagrammet Platser** kan du välja **Totalt antal platser** eller Aktiva **webbplatser**. I **lagringsdiagrammet** kan du välja **Lagringsallokerad** eller **Lagring som förbrukas.** När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|8.  <br/> | Tabellen visar en uppdelning av aktiviteterna per webbplats.  <br/> ![Kolumnalternativ för användningsrapport](../../media/sharepointsite-usage.png)           <br/> **Webbplatsens URL** är den fullständiga URL-adressen för webbplatsen.  <br/> **Borttagna** är borttagningsstatusen för webbplatsen. Det tar minst 7 dagar för webbplatser att markeras som borttagna.  <br/> **Webbplatsägare** är användarnamnet på den primära ägaren av webbplatsen.  <br/>**Webbplatsens huvudnamn** är e-postadressen till webbplatsens ägare.  <br/> **Datum för senaste aktivitet (UTC)** är datumet för den senaste gången som filaktivitet upptäcktes eller en sida visades på webbplatsen.  <br/> **Filer** är antalet filer på webbplatsen.  <br/> **Aktiva filer** är antalet aktiva filer på webbplatsen. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  <br/> En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data. >  Om du tog bort filer under tidsperioden som angetts för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på webbplatsen.<br/>**Använt lagringsutrymme (MB)** är mängden lagringsutrymme som för närvarande används på webbplatsen.  <br/> **Tilldelat lagringsutrymme (MB)** är den högsta mängden lagringsutrymme som tilldelats för webbplatsen.  <br/> **Visade sidor** är antalet gånger som sidor har visats på webbplatsen.  <br/> **Sidor som besökts** är antalet unika sidor som har besökts på webbplatsen.  <br/> **Rotwebbmall** är den mall som använts för att skapa webbplatsen.  <br/> Om du vill filtrera data efter olika platstyper exporterar du data och använder kolumnen Rotwebbmall. <br/>Om organisationens principer hindrar dig från att visa rapporter där användarinformation kan identifieras kan du ändra sekretessinställningen för alla dessa rapporter. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Välj **Hantera kolumner**Hantera kolumner om du vill lägga till eller ta bort kolumner från ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) rapporten.    <br/> |
|10.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera** ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) export. Då exporteras data för alla webbplatser och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 webbplatser kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 webbplatser måste du exportera data för att kunna filtrera och sortera.  <br/> När data exporteras till en Excel-fil bör du tänka på att datumet då innehållsrapporten genererades återspeglas i filen i kolumnen **Data från** och med.      <br/>   |
|||
   

