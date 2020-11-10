---
title: Microsoft 365-rapporter i administrations centret – Dynamics 365 kund röst aktivitet
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
description: Lär dig hur du skaffar en Microsoft Dynamics 365 Customer Voice Activity-rapport med hjälp av instrument panelen för Microsoft 365-rapporter i Microsoft 365 Admin Center.
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989019"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-rapporter i administrations centret – Dynamics 365 kund röst aktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få mer ingående förståelse för aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för rapporter](activity-reports.md).
  
Du kan till exempel förstå aktiviteten hos alla användare som har licens att använda Microsoft Dynamics 365 Customer Voice genom att titta på deras interaktioner med Dynamics 365 Customer Voice. Det hjälper dig också att förstå samarbetets möjligheter genom att titta på antalet Pro-undersökningar som skapats och Pro-undersökningar som användarna svarade på. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Så här kommer du till rapporten Dynamics 365 Customer Voice Activity

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på kortet Dynamics 365 Customer Voice.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Tolka rapporten Dynamics 365 Customer Voice Activity

Du kan visa aktiviteterna i röst rapporteringen för Dynamics 365 Customer genom att välja fliken **aktivitet** .<br/>![Microsoft 365-rapporter – rapport om kund röst aktivitet i Microsoft Dynamics 365](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport om Dynamics 365 Customer Voice Activity – Välj kolumner](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Användarnamn  <br/> |E-postadressen för den användare som utförde aktiviteten på Microsoft Forms.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en formulär aktivitet utfördes av användaren för det valda datum intervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/>Då filtreras tabellen för att endast Visa fil aktiviteter för användare som utförde aktiviteten på den aktuella dagen.  <br/> |
|Antal undersökningar som har skapats  <br/> |Antalet undersökningar som användaren har skapat.   <br/> |
|Antal undersöknings svar  <br/> |Antalet svar från svarare som undersökningen distribuerades till.|
|||