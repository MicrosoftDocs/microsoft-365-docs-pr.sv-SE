---
title: Microsoft 365-rapporter i administrationscentret – formuläraktivitet
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
description: Lär dig hur du skaffar en aktivitetsrapport för Microsoft Forms med instrumentpanelen Microsoft 365 Reports i administrationscentret för Microsoft 365.
ms.openlocfilehash: f835533fb626c8d6e7bd408b90abaa558304e20b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387759"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporter i administrationscentret – formuläraktivitet

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel förstå aktiviteten hos alla användare som licensieras för att använda Microsoft Forms genom att titta på deras interaktion med formulär. Det hjälper dig också att förstå graden av samarbete som pågår genom att titta på antalet formulär som skapats och formulär som användaren svarade på.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Så här kommer du till aktivitetsrapporten Formulär

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. **Välj** Formuläraktivitet i listrutan **Välj en rapport** \> **activity**.

## <a name="interpret-the-forms-activity-report"></a>Tolka formuläraktivitetsrapporten

Du kan få en vy över användarens formuläraktivitet genom att titta på diagrammen **Aktivitet** **och Användare.** 

![Aktivitetsrapport för formulär](../../media/adminformsactivity.png)

|||
|:-----|:-----|
|1.  <br/> |**Aktivitetsrapporten Formulär** kan visas för trender under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Vyn **Användare** hjälper dig att förstå trenden i antalet aktiva formuläranvändare. En användare anses vara aktiv om han eller hon har utfört en aktivitet runt ett formulär (skapa, redigera, visa, etc.) eller svarat på ett formulär inom den specifika tidsperioden.  <br/> |
|4.  <br/> |**Aktivitetsvyn** hjälper dig att förstå trenden i antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.<br/> En aktivitet kan inträffa flera gånger för ett enskilt formulär, men räknas bara som ett aktivt formulär. Du kan till exempel skapa ett formulär och fortsätta att redigera samma formulär flera gånger under en angiven tidsperiod, men det räknas bara som ett enda formulär. Men om en användare skickade flera svar för samma formulär, skulle varje svar fortfarande vara ett individuellt svar och därmed räknas flera gånger. <br/> |
|5.<br/>|I diagrammet **Användare** är Y-axeln antalet unika användare. X-axeln är det datum som de unika användarna är aktiva på. Legenderna är:<br/><br/>**Designers** innebär att användaren har skapat eller redigerat ett formulär.<br/>**Responders** innebär att användaren har skickat svar till ett formulär.<br/> **Totalt antal användare** innebär alla i företaget som har varit designer eller responder.<br/><br/> I **aktivitetsdiagrammet** är Y-axeln antalet unika formulär eller svar. X-axeln är det datum då formuläret eller svarsaktiviteten inträffade. Legenderna är:<br/><br/>**Formulär som skapas** är antalet unika formulär som användarna har skapat.<br/> **Inloggade svar** antalet inloggade svar som användarna i organisationen har fått.<br/> **Anonyma svar** är antalet anonyma svar som användarna i organisationen har fått.<br/><br/>|
|6.<br/>|Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet Användare väljer du till exempel designers, responders eller totala användare om du bara vill se information som är relaterad till var och en. Om du ändrar det här valet ändras inte informationen i rutnätstabellen under den.|
|7.<br/>|Tabellen visar en uppdelning av aktiviteterna på användarnivå. Legenderna är:<br/><br/>**Användarnamn** är e-postadressen till den användare som utförde aktiviteten i Microsoft Forms.<br/>**Sista aktivitetsdatum (UTC)** är det senaste datumet då en formuläraktivitet utfördes av användaren för det valda datumintervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/><br/>Detta filtrerar tabellen så att filaktivitetsdata endast visas för användare som utförde aktiviteten den specifika dagen.<br/><br/>**Antal formulär som har skapats** är antalet formulär som användaren har skapat.<br/> Antal formulär som **besvaras** är antalet formulär som användaren har skickat svar på.|
|8.<br/>|Markera ikonen **Hantera kolumner** om du vill lägga till eller ta bort kolumner från rapporten.|
|9.<br/>|Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Detta exporterar data för alla användare och gör att du kan göra enkel aggregering, sortering och filtrering för vidare analys. Om du har färre än 100 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|