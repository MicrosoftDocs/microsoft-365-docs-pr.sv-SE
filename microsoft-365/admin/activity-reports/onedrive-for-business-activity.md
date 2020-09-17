---
title: Microsoft 365-rapporter i administrations Center – OneDrive för företag-aktivitet
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Hämta rapporten för OneDrive-användning för din organisation och få aktiviteten för varje OneDrive-användare, antalet delade filer och lagrings användningen.
ms.openlocfilehash: dd5ac1c52d2226b12c75dc92c3407012251a90da
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948934"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-rapporter i administrations Center – OneDrive för företag-aktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få mer ingående förståelse för aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för var och en av de användare som har en licens för att använda SharePoint genom att titta på hans eller hennes interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp att förstå samarbetsnivån.
  
> [!NOTE]
> En del funktioner införs stegvis. Det innebär att du kanske ännu inte kan se den här funktionen eller att den ser annorlunda ut jämfört med beskrivningen i hjälpartiklarna. Men oroa dig inte, den kommer snart! 
  
Om du vill veta mer om mängden aktivitet på respektive OneDrive-konto och lagringsutnyttjandet kan du titta på [rapporten om OneDrive-användning](onedrive-for-business-usage.md).
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **OneDrive** -aktivitet i list rutan **Välj en rapport** \> **Activity**.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Förstå aktivitetsrapporten i OneDrive för företag

Du kan få information om OneDrive för företag-aktivitet genom att titta på vyerna **Filer** och **Användare**. 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I aktivitetsrapporten för **OneDrive för företag** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar. <br/>|
|3.  <br/> |Med vyn **Filer** kan du förstå det unika antalet licensierade användare som interagerat med filer mot något OneDrive-konto.  <br/> |
|4.  <br/> |Vyn **Användare** hjälper dig förstå trenden för antalet aktiva OneDrive-användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) inom den angivna tidsperioden.  <br/> Obs! en fil aktivitet kan förekomma flera gånger i en fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data.           |
|5.  <br/> | På Y-axeln i diagrammet **Filer** visas antalet unika filer som en användare antingen har sparat, synkroniserat, ändrat eller delat.  <br/>  På Y-axeln i diagrammet **Användare** visas antalet unika användare som har interagerat med en fil (sparat, synkroniserat, ändrat eller delat) på ett OneDrive-konto.  <br/>  X-axeln i alla diagram är det valda datumintervallet för den här specifika rapporten.  <br/> |
|18.6.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **filer** väljer du till exempel **Visa eller redigera** eller **synkroniserat** för att bara se informationen som är relaterad till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|borttagning.  <br/> | I tabellen visas en uppdelning av data per användare. Du kan lägga till eller ta bort kolumner i tabellen.   <br/>  **Username** är användar namnet för ägaren av OneDrive-kontot.  <br/> **Datum för senaste aktivitet (UTC)** är det senaste datum då en filaktivitet utfördes på OneDrive-kontot för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> ![Markera ett visst datum i diagrammet](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Då filtreras tabellen för att endast Visa fil aktiviteter för användare som utförde aktiviteten på den aktuella dagen.  <br/> **Visade eller redigerade filer** är antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.  <br/> **Synkroniserade filer** är antalet filer som har synkroniserats från en användares lokala enhet till OneDrive-kontot.  <br/> **Filer som delas internt** är antalet filer som har delats med användare inom organisationen eller med användare inom grupper (som kan inkludera externa användare).  <br/> **Filer som delats externt** är antalet filer som har delats med användare utanför organisationen.  <br/> **Borttagen** anger att användarens licens har tagits bort.  <br/> Obs! aktiviteten för en borttagen användare visas fortfarande i en rapport så länge han eller hon har licensierats vid ett visst tillfälle under den valda tids perioden. I kolumnen **Borttagen** får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.<br/>**Borttagningsdatum** är det datum då användarens licens togs bort.  <br/> **Tilldelad produkt** är de Microsoft 365-produkter som är licensierade till användaren.  <br/>  Om organisationens principer hindrar dig från att visa rapporter där användar information är identifierbar kan du ändra sekretess inställningen för alla dessa rapporter. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.2.  <br/> |Välj ikonen **Hantera kolumner** ![ Hantera kolumner ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) för att lägga till eller ta bort kolumner i rapporten.  <br/> |
|9.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

