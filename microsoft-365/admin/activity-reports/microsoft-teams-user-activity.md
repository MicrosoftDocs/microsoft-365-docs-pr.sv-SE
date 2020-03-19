---
title: Microsoft 365-rapporter i administrationscentret – Användaraktivitet för Microsoft Teams
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Läs om hur du får användaraktivitetsrapporten för Microsoft Teams och få insikter i teams-aktiviteten i organisationen.
ms.openlocfilehash: 53c3da2d563363c7c463abc62f7cdf4b478ccecc
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809738"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporter i administrationscentret – Användaraktivitet för Microsoft Teams

Instrumentpanelen för Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara en global administratör, global läsare eller rapporterar läsare i Microsoft 365 eller en Exchange-, SharePoint- eller Skype förföretag-administratör för att kunna se rapporter. 
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Så här visar du användaraktivitetsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **Microsoft Teams** \> **User-aktivitet**i listrutan Välj en **rapport** .
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för Microsoft Teams

Du kan få inblick i användarnas Microsoft Teams-aktivitet genom att titta på diagrammen **Aktivitet** och **Användare**.<br/>![Microsoft 365 rapporter - Microsoft Teams användaraktivitet.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|||
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft Teams användaraktivitet** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas dock data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |I vyn **Aktivitet** visas antalet Microsoft Teams-aktiviteter per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|4.  <br/> |I vyn **Användare** visas antalet användare per aktivitetstyp. Aktivitetstyperna är chattmeddelanden för team, privata chattmeddelanden, samtal och möten.  <br/> |
|5.  <br/> | I diagrammet **Aktivitet** visar Y-axeln antalet för den angivna aktiviteten.  <br/>  I diagrammet **Filer** visar Y-axeln antalet användare som deltagit i teamchattar, privata chattar, samtal eller möten.  <br/>  X-axeln i diagrammen visar det valda datumintervallet för den specifika rapporten.  <br/> |
|6.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I **aktivitetsdiagrammet** väljer du till exempel **Kanalmeddelanden,** **chattmeddelanden,** **samtal**eller **Möten** om du bara vill se informationen som är relaterad till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> ![Filtrera aktivitetsdiagrammen för Microsoft Teams](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|7.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längsta (180 dagar) rapportperioden. Antal aktiviteter varierar beroende på vilka datum som väljs.  <br/> Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> **Datum för senaste aktivitet (UTC)** anger det senaste datum då användaren deltog i en Microsoft Teams-aktivitet.  <br/> **Kanalmeddelanden** är antalet unika meddelanden som användaren publicerat i en teamchatt under den angivna tidsperioden.  <br/> **Chattmeddelanden** är antalet unika meddelanden som användaren publicerat i en privat chatt under den angivna tidsperioden.  <br/> **Samtal** är antalet samtal som användaren har deltagit i under den angivna tidsperioden.  <br/> **Möten** är antalet onlinemöten som användaren har deltagit i under den angivna tidsperioden.  <br/> **Annan aktivitet** är antalet andra teamaktiviteter som användaren har använt.  <br/> **Borttagen** anger om teamet har tagits bort. Om teamet har tagits bort, men det förekom aktiviteter under rapporteringsperioden visas det i tabellen med alternativet Borttagen angett till Sant.  <br/> **Borttaget datum** är det datum då teamet togs bort.  <br/> **Tilldelad produkt** är en lista över de produkter som har tilldelats användaren.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå i** [aktivitetsrapporterna i administrationscentret för Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Välj **Kolumner** om du vill lägga till eller ta bort kolumner från rapporten.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|9.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja **länken Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

