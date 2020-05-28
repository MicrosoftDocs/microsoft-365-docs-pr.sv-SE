---
title: Microsoft 365-rapporter i administrationscentret – E-postaktivitet
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
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Lär dig hur du skaffar en e-postaktivitetsrapport med instrumentpanelen Microsoft 365 Reports i administrationscentret för Microsoft 365.
ms.openlocfilehash: a864b997d607b06391c1a2a5d4725bc8d074de87
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387783"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365-rapporter i administrationscentret – E-postaktivitet

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel få en övergripande vy av e-postaktiviteten inom organisationen från sidan Rapporter och sedan mer detaljerat i widgeten E-postaktivitet för att förstå trenderna och detaljerna i e-postaktiviteten per användare inom organisation.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter. 

## <a name="how-to-get-to-the-email-activity-report"></a>Komma åt e-postaktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **Select a report** **Exchange** \> **Exchange-e-postaktivitet**i listrutan Välj en rapport .
  
## <a name="interpret-the-email-activity-report"></a>Tolka e-postaktivitetsrapporten

Du kan få inblick i användarnas e-postaktivitet genom att titta på diagrammen **Aktivitet** och **Användare**. 
  
![Rapport över e-postaktivitet](../../media/2317f03d-2d71-46bf-a5c7-d94dbc8cfbe1.png)
  
|||
|:-----|:-----|
|1.  <br/> |I rapporten **E-postaktivitet** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Med hjälp av diagrammet **Aktivitet** förstår du trenden med hur mycket e-postaktivitet som pågår i organisationen. Du kan förstå uppdelningen av e-postsändning, e-postläsning, mottagna e-postmeddelanden, mötesskapade eller mötesaktiviteterade aktiviteter.  <br/> |
|4.  <br/> |Med hjälp av diagrammet **Användare** förstår du trenden med mängden unika användare som skapar e-postaktiviteter. Du kan titta på trenden för användare som utför e-postsändning, e-postläsning, e-postmottagning, mötesskapande eller mötesaktivitet.  <br/> |
|5.  <br/> | I **aktivitetsdiagrammet** är Y-axeln antalet aktiviteter av typen e-post som skickas, e-post som tas emot, e-postläsning, möte skapas och möte interageras.  <br/>  I aktivitetsdiagrammet **Användare** är Y-axeln användarens utförande aktivitet av den typ e-post som skickas, e-post som tas emot, e-postläsning, möte skapas eller möte interageras.  <br/>  X-axeln i båda diagrammen är det valda datumintervallet för den här specifika rapporten.  <br/> |
|6.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I **aktivitetsdiagrammet** väljer du till exempel **Skickat,** **Mottaget,** **Läst,** **Möteskapat**eller **Mötesaverkade** ![ filterdiagram för specifika relaterade data ](../../media/6065f515-b97b-4829-b683-a7667542d1af.png) om du bara vill visa information som är relaterad till var och en.   När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|7.  <br/> | Tabellen visar en uppdelning av e-postaktiviteter per användare. Här visas alla användare som har en Exchange-produkt som tilldelats dem och deras e-aktiviteter. <br/> <br/> **Användarnamn** är användarens e-postadress.  <br/> **Visningsnamnet** är det fullständiga namnet om användaren.  <br/> **Borttagen** refererar till användare vars aktuella status har tagits bort, men som var aktiv under en del av rapportens rapporteringsperiod.  <br/> **Borttaget datum** är det datum användaren togs bort.  <br/> **Datum för senaste aktivitet** refererar till den senaste gången användaren utförde en aktivitet för att läsa eller skicka e-post.  <br/> **Skicka-åtgärder** är antalet gånger åtgärden att skicka ett e-postmeddelande har registrerats för användaren.  <br/> **Mottagningsåtgärder** är antalet gånger åtgärden att ta emot ett e-postmeddelande har registrerats för användaren.  <br/> **Läsåtgärder** är antalet gånger åtgärden att läsa ett e-postmeddelande har registrerats för användaren.  <br/> **Möte skapade åtgärder** är antalet gånger en mötesförfrågan skicka åtgärd spelades in för användaren.  <br/> **Mötessammanverkade åtgärder** är antalet gånger en mötesförfrågan accepterar, preliminärt, avböjer eller avbryter åtgärden har registrerats för användaren.  <br/> **Produkt som tilldelats** är de produkter som har tilldelats den här användaren.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|8.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera** ![ ](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) export. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
Rapporten E-postaktivitet är endast tillgänglig för postlådor som är associerade med användare som har licenser.
