---
title: Microsoft 365-rapporter i administrationscentret – SharePoint-aktivitet
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: Hämta SharePoint-aktivitetsanvändningsrapporten om du vill veta om aktiviteten för varje SharePoint-användare, antalet delade filer och lagringsanvändningen.
ms.openlocfilehash: de4d4951f98e722a3608e9bccf2c4a1dbfc388d0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387495"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-rapporter i administrationscentret – SharePoint-aktivitet

Som Microsoft 365-administratör visar instrumentpanelen **Rapporter** aktivitetsöversikten för olika produkter i organisationen. Där kan du öka detaljnivån för att få bättre inblick i de aktiviteter som är specifika för varje produkt. Kolla in [aktivitetsrapporterna i administrationscentret för Microsoft 365](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda SharePoint genom att titta på deras interaktion med filer. Genom att titta på hur många filer som delas kan du även få hjälp med att förstå samarbetsnivån.
  
> [!NOTE]
> En del funktioner införs stegvis. Det innebär att du kanske inte ser den här funktionen än eller att den ser annorlunda ut jämfört med beskrivningen i hjälpartiklarna. Oroa dig inte - om den ännu inte syns till kommer den snart! 
  
Om du vill förstå mängden aktivitet på respektive SharePoint-webbplats och lagringsutnyttjandet kan du titta på [rapporten om SharePoint-webbplatsanvändning](sharepoint-site-usage.md).
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hur kommer jag åt SharePoint-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **SharePoint-aktivitet** i listrutan **Välj en rapport** \> **Activity**.
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Tolka rapporten om SharePoint-aktivitet

Du kan få information om SharePoint-aktivitet genom att titta på vyerna **Filer** och **Användare**.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |I **SharePoint-aktivitetsrapporten** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Med vyn **Filer** kan du förstå det unika antalet licensierade användare som interagerar med filer som lagras på SharePoint-webbplatser.  <br/> |
|4.  <br/> |Vyn **Sidor** visar antalet unika sidor som besökts av användare.  <br/> |
|5.  <br/> |Vyn **Användare** hjälper dig att förstå trenden för antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.  <br/> En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data           |
|6.  <br/> | På Y-axeln i diagrammet **Filer** visas antalet unika filer som en användare antingen har sparat, synkroniserat, ändrat eller delat.  <br/>  På Y-axeln i diagrammet **Användare** visas antalet unika användare som har interagerat med en fil (sparat, synkroniserat, ändrat eller delat) på en webbplats.  <br/>  I diagrammet **Sidor** är X-axeln antalet unika sidor som användarna besökt.  <br/>  X-axeln i alla diagram är det valda datumintervallet för den här specifika rapporten.  <br/> |
|7.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I **fildiagrammet** väljer du till exempel **Visad eller redigerad**, **Synkroniserad**, **Delad internt**eller **Delad externt** om du bara vill visa den information som är relaterad till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|8.  <br/> | Tabellen visar en uppdelning av aktiviteterna per webbplats.  <br/>  <br/> **Användarnamn** är e-postadressen till den användare som utförde aktiviteten på SharePoint-webbplatsen.  <br/> **Datum för senaste aktivitet (UTC)** är det senaste datum då en filaktivitet utfördes eller en sida besöktes för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.  <br/> ![Välj ett visst datum i diagrammet](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> Detta filtrerar tabellen så att filaktivitetsdata endast visas för användare som utförde aktiviteten den specifika dagen.  <br/>  **Visade eller redigerade filer** är antalet filer som användaren har laddat upp, laddat ned, ändrat eller visat.  <br/>  **Filer som synkroniseras** är antalet filer som har synkroniserats från en användares lokala enhet till SharePoint-webbplatsen.  <br/>  **Filer som delas internt** är antalet filer som har delats med användare inom organisationen eller med användare inom grupper (som kan omfatta externa användare).  <br/>  **Filer som delats externt** är antalet filer som har delats med användare utanför organisationen.  <br/>  **Besökta sidor** är besök på unika sidor av användaren.  <br/>  **Borttagen** anger att användarens licens har tagits bort.  <br/>  **OBS:** Aktivitet för en borttagen användare visas fortfarande i rapporten så länge han eller hon var licensierad någon gång under den valda tidsperioden. I kolumnen Borttagen får du information om att användaren inte längre är aktiv, men att han eller hon har bidragit till data i rapporten.  <br/> **Borttagningsdatum** är det datum då användarens licens togs bort.  <br/>  **Produkten som tilldelats** är de Microsoft 365-produkter som är licensierade till användaren.  <br/> |
|9.  <br/> |Markera ikonen **Hantera kolumner** Hantera kolumner om du vill lägga till eller ta bort kolumner ![ från ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) rapporten.  <br/> |
|10.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

