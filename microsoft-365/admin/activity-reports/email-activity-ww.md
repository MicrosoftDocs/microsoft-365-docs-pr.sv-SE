---
title: Microsoft 365 Rapporter i administrationscentret – E-postaktivitet
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
description: Lär dig hur du hämtar en e-postaktivitetsrapport med hjälp Microsoft 365 instrumentpanelen Rapporter Microsoft 365 administrationscentret.
ms.openlocfilehash: 65ef74ccd05aa4b55fc127985c03a490bb109b4b
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921991"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365 Rapporter i administrationscentret – E-postaktivitet

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel få en övergripande vy av e-postaktiviteten inom organisationen från sidan Rapporter och sedan mer detaljerat i widgeten E-postaktivitet för att förstå trenderna och detaljerna i e-postaktiviteten per användare inom organisation.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter. 

## <a name="how-to-get-to-the-email-activity-report"></a>Komma åt e-postaktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.
2. Välj **Visa mer under** **E-postaktivitet**. 
3. I **listrutan** E-postaktivitet väljer du Välj Exchange  \> **E-postaktivitet**.
  
## <a name="interpret-the-email-activity-report"></a>Tolka e-postaktivitetsrapporten

Du kan få inblick i användarnas e-postaktivitet genom att titta på diagrammen **Aktivitet** och **Användare**. 
  
![Rapport om e-postaktivitet](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **E-postaktivitet** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Med hjälp av diagrammet **Aktivitet** förstår du trenden med hur mycket e-postaktivitet som pågår i organisationen. Du kan förstå uppdelningen mellan aktiviteterna för att skicka, läsa e-post, ta emot e-post, skapa möte eller möten.  <br/> |
|4.  <br/> |Med hjälp av diagrammet **Användare** förstår du trenden med mängden unika användare som skapar e-postaktiviteter. Du kan titta på trenden för användare som utför skicka e-post, läsa e-post, ta emot e-post, skapa möte eller interagera med möten.  <br/> |
|5.  <br/> | I diagrammet **Aktivitet är** Y-axeln antalet aktiviteter av typen e-postmeddelande skickat, e-postmeddelande mottaget, läst e-postmeddelande, möte skapat och möte interagerat.  <br/>  I **aktivitetsdiagrammet** Användare är Y-axeln användarens aktivitet av typen e-postmeddelande skickat, e-postmeddelande mottaget, läst e-postmeddelande, möte skapat eller möte interagerat.  <br/>  X-axeln i båda diagrammen är det valda datumintervallet för den här specifika rapporten.  <br/> |
|6.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen.  <br/> |
|7.  <br/> | Tabellen visar en uppdelning av e-postaktiviteter per användare. Här visas alla användare som har en Exchange-produkt som tilldelats dem och deras e-aktiviteter. <br/> <br/> **Användarnamn** är användarens e-postadress.  <br/> **Visningsnamn** är användarens fullständiga namn.  <br/> **Borttagen** refererar till användare vars aktuella status har tagits bort, men som var aktiv under en del av rapportens rapporteringsperiod.  <br/> **Borttaget datum** är det datum användaren togs bort.  <br/> **Datum för senaste aktivitet** refererar till den senaste gången användaren utförde en aktivitet för att läsa eller skicka e-post.  <br/> **Skicka-åtgärder** är antalet gånger åtgärden att skicka ett e-postmeddelande har registrerats för användaren.  <br/> **Mottagningsåtgärder** är antalet gånger åtgärden att ta emot ett e-postmeddelande har registrerats för användaren.  <br/> **Läsåtgärder** är antalet gånger åtgärden att läsa ett e-postmeddelande har registrerats för användaren.  <br/> **Åtgärder som skapats under** mötet är antalet gånger åtgärden att skicka en mötesförfrågan har registrerats för användaren.  <br/> **Åtgärder som har interagerats** i ett möte är antalet gånger åtgärden att acceptera, preliminärt, avböja eller avbryta en mötesförfrågan registrerats för användaren.  <br/> **Tilldelad** produkt är de produkter som har tilldelats till användaren.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information **finns i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i Microsoft 365 administrationscenter](activity-reports.md).  <br/> |
|8.  <br/> |Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport om e-postaktivitet – välj kolumner](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
> [!NOTE]
> Rapporten E-postaktivitet är endast tillgänglig för postlådor som är kopplade till användare som har licenser.
