---
title: Microsoft 365 Rapporter i administrationscentret – SharePoint webbplatsanvändning
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Få rapporten SharePoint för webbplatsanvändning om du vill veta hur många filer användarna lagrar på SharePoint webbplatser, hur många som används aktivt och hur mycket lagringsutrymme som används totalt.
ms.openlocfilehash: 62bf01c867b7e9217d25e655af6633a72773caa1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241874"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Rapporter i administrationscentret – SharePoint webbplatsanvändning

Som Microsoft 365 administratör kan du **i instrumentpanelen** Rapporter se en översikt över aktiviteter i olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Du kan till exempel få en överblick på hög nivå av det värde som du får från SharePoint som det totala antalet filer som användare lagrar på SharePoint-webbplatser, hur många filer som används aktivt och hur mycket lagring som används på alla dessa webbplatser. Du kan sedan öka detaljnivån på rapporten om SharePoint-webbplatsanvändningen för att förstå trenderna och information per webbplatsnivå för alla webbplatser. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.
Microsoft 365 Rapporter i administrationscentret stöds inte för klientorganisationen GCC Hög och DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Så här kommer du till rapporten om SharePoint-webbplatsanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på SharePoint kort.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Tolka rapporten SharePoint för webbplatsanvändning

Du kan visa webbplatsanvändningen i SharePoint genom att välja **fliken Webbplatsanvändning.**<br/>![Microsoft 365 – Microsoft SharePoint webbplatsanvändningsrapport.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![SharePoint webbplatsanvändning – välj kolumner](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Webbplats-URL  <br/> |Den fullständiga URL:en för webbplatsen. <br/> |
|Borttagen  <br/> |Borttagningsstatus för webbplatsen. Det tar minst 7 dagar för webbplatser att markeras som borttagna.  <br/> |
|Webbplatsägare  <br/> |Användarnamnet för den primära ägaren av webbplatsen.   <br/> |
|Huvudnamn för webbplatsägare  <br/> |E-postadressen till webbplatsens ägare. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Datumet för den senaste gången filaktivitet upptäcktes eller en sida visades på webbplatsen.  <br/> |
|Känslighets-ID för webbplatsen  <br/> | Känslighetsetiketten på webbplatsen.  <br/> |
|Extern delning  <br/> | De externa inställningar som kan delas på webbplatsen.  <br/> |
|Princip för ohanterad enhet  <br/> | Principen för webbplatsåtkomst för ohanterade enheter.  <br/> |
|Geoplats  <br/> | Webbplatsens geoplats.  <br/> |
|Filer  <br/> |Antalet filer på webbplatsen. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer på webbplatsen.<br/> Obs! Om du tog bort filer under den angivna tidsperioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på webbplatsen.  <br/> |
|Storage (MB)  <br/> |Det lagringsutrymme som för närvarande används på webbplatsen.  <br/>|
|Storage allokerat (MB)  <br/> |Den maximala mängden lagringsutrymme som tilldelats för webbplatsen.  <br/>|
|Sidvyer  <br/> |Antalet gånger sidor har visats på webbplatsen.  <br/>|
|Besökta sidor  <br/> |Antalet unika sidor som besökts på webbplatsen.  <br/>|
|Anonymt antal länkar  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "Alla som har länken" på webbplatsen.  <br/>|
|Antal företagslänk  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "Personer i organisation med länken" på webbplatsen.  <br/>|
|Säker länk för gästantal  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "vissa personer" på webbplatsen.  <br/>|
|Säker länk för medlemsantal  <br/> |Antalet gånger dokument eller mappar delas med hjälp av "vissa personer" på webbplatsen.  <br/>|
|Rotwebbmall  <br/> |Den mall som användes för att skapa webbplatsen.  <br/> Obs! Om du vill filtrera data efter olika webbplatstyper exporterar du dessa data och använder kolumnen Rotwebbmall. |
|||