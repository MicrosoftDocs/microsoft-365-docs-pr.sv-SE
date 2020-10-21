---
title: Microsoft 365-rapporter i administrations centret – SharePoint-aktivitet
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
description: Hämta rapporten för SharePoint-aktivitets användning om du vill veta mer om aktiviteten för varje SharePoint-användare, antalet delade filer och lagrings användningen.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649878"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-rapporter i administrations centret – SharePoint-aktivitet

Som Microsoft 365-administratör visar instrument panelen **rapporter** dig översikten över olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Ta en titt på [aktivitets rapporterna i administrations centret för Microsoft 365](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda SharePoint genom att titta på deras interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp med att förstå samarbetsnivån.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hur kommer jag åt SharePoint-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på SharePoint-kortet.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Tolka rapport om SharePoint-aktivitet

Du kan visa aktiviteterna i SharePoint-rapporten genom att välja fliken **aktivitet** .<br/>![Microsoft 365-rapporter – aktivitets rapport för Microsoft SharePoint.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![SharePoint-aktivitets rapport – Välj kolumner](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Användarnamn  <br/> |E-postadressen för den användare som utförde aktiviteten på SharePoint-webbplatsen.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en fil aktivitet utfördes eller en sida har besökts för det valda datum intervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> |
|Filer som visats eller redigerats  <br/> |Antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.   <br/> |
|Filer har synkroniserats  <br/> |Antalet filer som har synkroniserats från en användares lokala enhet till SharePoint-webbplatsen. <br/> |
|Filer som delas internt  <br/> | Antalet filer som har delats med användare inom organisationen eller med användare inom grupper (som kan omfatta externa användare).  <br/> |
|Filer som delas externt  <br/> |Antalet filer som har delats med användare utanför organisationen. <br/>|
|Besökta sidor  <br/> |Besök på unika sidor av användaren. <br/>|
|Deleted  <br/> | Detta anger att användarens licens har tagits bort.  <br/>  **Obs!** Aktiviteten för en borttagen användare visas fortfarande i rapporten så länge han eller hon har licensierats vid ett visst tillfälle under den valda tids perioden. I kolumnen Borttagen får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.  <br/> |
|Borttaget den  <br/> |Det datum då användarens licens togs bort. <br/>|
|Tilldelad produkt  <br/> |De Microsoft 365-produkter som är licensierade till användaren.|
|||