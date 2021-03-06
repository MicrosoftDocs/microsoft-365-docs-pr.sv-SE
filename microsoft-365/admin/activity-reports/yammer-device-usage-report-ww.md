---
title: Microsoft 365 Rapporter i administrationscentret – rapporten Yammer om enhetsanvändning
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
description: Hämta rapporten Yammer om enhetsanvändning om du vill veta vilka enheter användarna använder Yammer på.
ms.openlocfilehash: 817627cac791d35f49cd240ceb48de15ef328ef8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241850"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365 Rapporter i administrationscentret – rapporten Yammer om enhetsanvändning

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
I rapporten om användning av Yammer på enheter hittar du information om vilka enheter användarna använder Yammer på. Du kan visa antalet dagliga användare efter enhetstyp och antalet användare efter enhetstyp. Båda går att visa för en viss tidsperiod. Du kan också visa detaljerad information per användare.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Hur får jag fram rapporten om användning av Yammer på enheter?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på Yammer kort.
  
## <a name="interpret-the-yammer-device-usage-report"></a>Tolka rapporten Yammer över enhetsanvändning

Du kan visa användningen i OneDrive genom att välja **fliken Enhetsanvändning.**<br/>![Microsoft 365 – Microsoft Yammer om enhetsanvändning.](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Yammer om enhetsanvändning – välj kolumner](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. I det här rutnätet visas användare som loggat in Yammer med det Microsoft 365-kontot eller som loggat in på nätverket med enkel inloggning. <br/> |
|Visningsnamn  <br/> |Användarens fullständiga namn. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> |
|Användartillstånd  <br/> |Ett av tre värden: Aktiv, Borttagna eller Inaktiverad. De här rapporterna visar data för aktiva, inaktiverade och borttagna användare. De avspeglar inte väntande användare eftersom väntande användare inte kan publicera, läsa eller gilla ett meddelande.   <br/> |
|Datum för tillståndsändring (UTC)  <br/> |Datumet då användarens status ändrades i Yammer.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum (UTC) då användaren deltog i en Yammer aktivitet.  <br/> |
|Webb  <br/> |Anger om användaren har använt Yammer på webben.  <br/> |
|Windows telefon  <br/> | Anger om användaren har använt en Yammer på en Windows telefon.  <br/> |
|Android-telefon  <br/> |Anger om användaren har använt en Yammer på en Android-telefon. <br/>|
|iphone <br/> | Anger om användaren har använt Yammer på en iPhone.  <br/> |
|ipad  <br/> |Anger om användaren har använt Yammer på ett iPad. <br/>|
|annat  <br/> |Anger om användaren har använt en Yammer annan enhet, inte tidigare listad. <br/>|
|||