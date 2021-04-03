---
title: Microsoft 365-rapporter i administrationscentret – Yammer-aktivitetsrapport
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
description: Hämta Yammer-aktivitetsrapporten och få mer information om antalet användare som använder Yammer för att publicera, gilla eller läsa ett meddelande.
ms.openlocfilehash: 636e5fae9a71fc819a032743e06127dace25f0a4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579500"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365-rapporter i administrationscentret – Yammer-aktivitetsrapport

Som Microsoft 365-administratör kan **du i** instrumentpanelen Rapporter se data om användningen av produkter inom organisationen. Titta i [aktivitetsrapporter i administrationscentret](activity-reports.md). Med **Yammer-aktivitetsrapporten** får du förståelse för användningen av Yammer i organisationen genom att titta på antalet unika användare som använder Yammer för att publicera, gilla eller läsa ett meddelande och graden av aktivitet som skapas i organisationen. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Hur kommer jag åt Yammer-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på Yammer-kortet.

  
## <a name="interpret-the-yammer-activity-report"></a>Tolka Yammer-aktivitetsrapporten

Du kan visa aktiviteterna i Yammer-rapporten genom att välja **fliken** Aktivitet.<br/>![Microsoft 365-rapporter – Microsoft Yammer-aktivitetsrapport.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Yammer-aktivitetsrapport – välj kolumner](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. I det här rutnätet visas användare som loggat in på Yammer med Microsoft 365-kontot eller som loggat in på nätverket med enkel inloggning. <br/> |
|Visningsnamn  <br/> |Användarens fullständiga namn. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> |
|Användartillstånd  <br/> |Ett av tre värden: Aktiverad, Borttagna eller Inaktiverade. De här rapporterna visar data för aktiva, inaktiverade och borttagna användare. De avspeglar inte väntande användare eftersom väntande användare inte kan publicera, läsa eller gilla ett meddelande.  <br/> |
|Datum för tillståndsändring (UTC)  <br/> |Datumet då användarens status ändrades i Yammer.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Det senaste datum då användaren publicerade, läste eller gillade ett meddelande.  <br/> |
|Publicerad  <br/> |Antalet meddelanden som användaren publicerat under den angivna tidsperioden. <br/>|
|Läsa  <br/> |Antalet konversationer som användaren läst under den angivna tidsperioden.  <br/> |
|Gillade  <br/> |Antalet meddelanden som användaren gillat under den angivna tidsperioden.  <br/>|
|Tilldelad produkt  <br/> |Produkterna som är tilldelade till den här användaren.|
|||