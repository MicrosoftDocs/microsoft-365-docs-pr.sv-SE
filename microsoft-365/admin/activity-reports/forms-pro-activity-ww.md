---
title: Microsoft 365 Rapporter i administrationscentret – Dynamics 365-kundröstaktivitet
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
description: Lär dig hur du får en Microsoft Dynamics 365 Customer Voice-aktivitetsrapport med hjälp Microsoft 365 instrumentpanelen Rapporter i Microsoft 365 administrationscenter.
ms.openlocfilehash: 7975db1f3681ab0823e222f017f6addb514dafd7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242066"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 Rapporter i administrationscentret – Dynamics 365-kundröstaktivitet

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få mer ingående förståelse för aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda Microsoft Dynamics 365 Customer Voice genom att titta på deras interaktioner med Dynamics 365 Customer Voice. Det hjälper dig också att förstå samarbetsnivån genom att titta på antalet undersökningar som Pro har skapats och Pro Undersökningar som användarna har svarat på. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>Så här kommer du till Dynamics 365 Customer Voice-aktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa mer** på Dynamics 365 Customer Voice-kortet.
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Tolka dynamics 365-kundröstaktivitetsrapporten

Du kan visa aktiviteterna i Dynamics 365 Customer Voice-rapporten genom att välja **fliken** Aktivitet.<br/>![Microsoft 365 – Microsoft Dynamics 365 Customer Voice-aktivitetsrapport.](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Dynamics 365 Customer Voice-aktivitetsrapport – välj kolumner](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |E-postadressen för den användare som utförde aktiviteten på Microsoft Forms.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då en formuläraktivitet utfördes av användaren för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/>Då filtreras tabellen så att data för filaktivitet endast visas för användare som utförde aktiviteten på den specifika dagen.  <br/> |
|Antal undersökningar som skapats  <br/> |Antalet undersökningar som användaren har skapat.   <br/> |
|Antal undersökningssvar  <br/> |Antalet svar från svarare som undersökningen har distribuerats till.|
|||