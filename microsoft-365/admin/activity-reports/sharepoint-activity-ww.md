---
title: Microsoft 365 Rapporter i administrationscentret – SharePoint aktivitet
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
description: Få rapporten SharePoint användningsaktivitet för att få information om aktiviteten för varje användare SharePoint, antalet delade filer och lagringsutnyttjandet.
ms.openlocfilehash: f049a67e8444654e05cfe3dc72a8d4fe39792cb2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244086"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365 Rapporter i administrationscentret – SharePoint aktivitet

Som Microsoft 365 administratör kan du **i instrumentpanelen** Rapporter se en översikt över olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Titta i [aktivitetsrapporterna i Microsoft 365 administrationscenter.](activity-reports.md)
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda SharePoint genom att titta på deras interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp med att förstå samarbetsnivån.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hur kommer jag åt SharePoint-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på SharePoint kort.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Tolka SharePoint aktivitetsrapport

Du kan visa aktiviteterna i SharePoint genom att välja **fliken** Aktivitet.<br/>![Microsoft 365 – Microsoft SharePoint aktivitetsrapport.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![SharePoint aktivitetsrapport – välj kolumner](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |E-postadressen till den användare som utförde aktiviteten på SharePoint webbplats.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en filaktivitet utfördes eller en sida besöktes för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> |
|Visade eller redigerade filer  <br/> |Antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.   <br/> |
|Filer synkroniserade  <br/> |Antalet filer som har synkroniserats från en användares lokala enhet till SharePoint webbplats. <br/> |
|Filer som delats internt  <br/> | Antalet filer som har delats med användare inom organisationen eller med användare i grupper (som kan innehålla externa användare).  <br/> |
|Filer som delats externt  <br/> |Antalet filer som har delats med användare utanför organisationen. <br/>|
|Besökta sidor  <br/> |Besök på unika sidor av användaren. <br/>|
|Borttagen  <br/> | Det här anger att användarens licens har tagits bort.  <br/>  **OBS!** Aktivitet för en borttagna användare visas fortfarande i rapporten om han eller hon har varit licensierad någon gång under den valda tidsperioden. I kolumnen Borttagen får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.  <br/> |
|Borttagna datum  <br/> |Datumet då användarens licens togs bort. <br/>|
|Tilldelad produkt  <br/> |Den Microsoft 365 produkter som är licensierade till användaren.|
|||