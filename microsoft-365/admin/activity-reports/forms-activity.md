---
title: Microsoft 365-rapporter i administrations centret – formulär aktivitet
ms.author: sirkkuw
author: sirkkuw
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
description: Lär dig hur du får en rapport om Microsoft Forms-aktiviteter med instrument panelen för Microsoft 365-rapporter i administrations centret för Microsoft 365.
ms.openlocfilehash: 78b09edfbfeb83c056af16787085b7c4cfe93fc6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949210"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporter i administrations centret – formulär aktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel förstå aktiviteten hos alla användare som är licensierade att använda Microsoft-formulär genom att studera deras interaktion med formulär. Det hjälper dig också att förstå samarbetets möjligheter genom att titta på antalet formulär som skapats och formulär som användaren svarade på.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Så här kommer du till rapporten formulär aktivitet

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **formulär** aktivitet i list rutan **Välj en rapport** \> **activity**.

## <a name="interpret-the-forms-activity-report"></a>Tolka rapporten formulär aktivitet

Du kan få en vy i användarens formulär aktivitet genom att titta på diagrammen **aktivitet** och **användare** . 

![Formulär aktivitets rapport](../../media/adminformsactivity.png)

|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **formulär aktivitet** kan du se trender under de senaste 7, 30, 90 eller 180 dagar. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |Med vyn **användare** kan du förstå trenden i antalet aktiva formulär användare. En användare anses vara aktiv om han eller hon har kört en aktivitet i ett formulär (skapa, redigera, vy o.s.v.) eller svarat på ett formulär under den angivna tids perioden.  <br/> |
|4.  <br/> |Med vyn **aktivitet** kan du förstå trenden för antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.<br/> Obs! en aktivitet kan förekomma flera gånger i ett formulär, men räknas bara som ett aktivt formulär. Du kan till exempel skapa ett formulär och fortsätta att redigera samma formulär flera gånger under en viss tids period, men det räknas bara som ett enda formulär. Om en användare har lämnat flera svar för samma formulär skulle varje svar ändå vara ett enskilt svar och därför räknas flera gånger. <br/> |
|5.<br/>|I diagrammet **användare** är Y-axeln antalet unika användare. X-axeln är det datum då de unika användarna är aktiva på. Följande förklaringar är:<br/><br/>**Designers** innebär att användaren har skapat eller redigerat ett formulär.<br/>**Svarare** innebär att användaren har skickat svar till ett formulär.<br/> **Totalt antal användare** betyder vem som helst i företaget som har en designer eller responder.<br/><br/> I diagrammet **aktivitet** är Y-axeln antalet unika formulär eller svar. X-axeln är det datum då formen eller svars aktiviteten ägde rum. Följande förklaringar är:<br/><br/>**Skapade formulär** är antalet unika formulär som användarna har skapat.<br/> **Inloggade svar** antalet inloggade svar som användarna i organisationen har tagit emot.<br/> **Anonyma svar** är antalet anonyma svar som användarna i organisationen har tagit emot.<br/><br/>|
|18.6.<br/>|Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet användare väljer du till exempel designer, svarare eller totalt antal användare om du bara vill se informationen som hör till var och en. Om du ändrar den här markeringen ändras inte informationen i rutnäts tabellen nedanför den.|
|borttagning.<br/>|Tabellen visar en uppdelning av aktiviteterna på per-användare-nivå. Följande förklaringar är:<br/><br/>**Username** är e-postadressen för den användare som utförde aktiviteten på Microsoft Forms.<br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en formulär aktivitet utfördes av användaren för det valda datum intervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/><br/>Då filtreras tabellen för att endast Visa fil aktiviteter för användare som utförde aktiviteten på den aktuella dagen.<br/><br/>**Antal skapade formulär** är antalet formulär som användaren har skapat.<br/> **Antalet besvarade formulär** är antalet formulär som användaren har skickat svar till.|
|8.2.<br/>|Välj ikonen **Hantera kolumner** för att lägga till eller ta bort kolumner i rapporten.|
|9.<br/>|Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Detta exporterar data för alla användare och gör att du kan utföra enkel sammanställning, sortering och filtrering för ytterligare analyser. Om du har färre än 100 användare kan du sortera och filtrera i tabellen i rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|