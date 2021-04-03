---
title: Microsoft 365-rapporter i administrationscentret – OneDrive för företag-aktivitet
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Hämta användningsrapporten för OneDrive för organisationen och få information om aktiviteten för varje OneDrive-användare, antalet delade filer och lagringsutnyttjandet.
ms.openlocfilehash: 7b6173b3a86187e4612aaaa51bafbfbe965a6cfa
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579536"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-rapporter i administrationscentret – OneDrive för företag-aktivitet

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få mer ingående förståelse för aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för var och en av de användare som har en licens för att använda SharePoint genom att titta på hans eller hennes interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp att förstå samarbetsnivån.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på OneDrive-kortet.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Förstå aktivitetsrapporten i OneDrive för företag

Du kan visa aktiviteterna i OneDrive-rapporten genom att välja **fliken** Aktivitet.<br/>![Microsoft 365-rapporter – Microsoft OneDrive-aktivitetsrapport.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![OneDrive-aktivitetsrapport – välj kolumner](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |Användarnamnet på ägaren av OneDrive-kontot.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en filaktivitet utfördes på OneDrive-kontot för det valda datumintervallet. . Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> |
|Visade eller redigerade filer  <br/> |Antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.   <br/> |
|Filer synkroniserade  <br/> |Antalet filer som har synkroniserats från en användares lokala enhet till OneDrive-kontot. <br/> |
|Filer som delats internt  <br/> | Antalet filer som har delats med användare inom organisationen eller med användare i grupper (som kan omfatta externa användare).  <br/> |
|Filer som delats externt  <br/> |Antalet filer som har delats med användare utanför organisationen. <br/>|
|Borttagen  <br/> | Det här anger att användarens licens har tagits bort.  <br/> Obs! Aktivitet för en borttagna användare visas fortfarande i en rapport om han eller hon har licensieras någon gång under den valda tidsperioden. I kolumnen **Borttagen** får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.  <br/> |
|Borttagna datum  <br/> |Datumet då användarens licens togs bort. <br/>|
|Tilldelad produkt  <br/> |De Microsoft 365-produkter som är licensierade till användaren.|
|||