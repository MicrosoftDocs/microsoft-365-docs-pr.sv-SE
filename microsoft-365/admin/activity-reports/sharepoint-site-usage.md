---
title: Microsoft 365-rapporter i administrations centret – SharePoint-webbplatsens användning
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
description: 'Hämta rapporten om användning av SharePoint-webbplatser för att få veta hur många filer användarna lagrar på SharePoint-webbplatser, hur många som används aktivt och hur mycket lagrings utrymme som förbrukas. '
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688211"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporter i administrations centret – SharePoint-webbplatsens användning

Som Microsoft 365-administratör visar instrument panelen **rapporter** dig översikten över olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Du kan till exempel få en överblick på hög nivå av det värde som du får från SharePoint som det totala antalet filer som användare lagrar på SharePoint-webbplatser, hur många filer som används aktivt och hur mycket lagring som används på alla dessa webbplatser. Du kan sedan öka detaljnivån på rapporten om SharePoint-webbplatsanvändningen för att förstå trenderna och information per webbplatsnivå för alla webbplatser. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.
Microsoft 365-rapporter i administrations centret stöds inte för GCC-och DoD-klienter.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Så här kommer du till rapporten om SharePoint-webbplatsanvändning

1. Gå till **rapport** användning i administrations centret \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>.
    
2. Klicka på **Visa mer** under **SharePoint-filer** . 

3. Bredvid **SharePoint-aktivitet** klickar du på nedpilen för att öppna menyn.

4. Välj användning av **SharePoint** - \> **webbplats**.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Tolka rapporten om SharePoint-webbplatsanvändning

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **SharePoint-webbplatsanvändning** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar. <br/> |
|3.  <br/> |I diagrammet **webbplatser** visas antalet sammanslagna och aktiva webbplatser, inklusive alla webbplatser som användarna hade visat, ändrat, överfört, laddat ned, delat eller synkroniserat en fil eller Visa en sida i rapporterings perioden.  <br/> |
|4.  <br/> |I diagrammet **Filer** visas det totala antalet filer på alla webbplatser och antalet aktiva filer. I det totala antalet ingår både användar- och systemfiler. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  |
|5.  <br/> |I diagrammet **Lagring** visas trenden för lagringsutrymme som tilldelats och använts under rapporteringsperioden.  <br/> |
|18.6.  <br/> |I diagrammet **Sidor** visas antalet sidor som visats på alla webbplatser.  <br/> |
|borttagning.  <br/> |Du kan filtrera diagram som visas genom att markera ett objekt i förklaringen. I diagrammet **filer** väljer du till exempel **filer** eller **aktiva filer**. I diagrammet **webbplatser** kan du välja **Totalt antal webbplatser** eller **aktiva webbplatser**. I **lagrings** diagrammet kan du välja **lagrings utrymme som tilldelats** eller **lagrat.** När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|8.2.  <br/> | Tabellen visar en uppdelning av aktiviteterna per webbplats.  <br/> ![Kolumn alternativ för användnings rapport](../../media/sharepointsite-usage.png)           <br/> **Webbplatsens URL** är den fullständiga URL-adressen för webbplatsen.  <br/> **Borttagna** är borttagningsstatusen för webbplatsen. Det tar minst 7 dagar för webbplatser att markeras som borttagna.  <br/> **Webbplatsägare** är användarnamnet på den primära ägaren av webbplatsen.  <br/>**Webbplats ägarens huvud namn** är e-postadressen till ägaren till webbplatsen.  <br/> **Datum för senaste aktivitet (UTC)** är datumet för den senaste gången som filaktivitet upptäcktes eller en sida visades på webbplatsen.  <br/> **Filer** är antalet filer på webbplatsen.  <br/> **Aktiva filer** är antalet aktiva filer på webbplatsen.<br/> OBS! om filer togs bort under den angivna tids perioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på webbplatsen.<br/>**Använt lagringsutrymme (MB)** är mängden lagringsutrymme som för närvarande används på webbplatsen.  <br/> **Tilldelat lagringsutrymme (MB)** är den högsta mängden lagringsutrymme som tilldelats för webbplatsen.  <br/> **Visade sidor** är antalet gånger som sidor har visats på webbplatsen.  <br/> **Sidor som besökts** är antalet unika sidor som har besökts på webbplatsen.  <br/> **Rotwebbmall** är den mall som använts för att skapa webbplatsen.  <br/> Obs! Om du vill filtrera data efter olika webbplats typer exporterar du dem och använder kolumnen rotmapp. <br/>Om organisationens principer hindrar dig från att visa rapporter där användar information är identifierbar kan du ändra sekretess inställningen för alla dessa rapporter. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Välj **Hantera kolumner** ![ Hantera kolumner ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) för att lägga till eller ta bort kolumner i rapporten.    <br/> |
|10.3.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja länken **Exportera** ![ export ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) . Då exporteras data för alla webbplatser och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 webbplatser kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 webbplatser måste du exportera data för att kunna filtrera och sortera.  <br/> Obs! när data exporteras till en Excel-fil visas det datum då innehålls rapporten skapades i filen i kolumnen **data från och med** .      <br/>   |
|||
