---
title: Microsoft 365-rapporter i administrationscentret – användaraktivitet för Microsoft Teams
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Lär dig hur du får användaraktivitetsrapporten för Microsoft Teams och får inblick i Teams-aktiviteten i din organisation.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233416"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporter i administrationscentret – användaraktivitet för Microsoft Teams

Instrumentpanelen Microsoft **365-rapporter** visar en översikt över aktiviteter för produkter i din organisation. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Så här visar du användaraktivitetsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.
2. På startsidan för instrumentpanelen klickar du på **knappen Visa mer** på Microsoft Teams aktivitetskort.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för Microsoft Teams

Du kan visa användaraktiviteten i Teams-rapporten genom att välja **fliken Användaraktivitet.** <br/>![Microsoft 365-rapporter – användaraktivitet för Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Du kan också exportera rapportdata till en CSV-fil för Excel genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. Det exporterade formatet för **ljudtid,** **videotid och** **skärmresurstid** följer ISO8601-formatet för varaktighet.

I rapporten **Microsoft Teams användaraktivitet** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).

För att säkerställa datakvaliteten utför vi dagliga dataverifieringskontroller under de senaste tre dagarna och kommer att fylla i eventuella luckor som upptäckts. Du kanske märker skillnader i historiska data under processen.

|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.   <br/> |
|Kanalmeddelanden   <br/> |Antalet unika meddelanden som användaren publicerat i en teamchatt under den angivna tidsperioden.  <br/> |
|Chattmeddelanden   <br/> |Antalet unika meddelanden som användaren publicerat i en privat chatt under den angivna tidsperioden.  <br/> |
|Totalt antal möten   <br/> |Antalet onlinemöten som användaren har deltagit i under den angivna tidsperioden.  <br/> |
|1:1-samtal   <br/> | Antalet 1:1-anrop som användaren har deltagit i under den angivna tidsperioden.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då användaren deltog i en Microsoft Teams-aktivitet.<br/> |
|Adhoc för möten som deltagare   <br/> | Antalet möten som inte har schemalagts i kalendern som användaren har deltagit i under den angivna tidsperioden.  <br/> |
|Möten organiserade adhoc <br/> |Antalet möten som inte har schemalagts i kalendern som användaren organiserat under den angivna tidsperioden. <br/>|
|Schemalagda möten  <br/> |Antalet schemalagda möten som en användare organiserat under den angivna tidsperioden.  <br/> |
|Är licensierad |Väljs om användaren är licensierad att använda Teams.|
|Annan aktivitet|Användaren är aktiv men har utfört andra aktiviteter än de åtgärdstyper som exponeras som erbjuds i rapporten (skicka eller svara på kanalmeddelanden och chattmeddelanden, schemalägga eller delta i 1:1-samtal och möten). Exempelåtgärder är när en användare ändrar Teams status eller Teams statusmeddelande eller öppnar ett kanalmeddelandeinlägg men inte svarar. |
|||