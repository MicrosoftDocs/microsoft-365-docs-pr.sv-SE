---
title: Microsoft 365-rapporter i administrations centret – SharePoint-webbplatsens användning
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Hämta rapporten om användning av SharePoint-webbplatser för att få veta hur många filer användarna lagrar på SharePoint-webbplatser, hur många som används aktivt och hur mycket lagrings utrymme som förbrukas.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649877"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporter i administrations centret – SharePoint-webbplatsens användning

Som Microsoft 365-administratör visar instrument panelen **rapporter** dig översikten över olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Du kan till exempel få en överblick på hög nivå av det värde som du får från SharePoint som det totala antalet filer som användare lagrar på SharePoint-webbplatser, hur många filer som används aktivt och hur mycket lagring som används på alla dessa webbplatser. Du kan sedan öka detaljnivån på rapporten om SharePoint-webbplatsanvändningen för att förstå trenderna och information per webbplatsnivå för alla webbplatser. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.
Microsoft 365-rapporter i administrations centret stöds inte för GCC-och DoD-klienter.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Så här kommer du till rapporten om SharePoint-webbplatsanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på SharePoint-kortet.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Tolka rapport om SharePoint-webbplatsens användning

Du kan visa webbplats användningen i SharePoint-rapporten genom att välja fliken **webbplats användning** .<br/>![Microsoft 365-rapporter – rapport om Microsoft SharePoint-webbplats.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport över användning av SharePoint-webbplats – Välj kolumner](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Webbplatsens URL  <br/> |Den fullständiga URL-adressen för webbplatsen. <br/> |
|Deleted  <br/> |Borttagnings status för webbplatsen. Det tar minst 7 dagar för webbplatser att markeras som borttagna.  <br/> |
|Webbplats ägare  <br/> |Användar namnet på den primära ägaren av webbplatsen.   <br/> |
|Huvud namn för webbplats ägare  <br/> |E-postadressen till ägaren till webbplatsen. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Datumet för den senaste tids aktiviteten upptäcktes eller en sida visades på webbplatsen.  <br/> |
|Hjälpfiler  <br/> |Antalet filer på webbplatsen. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer på webbplatsen.<br/> OBS! om filer togs bort under den angivna tids perioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på webbplatsen.  <br/> |
|Använt lagrings utrymme (MB)  <br/> |Mängden lagrings utrymme som används på webbplatsen.  <br/>|
|Allokerat lagrings utrymme (MB)  <br/> |Det högsta tillåtna lagrings utrymmet för webbplatsen.  <br/>|
|Sidvyer  <br/> |Antalet gånger som sidor visades på webbplatsen.  <br/>|
|Besökta sidor  <br/> |Antalet unika sidor som besökts på webbplatsen.  <br/>|
|Rotmapp med rot  <br/> |Den mall som används för att skapa webbplatsen.  <br/> Obs! Om du vill filtrera data efter olika webbplats typer exporterar du dem och använder kolumnen rotmapp. |
|||