---
title: Microsoft 365-rapporter i administrationscentret – Dynamics 365 Customer Voice-aktivitet
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
description: Lär dig hur du får en Microsoft Dynamics 365 Customer Voice-aktivitetsrapport med hjälp av instrumentpanelen Microsoft 365 Rapporter i administrationscentret för Microsoft 365.
ms.openlocfilehash: 26d376602caebcb5276b77a3d2c962a14e5fead5
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579656"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-rapporter i administrationscentret – Dynamics 365 Customer Voice-aktivitet

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda Microsoft Dynamics 365 Customer Voice genom att titta på deras interaktioner med Dynamics 365 Customer Voice. Det hjälper dig också att förstå samarbetsnivån genom att titta på antalet pro undersökningar som har skapats och pro undersökningar som användarna har svarat på. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Så här kommer du till aktivitetsrapporten för Forms Pro

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj  **Dynamics 365** Customer Voice-aktivitet i listrutan Välj en \> **rapport.**

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Tolka dynamics 365-kundröstaktivitetsrapporten

Du kan få en uppfattning om användarnas Dynamics 365 Customer Voice-aktivitet genom att titta på **diagrammen Aktivitet** **och** Användare. 

![Formuläraktivitetsrapport](../../media/formsproactivity.png)

|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I **rapporten Dynamics 365** Kundröst-aktivitet kan du se trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).   <br/> |
|2.  <br/> |Informationen i varje rapport är vanligtvis lika ny som de senaste 48 timmarna.  <br/> |
|3.  <br/> |Vyn **Användare** hjälper dig att förstå trenden för antalet aktiva Dynamics 365 Customer Voice-användare. En användare anses vara aktiv om de har genomfört en aktivitet runt en pro undersökning (skapa, redigera, visa osv.) inom den specifika tidsperioden.  <br/> |
|4.  <br/> |Vyn **Aktivitet** hjälper dig att förstå trenden för antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.<br/> Obs! En aktivitet kan inträffa flera gånger för en enskild undersökning, men räknas bara som en aktiv undersökning. Du kan till exempel skapa en pro survey och fortsätta att redigera samma undersökning flera gånger under en viss tidsperiod, men den räknas bara som en enda undersökning. <br>|
|5.<br/>|I **diagrammet Användare** visar Y-axeln antalet unika användare. X-axeln är det datum då unika användare är aktiva. Förklaringarna är:<br/><br/>**Designers** innebär att användaren har skapat eller redigerat en Dynamics 365 Customer Voice Survey.<br><br>I diagrammet **Aktivitet** är Y-axeln antalet Dynamics 365 Kundröst-svar per undersökning. X-axeln är det datum då undersöknings- eller svarsaktiviteten inträffade. Förklaringarna är:<br/><br/>**Undersökningar som** har skapats är antalet unika Dynamics 365 Customer Voice-undersökningar som användarna har skapat<br>**Svar** är antalet anonyma eller icke-anonyma svar som användare som har fått undersökningen har skickat. |
|6.<br/>|Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Användare kan du till exempel välja designers, svarare eller totalt antal användare om du bara vill se den relaterade informationen. När du ändrar det här valet ändras inte informationen i rutnätstabellen nedanför den.|
|7.<br/>|Tabellen visar en uppdelning av aktiviteterna per användare. Förklaringarna är:<br/><br/>**Användarnamn** är e-postadressen till den användare som utförde aktiviteten på Microsoft Forms.<br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en formuläraktivitet utfördes av användaren för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/>Då filtreras tabellen så att data för filaktivitet endast visas för användare som utförde aktiviteten på den specifika dagen.<br/><br/>**Antal undersökningar som har** skapats är antalet undersökningar som användaren har skapat.<br/> **Antalet undersökningssvar** är antalet svar från svarare som undersökningen har distribuerats till.|
|8.<br/>|Välj ikonen **Hantera kolumner för** att lägga till eller ta bort kolumner i rapporten.|
|9.<br/>|Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel aggregering, sortering och filtrering för vidare analys. Om du har mindre än 100 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|