---
title: Microsoft 365-rapporter i administrations centret – Yammer-aktivitet
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
description: Få en rapport över Yammer-aktiviteter och lär dig mer om antalet användare som använder Yammer för att publicera, gilla eller läsa ett meddelande.
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779411"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365-rapporter i administrations centret – Yammer-aktivitet

Som Microsoft 365-administratör kan du använda **rapport** instrument panelen för att visa information om användningen av produkterna i din organisation. Kolla [in aktivitets rapporter i administrations centret](activity-reports.md). Med **Yammer-aktivitetsrapporten** får du förståelse för användningen av Yammer i organisationen genom att titta på antalet unika användare som använder Yammer för att publicera, gilla eller läsa ett meddelande och graden av aktivitet som skapas i organisationen. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Hur kommer jag till rapporten aktivitets rapport för Yammer?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på Yammer-kortet.

  
## <a name="interpret-the-yammer-activity-report"></a>Tolka Yammer-aktivitetsrapporten

Du kan visa aktiviteterna i Yammer-rapporten genom att välja fliken **aktivitet** .<br/>![Microsoft 365-rapporter – aktivitets rapport i Microsoft Yammer.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Yammer-aktivitets rapport – Välj kolumner](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Användarnamn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. I det här rutnätet visas användare som är inloggade på Yammer med hjälp av Microsoft 365-kontot eller som är inloggad i nätverket med enkel inloggning. <br/> |
|Visningsnamn  <br/> |Användarens fullständiga namn. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> |
|Användar tillstånd  <br/> |Ett av tre värden: aktive rad, borttagen eller upphävd. De här rapporterna visar data för aktiva, inaktiverade och borttagna användare. De avspeglar inte väntande användare eftersom väntande användare inte kan publicera, läsa eller gilla ett meddelande.  <br/> |
|Status ändrings datum (UTC)  <br/> |Det datum då användarens tillstånd ändrades i Yammer.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Det sista datumet då användaren publicerade, läst eller gillat ett meddelande.  <br/> |
|Skickats  <br/> |Antalet meddelanden användaren skickade under den angivna tids perioden. <br/>|
|Läsa  <br/> |Antalet konversationer som användaren läst under den angivna tids perioden.  <br/> |
|Gillat  <br/> |Antalet meddelanden som användaren gillat under den angivna tids perioden.  <br/>|
|Tilldelad produkt  <br/> |Produkter som har tilldelats till den här användaren.|
|||