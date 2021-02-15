---
title: Microsoft 365-rapporter i administrationscentret – SharePoint-webbplatsanvändning
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
description: Få rapporten om SharePoint-webbplatsanvändning att ta reda på hur många filer användarna lagrar på SharePoint-webbplatser, hur många som används aktivt och hur mycket lagringsutrymme som används totalt.
ms.openlocfilehash: 403ebfd75fca5ba5777832140155bb09734db3c7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233519"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporter i administrationscentret – SharePoint-webbplatsanvändning

Som Microsoft 365-administratör kan du **på** instrumentpanelen Rapporter se en översikt över aktiviteter i olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Du kan till exempel få en överblick på hög nivå av det värde som du får från SharePoint som det totala antalet filer som användare lagrar på SharePoint-webbplatser, hur många filer som används aktivt och hur mycket lagring som används på alla dessa webbplatser. Du kan sedan öka detaljnivån på rapporten om SharePoint-webbplatsanvändningen för att förstå trenderna och information per webbplatsnivå för alla webbplatser. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.
Microsoft 365-rapporter i administrationscentret stöds inte för GCC High- och DoD-klientorganisationen.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Så här kommer du till rapporten om SharePoint-webbplatsanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på SharePoint-kortet.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Tolka rapporten om SharePoint-webbplatsanvändning

Du kan visa webbplatsanvändningen i SharePoint-rapporten genom att välja **fliken Webbplatsanvändning.**<br/>![Microsoft 365-rapporter – Microsoft SharePoint-webbplatsanvändningsrapport.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport om SharePoint-webbplatsanvändning – välj kolumner](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Du kan också exportera rapportdata till en CSV-fil för Excel genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Webbplats-URL  <br/> |Den fullständiga URL:en för webbplatsen. <br/> |
|Deleted  <br/> |Borttagningsstatus för webbplatsen. Det tar minst 7 dagar för webbplatser att markeras som borttagna.  <br/> |
|Webbplatsägare  <br/> |Användarnamnet för webbplatsens primära ägare.   <br/> |
|Huvudnamn för webbplatsägare  <br/> |E-postadressen till webbplatsens ägare. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Datumet för den senaste gången filaktivitet upptäcktes eller en sida visades på webbplatsen.  <br/> |
|Id för känslighet för webbplatsen  <br/> | Känslighetsetiketten på webbplatsen.  <br/> |
|Extern delning  <br/> | De externa inställningar som kan delas på webbplatsen.  <br/> |
|Princip för ohanterad enhet  <br/> | Principen för webbplatsåtkomst för ohanterade enheter.  <br/> |
|Geoplats  <br/> | Webbplatsens geoplats.  <br/> |
|Filer  <br/> |Antalet filer på webbplatsen. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer på webbplatsen.<br/> Obs! Om filer har tagits bort under den angivna tidsperioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på webbplatsen.  <br/> |
|Använt lagringsutrymme (MB)  <br/> |Mängden lagringsutrymme som för närvarande används på webbplatsen.  <br/>|
|Tilldelat lagringsutrymme (MB)  <br/> |Största tillåtna lagringsutrymme som tilldelats för webbplatsen.  <br/>|
|Sidvyer  <br/> |Antalet gånger sidor har visats på webbplatsen.  <br/>|
|Besökta sidor  <br/> |Antalet unika sidor som besökts på webbplatsen.  <br/>|
|Antal anonyma länkar  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "Alla med länken" på webbplatsen.  <br/>|
|Antal företagslänk  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "Personer i organisationen med länken" på webbplatsen.  <br/>|
|Säker länk för gästantal  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "vissa personer" på webbplatsen.  <br/>|
|Säker länk för antal medlemmar  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "vissa personer" på webbplatsen.  <br/>|
|Rotwebbmall  <br/> |Den mall som används för att skapa webbplatsen.  <br/> OBS! Om du vill filtrera data efter olika webbplatstyper exporterar du data och använder kolumnen Rotwebbmall. |
|||