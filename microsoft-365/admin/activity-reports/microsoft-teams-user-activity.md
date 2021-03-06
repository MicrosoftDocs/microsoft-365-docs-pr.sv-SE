---
title: Microsoft 365 i administrationscentret – Microsoft Teams användaraktivitet
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
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Lär dig hur du får Microsoft Teams av användaraktivitetsrapporten och får inblick i Teams aktivitet i organisationen.
ms.openlocfilehash: c824a0ce285a085c9ae8b7326647ad4bcdf5f013
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924273"
---
# <a name="microsoft-365-admin-center-reports---microsoft-teams-user-activity"></a>Microsoft 365 i administrationscentret – Microsoft Teams användaraktivitet

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Så här visar du användaraktivitetsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I **listrutan Välj en** rapport väljer **du** Microsoft Teams \> **Användaraktivitet**.
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för Microsoft Teams

Du kan få inblick i användarnas Microsoft Teams-aktivitet genom att titta på diagrammen **Aktivitet** och **Användare**.<br/>![Microsoft 365 – Microsoft Teams användaraktivitet.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft Teams användaraktivitet** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |För att säkerställa datakvaliteten utför vi dagliga dataverifieringskontroller under de senaste fem dagarna och kommer att fylla eventuella luckor som upptäckts. Du kanske märker skillnader i historiska data under processen.  <br/> |
|4.  <br/> |I vyn **Aktivitet** visas antalet Microsoft Teams-aktiviteter per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|5.  <br/> |I vyn **Användare** visas antalet användare per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|6.  <br/> | I diagrammet **Aktivitet** är Y-axeln antalet för den angivna aktiviteten.  <br/>  I diagrammet **Filer** visar Y-axeln antalet användare som deltar i teamchattar, privata chattar, samtal eller möten.  <br/>  X-axeln i diagrammen är det valda datumintervallet för den specifika rapporten.  <br/> |
|7.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Aktivitet väljer du **till** exempel Kanalmeddelanden,  **Chattmeddelanden,** Samtal eller Möten om du bara vill se den relaterade informationen.   När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> ![Filtrera Microsoft Teams aktivitetsscheman](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längsta (180 dagar) rapportperioden. Antal aktiviteter varierar beroende på vilka datum som väljs.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> **Datum för senaste aktivitet (UTC)** anger det senaste datum då användaren deltog i en Microsoft Teams-aktivitet.  <br/> **Kanalmeddelanden** är antalet unika meddelanden som användaren publicerat i en teamchatt under den angivna tidsperioden.  <br/> **Chattmeddelanden** är antalet unika meddelanden som användaren publicerat i en privat chatt under den angivna tidsperioden.  <br/> **Samtal** är antalet samtal som användaren har deltagit i under den angivna tidsperioden.  <br/> **Möten** är antalet onlinemöten som användaren har deltagit i under den angivna tidsperioden.  <br/> **Annan aktivitet** är antalet andra teamaktiviteter som användaren har använt.  <br/> **Borttagen** anger om teamet har tagits bort. Om teamet har tagits bort, men det förekom aktiviteter under rapporteringsperioden visas det i tabellen med alternativet Borttagen angett till Sant.  <br/> **Borttaget datum** är det datum då teamet togs bort.  <br/> **Tilldelad produkt** är en lista över de produkter som har tilldelats användaren.  <br/>  Om organisationens principer hindrar dig från att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information **finns i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i Microsoft 365 administrationscenter](activity-reports.md).  <br/> |
|9.  <br/> |Välj **Kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

