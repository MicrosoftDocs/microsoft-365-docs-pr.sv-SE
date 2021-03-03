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
ms.openlocfilehash: 41403bcda1d1485798ac5eefe8f3386a314aea1b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406188"
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

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

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
|Ad hoc-möten som deltagare   <br/> | Antalet ad hoc-möten som en användare har deltagit i under den angivna tidsperioden.  <br/> |
|Möten organiserade ad hoc <br/> |Antalet ad hoc-möten som en användare organiserat under den angivna tidsperioden. <br/>|
|Totalt antal ordnade möten  <br/> |Summan av enplanerade, återkommande, ad hoc- och oklassificerade möten som en användare organiserat under den angivna tidsperioden.  <br/> |
|Totalt antal möten som deltagare  <br/> |Summan av engångs schemalagda, återkommande, ad hoc- och oklassificerade möten som en användare deltagit i under den angivna tidsperioden.  <br/> |
|Möten som schemalagts en gång  <br/> |Antalet tidsbokade möten som en användare organiserat under den angivna tidsperioden.  <br/> |
|Schemalagda återkommande möten  <br/> |Antalet återkommande möten som en användare organiserat under den angivna tidsperioden.  <br/> |
|Möten som deltagare har schemalagts en gång  <br/> |Antalet schemalagda möten som en användare har deltagit i under den angivna tidsperioden.  <br/> |
|Möten som har deltagit i schemalagda återkommande möten  <br/> |Antalet återkommande möten som en användare har deltagit i under den angivna tidsperioden.  <br/> |
|Är licensierad  <br/> |Väljs om användaren är licensierad att använda Teams. <br/>|
|Annan aktivitet  <br/>|Användaren är aktiv men har utfört andra aktiviteter än de åtgärdstyper som exponeras som erbjuds i rapporten (skicka eller svara på kanalmeddelanden och chattmeddelanden, schemalägga eller delta i 1:1-samtal och möten). Exempelåtgärder är när en användare ändrar Teams status eller Teams statusmeddelande eller öppnar ett kanalmeddelandeinlägg men inte svarar.  <br/>|
|oklassificerade möten <br/>|Den som inte kan klassificeras som schema eller återkommande eller ad hoc. De är korta och kan för det mesta inte identifieras på grund av manipulerad telemetriinformation. |
|||