---
title: Microsoft 365-rapporter i administrations Center – e-postaktivitet
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
description: Lär dig hur du får en rapport om e-postaktiviteter med instrument panelen för Microsoft 365-rapporter i administrations centret för Microsoft 365.
ms.openlocfilehash: b2b322fe7e35c3fa7e4a5966919321b329004d92
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948238"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365-rapporter i administrations Center – e-postaktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel få en övergripande vy av e-postaktiviteten inom organisationen från sidan Rapporter och sedan mer detaljerat i widgeten E-postaktivitet för att förstå trenderna och detaljerna i e-postaktiviteten per användare inom organisation.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter. 

## <a name="how-to-get-to-the-email-activity-report"></a>Komma åt e-postaktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du **Exchange** \> **-e-postaktivitet**.
  
## <a name="interpret-the-email-activity-report"></a>Tolka e-postaktivitetsrapporten

Du kan få inblick i användarnas e-postaktivitet genom att titta på diagrammen **Aktivitet** och **Användare**. 
  
![Rapport om e-postaktivitet](../../media/2317f03d-2d71-46bf-a5c7-d94dbc8cfbe1.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **E-postaktivitet** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |Med hjälp av diagrammet **Aktivitet** förstår du trenden med hur mycket e-postaktivitet som pågår i organisationen. Du kan förstå delning av e-post, e-post, olästa, e-postmeddelanden, skapade möten eller möten.  <br/> |
|4.  <br/> |Med hjälp av diagrammet **Användare** förstår du trenden med mängden unika användare som skapar e-postaktiviteter. Du kan se trenden för de användare som utför e-postutskick, e-postläsning, e-post, möten att skapa eller träffa möten.  <br/> |
|5.  <br/> | I diagrammet **aktivitet** är Y-axeln antalet aktiviteter av typen e-post som skickas, e-post, oläst e-post, för skapade möten och möten.  <br/>  I aktivitets diagrammet **användare** är Y-axeln användarens utförande av den typ av e-post som skickas, e-post, läst e-post, för skapade möten eller möten.  <br/>  X-axeln i båda diagrammen är det valda datumintervallet för den här specifika rapporten.  <br/> |
|18.6.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **aktivitet** väljer du till exempel **skickat**, **mottaget**, **läst**, **möte som skapats**eller ett **Mötes interagerat** ![ filter diagram för specifika relaterade data för ](../../media/6065f515-b97b-4829-b683-a7667542d1af.png) att visa endast informationen som hör till var och en.   När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|borttagning.  <br/> | Tabellen visar en uppdelning av e-postaktiviteter per användare. Här visas alla användare som har en Exchange-produkt som tilldelats dem och deras e-aktiviteter. <br/> <br/> **Användarnamn** är användarens e-postadress.  <br/> **Visnings namn** är det fullständiga namnet om användaren.  <br/> **Borttagen** refererar till användare vars aktuella status har tagits bort, men som var aktiv under en del av rapportens rapporteringsperiod.  <br/> **Borttaget datum** är det datum användaren togs bort.  <br/> **Datum för senaste aktivitet** refererar till den senaste gången användaren utförde en aktivitet för att läsa eller skicka e-post.  <br/> **Skicka-åtgärder** är antalet gånger åtgärden att skicka ett e-postmeddelande har registrerats för användaren.  <br/> **Mottagningsåtgärder** är antalet gånger åtgärden att ta emot ett e-postmeddelande har registrerats för användaren.  <br/> **Läsåtgärder** är antalet gånger åtgärden att läsa ett e-postmeddelande har registrerats för användaren.  <br/> **Åtgärdade åtgärder** är antalet gånger som en skicka-åtgärd för en Mötes förfrågan har registrerats för användaren.  <br/> **Åtgärder som interagerat med mötet** är antalet gånger som en Mötes förfrågan accepterar, preliminärt, avböjer eller Avbryt åtgärd har registrerats för användaren.  <br/> **Tilldelad produkt** är de produkter som tilldelats den här användaren.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.2.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja länken **Exportera** ![ Exportera ](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) . Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
Obs! rapporten e-postaktivitet är bara tillgänglig för post lådor som är kopplade till användare som har licenser.
