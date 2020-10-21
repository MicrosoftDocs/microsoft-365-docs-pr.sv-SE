---
title: Microsoft 365-rapporter i administrations Center – OneDrive för företag-aktivitet
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
description: Hämta rapporten för OneDrive-användning för din organisation och få aktiviteten för varje OneDrive-användare, antalet delade filer och lagrings användningen.
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649866"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-rapporter i administrations Center – OneDrive för företag-aktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få mer ingående förståelse för aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för var och en av de användare som har en licens för att använda SharePoint genom att titta på hans eller hennes interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp att förstå samarbetsnivån.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på OneDrive-kortet.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Förstå aktivitetsrapporten i OneDrive för företag

Du kan visa aktiviteterna i OneDrive-rapporten genom att välja fliken **aktivitet** .<br/>![Microsoft 365-rapporter – aktivitets rapport för Microsoft OneDrive.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Aktivitets rapport för OneDrive – Välj kolumner](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Användarnamn  <br/> |Användar namnet för ägaren av OneDrive-kontot.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en fil aktivitet utfördes på OneDrive-kontot för det valda datum intervallet. . Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> |
|Filer som visats eller redigerats  <br/> |Antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.   <br/> |
|Filer har synkroniserats  <br/> |Antalet filer som har synkroniserats från en användares lokala enhet till OneDrive-kontot. <br/> |
|Filer som delas internt  <br/> | Antalet filer som har delats med användare inom organisationen eller med användare inom grupper (som kan innehålla externa användare).  <br/> |
|Filer som delas externt  <br/> |Antalet filer som har delats med användare utanför organisationen. <br/>|
|Deleted  <br/> | Detta anger att användarens licens har tagits bort.  <br/> Obs! aktiviteten för en borttagen användare visas fortfarande i en rapport så länge han eller hon har licensierats vid ett visst tillfälle under den valda tids perioden. I kolumnen **Borttagen** får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.  <br/> |
|Borttaget den  <br/> |Det datum då användarens licens togs bort. <br/>|
|Tilldelad produkt  <br/> |De Microsoft 365-produkter som är licensierade till användaren.|
|||