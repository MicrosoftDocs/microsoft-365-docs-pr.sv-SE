---
title: Microsoft 365-rapporter i administrations Center – användar aktivitet för Microsoft Teams
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
description: Lär dig hur du hämtar användar aktivitets rapporten för Microsoft Teams och få insikter om Teams-aktiviteten i din organisation.
ms.openlocfilehash: 7e32ca6b665cab9da93dec9632ef25176db0e839
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611406"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporter i administrations Center – användar aktivitet för Microsoft Teams

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Så här visar du användaraktivitetsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på aktivitets kortet för Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för Microsoft Teams

Du kan visa användar aktiviteten i Teams-rapporten genom att välja fliken **användar aktivitet** . <br/>![Microsoft 365-rapporter – användar aktivitet för Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. Det exporterade formatet för **ljud tids**-, **video**-och **skärm delnings tid** följer iso8601.

För att säkerställa data kvaliteten utför vi dagliga data verifierings kontroller för de senaste tre dagarna och fyller eventuella luckor som upptäcks. Du kan lägga märke till skillnader i historiska data under processen.

|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Användar namn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.   <br/> |
|Kanal meddelanden   <br/> |Antalet unika meddelanden som användaren har publicerat under den angivna tids perioden.  <br/> |
|Chatta   <br/> |Antalet unika meddelanden som användaren publicerat i en privat chatt under den angivna tids perioden.  <br/> |
|Totalt antal möten   <br/> |Antalet onlinemöten som användaren deltog i under den angivna tids perioden.  <br/> |
|1:1-samtal   <br/> | Antalet 1:1-samtal som användaren deltog i under den angivna tids perioden.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det sista datum som användaren deltog i en Microsoft Teams-aktivitet.<br/> |
|Möten deltog i adhoc   <br/> | Antalet möten som inte har schemalagts i den kalender som användaren deltog i under den angivna tids perioden.  <br/> |
|Möten organiserade adhoc <br/> |Antalet möten som inte har schemalagts i den kalender som användaren organiserade under den angivna tids perioden. <br/>|
|Schemalagda möten  <br/> |Antalet schemalagda möten som en användare organiserat under den angivna tids perioden.  <br/> |
|Är licensierad |Markerad om användaren är licensierad för att använda Teams.|
|Annan aktivitet|Användaren är aktiv men har gjort andra aktiviteter än utsatta åtgärds typer i rapporten (skickar eller svarar på kanal meddelanden och chattar, schemalägger eller deltar i 1:1-samtal och-möten). Exempel på åtgärder är när en användare ändrar team status eller team status meddelandet eller öppnar ett meddelande inlägg, men som inte svarar. |
|||