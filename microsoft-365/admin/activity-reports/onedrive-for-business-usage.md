---
title: Microsoft 365-rapporter i administrationscentret – OneDrive för företag-användning
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
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Få information i användningsrapporten för OneDrive för företag om det totala antalet filer och lagring som används i organisationen. '
ms.openlocfilehash: 1aaae0872863a7983598af009b2ecdffc81a6389
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904534"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporter i administrationscentret – OneDrive för företag-användning

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Hur får jag fram OneDrive-användningsrapporten?

1. Gå till Rapportanvändning  i \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">administrationscentret.</a>

    
2. Välj **OneDrive-användning** i listrutan Välj **en** \> **rapport.** 
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan få en inblick i hur OneDrive för företag används genom att titta på vyerna **Konton**, **Filer** och **Lagring**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I användningsrapporten för **OneDrive** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna. <br/>|
|3.  <br/> |Vyn **Konton** visar trenden för det totala antalet och aktiva OneDrive-konton. "Aktiva konton" är alla konton där användare visar, ändrar, laddar upp, laddar ned, delar eller synkroniserar filer.  <br/> |
|4.  <br/> |I **vyn** Filer visas det totala antalet filer och antalet aktiva filer. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  <br/> Obs! En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data.           |
|5.  <br/> |I vyn **Lagring** visas trenden för mängden lagringsutrymme som du använder i OneDrive. Om du vill kontrollera lagringsbegränsningarna kan du [läsa Kontrollera om en användare har standardlagringsgränsen eller en viss gräns.](/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit)  <br/> Obs! Storleken omfattar alla versioner och metadata som är kopplade till filerna.           |
|6.  <br/> | I diagrammet **Konton** visar Y-axeln antalet OneDrive-konton.  <br/>  I diagrammet **Filer** visar Y-axeln antalet filer som lagrats på OneDrive.  <br/>  I diagrammet **Lagring** visar Y-axeln hur mycket lagringsutrymme som används på OneDrive.  <br/>  X-axeln i alla diagram är det valda datumintervallet för den här specifika rapporten.  <br/> |
|7.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Filer kan **du till** exempel välja Totalt **antal filer** eller Aktiva **filer**. I diagrammet **Konton** väljer du **Totalt antal konton** eller Aktiva **konton.** Eller välj **Använt** lagringsutrymme i **diagrammet Lagring.** När du ändrar ditt val ändras inte informationen i tabellen.  <br/> |
|8.  <br/> | Tabellen visar en sammanfattning av data för varje användares OneDrive. För att visas i tabellen måste användaren ha tilldelats en produktlicens som innehåller OneDrive, och de måste ha SharePoint Online aktiverat. Användaren måste även antingen logga in på OneDrive-synkroniseringsklienten eller bläddra till sin egen OneDrive med hjälp av en webbläsare.  <br/>  Om OneDrive har haft filaktivitet visas det senaste datum som filaktiviteten utfördes. Raderna i tabellen sorteras efter **Datum för senaste aktivitet** så OneDrive-kontot med den senaste filaktiviteten visas därför högst upp i listan.  <br/>  Du kan lägga till eller ta bort kolumner i tabellen.  <br/> ![Kolumnalternativ](../../media/onedriveusage-columns.png)  <br/> **URL** är webbadressen till användarens OneDrive.  <br/> **Borttaget** är borttagningsstatusen för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> **Ägare** är användarnamnet på den primära administratören för OneDrive.  <br/> **Ägarens huvudnamn** är e-postadressen till OneDrive-ägaren.  <br/> **Datum för senaste aktivitet (UTC)** är det senaste datum då en filaktivitet utfördes på OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> **Filer** är antalet filer på OneDrive.  <br/> **Aktiva filer** är antalet aktiva filer under tidsperioden.<br/> Obs! Om du tog bort filer under den angivna tidsperioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer i OneDrive. Borttagna användare kommer att fortsätta att visas i rapporter i 180 dagar.<br/>**Använt lagringsutrymme (MB)** är mängden lagringsutrymme som används på OneDrive i MB. <br/>  Om organisationens principer hindrar dig från att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information finns **i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i administrationscentret för Microsoft 365.](activity-reports.md)  <br/> |
|9.  <br/> |Välj ikonen **Hantera kolumner Hantera** kolumner för att lägga till eller ta bort kolumner i ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) rapporten.  <br/> |
|10.  <br/> |Du kan också exportera rapportdata till en CsV-fil för Excel genom att välja **länken** Exportera. Då exporteras data för varje OneDrive och du kan göra en enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 OneDrive-konton kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 OneDrive-konton måste du exportera data för att kunna filtrera och sortera.  <br/> Obs! När data exporteras till en Excel-fil återspeglas datumet då innehållsrapporten skapades i filen i **kolumnen Data från och med.**  <br/> |
|||
