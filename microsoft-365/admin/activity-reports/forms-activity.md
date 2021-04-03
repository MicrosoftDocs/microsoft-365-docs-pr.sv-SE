---
title: Microsoft 365-rapporter i administrationscentret – Formuläraktivitet
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
description: Lär dig hur du hämtar en Microsoft Forms-aktivitetsrapport med hjälp av instrumentpanelen Rapporter i Microsoft 365 i administrationscentret för Microsoft 365.
ms.openlocfilehash: ce1109c6d6d626079794085b4dc742829841d06e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579680"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporter i administrationscentret – Formuläraktivitet

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda Microsoft Forms genom att titta på deras interaktion med formulär. Det hjälper dig också att förstå samarbetsnivån genom att titta på antalet formulär som skapats och formulär som användaren har svarat på.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Så här kommer du till formuläraktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I **listrutan Välj en** rapport väljer du  \> **Formuläraktivitet**.

## <a name="interpret-the-forms-activity-report"></a>Tolka formuläraktivitetsrapporten

Du kan få en uppfattning om användarnas formuläraktivitet genom att titta på **diagrammen Aktivitet** **och** Användare. 

![Formuläraktivitetsrapport](../../media/adminformsactivity.png)

|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I **rapporten Formuläraktivitet** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Vyn **Användare** hjälper dig att förstå trenden för antalet aktiva formuläranvändare. En användare anses vara aktiv om han eller hon har genomfört en aktivitet runt ett formulär (skapa, redigera, visa osv.) eller svarat på ett formulär inom den specifika tidsperioden.  <br/> |
|4.  <br/> |Vyn **Aktivitet** hjälper dig att förstå trenden för antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.<br/> OBS! En aktivitet kan inträffa flera gånger för ett enskilt formulär, men räknas bara som ett aktivt formulär. Du kan till exempel skapa ett formulär och fortsätta att redigera samma formulär flera gånger under en viss tidsperiod, men det räknas bara som ett enda formulär. Men om en användare skickade flera svar för samma formulär skulle varje svar fortfarande vara ett enskilt svar och räknas därför flera gånger. <br/> |
|5.<br/>|I **diagrammet Användare** visar Y-axeln antalet unika användare. X-axeln är det datum då unika användare är aktiva. Förklaringarna är:<br/><br/>**Designers** innebär att användaren har skapat eller redigerat ett formulär.<br/>**Svarare** innebär att användaren har skickat svar till ett formulär.<br/> **Totalt antal** användare innebär alla i företaget som har varit designer eller svarare.<br/><br/> I diagrammet **Aktivitet** visar Y-axeln antalet unika formulär eller svar. X-axeln är datumet då formulär- eller svarsaktiviteten inträffade. Förklaringarna är:<br/><br/>**Formulär som** har skapats är antalet unika formulär som användarna har skapat.<br/> **Inloggade svar** antalet inloggade svar som användarna i organisationen har tagit emot.<br/> **Anonyma** svar är antalet anonyma svar som användarna i organisationen har tagit emot.<br/><br/>|
|6.<br/>|Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Användare kan du till exempel välja designers, svarare eller totalt antal användare om du bara vill se den relaterade informationen. När du ändrar det här valet ändras inte informationen i rutnätstabellen nedanför den.|
|7.<br/>|Tabellen visar en uppdelning av aktiviteterna per användare. Förklaringarna är:<br/><br/>**Användarnamn** är e-postadressen till den användare som utförde aktiviteten på Microsoft Forms.<br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en formuläraktivitet utfördes av användaren för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/><br/>Då filtreras tabellen så att data för filaktivitet endast visas för användare som utförde aktiviteten på den specifika dagen.<br/><br/>**Antal formulär som skapats** är antalet formulär som användaren har skapat.<br/> **Antal formulär som har** besvarats är antalet formulär som användaren har skickat svar till.|
|8.<br/>|Välj ikonen **Hantera kolumner för** att lägga till eller ta bort kolumner i rapporten.|
|9.<br/>|Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel aggregering, sortering och filtrering för vidare analys. Om du har färre än 100 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|