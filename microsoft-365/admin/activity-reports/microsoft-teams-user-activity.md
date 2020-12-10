---
title: Microsoft 365-rapporter i administrations Center – användar aktivitet för Microsoft Teams
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Lär dig hur du hämtar användar aktivitets rapporten för Microsoft Teams och få insikter om Teams-aktiviteten i din organisation.
ms.openlocfilehash: b2b01371872d0a4b2ebbfb6b011cf8bd4299a90b
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611382"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporter i administrations Center – användar aktivitet för Microsoft Teams

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Så här visar du användaraktivitetsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du **Microsoft Teams** \> **användar aktivitet**.
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för Microsoft Teams

Du kan få inblick i användarnas Microsoft Teams-aktivitet genom att titta på diagrammen **Aktivitet** och **Användare**.<br/>![Microsoft 365-rapporter – användar aktivitet för Microsoft Teams.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft Teams användaraktivitet** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |För att säkerställa data kvaliteten utför vi dagliga data verifierings kontroller under de senaste fem dagarna och fyller eventuella luckor som upptäcks. Du kan lägga märke till skillnader i historiska data under processen.  <br/> |
|4.  <br/> |I vyn **Aktivitet** visas antalet Microsoft Teams-aktiviteter per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|5.  <br/> |I vyn **Användare** visas antalet användare per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|18.6.  <br/> | I diagrammet **aktivitet** är Y-axeln antalet angivna aktiviteter.  <br/>  I diagrammet **filer** är Y-axeln antalet användare som deltar i gruppchatt, privata chattar, samtal och möten.  <br/>  X-axeln i diagrammen är det valda datum intervallet för den specifika rapporten.  <br/> |
|borttagning.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **aktivitet** väljer du till exempel **kanal meddelanden**, **chattar**, **samtal** eller **möten** för att bara se informationen som hör till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> ![Filtrera aktivitets diagram för Microsoft Teams](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.2.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längsta (180 dagar) rapportperioden. Antal aktiviteter varierar beroende på vilka datum som väljs.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> **Datum för senaste aktivitet (UTC)** anger det senaste datum då användaren deltog i en Microsoft Teams-aktivitet.  <br/> **Kanalmeddelanden** är antalet unika meddelanden som användaren publicerat i en teamchatt under den angivna tidsperioden.  <br/> **Chattmeddelanden** är antalet unika meddelanden som användaren publicerat i en privat chatt under den angivna tidsperioden.  <br/> **Samtal** är antalet samtal som användaren har deltagit i under den angivna tidsperioden.  <br/> **Möten** är antalet onlinemöten som användaren har deltagit i under den angivna tidsperioden.  <br/> **Annan aktivitet** är antalet andra teamaktiviteter som användaren har använt.  <br/> **Borttagen** anger om teamet har tagits bort. Om teamet har tagits bort, men det förekom aktiviteter under rapporteringsperioden visas det i tabellen med alternativet Borttagen angett till Sant.  <br/> **Borttaget datum** är det datum då teamet togs bort.  <br/> **Tilldelad produkt** är en lista över de produkter som har tilldelats användaren.  <br/>  Om organisationens principer hindrar dig från att visa rapporter där användar information är identifierbar kan du ändra sekretess inställningen för alla dessa rapporter. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Välj **kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.3.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

