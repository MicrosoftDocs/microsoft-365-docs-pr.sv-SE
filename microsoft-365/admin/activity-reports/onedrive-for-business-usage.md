---
title: Microsoft 365-rapporter i administrations Center – OneDrive för företag-användning
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
description: 'Få en rapport om OneDrive för företag-användning om du vill veta hur många filer och lagrings utrymme som används i din organisation. '
ms.openlocfilehash: e08dff4e763479afa197377d37e474384492c012
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948931"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporter i administrations Center – OneDrive för företag-användning

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Hur får jag fram OneDrive-användningsrapporten?

1. Gå till **rapport** användning i administrations centret \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a>.

    
2. I list rutan **Välj en rapport** väljer du OneDrive- **OneDrive** \> **användning**. 
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan få en inblick i hur OneDrive för företag används genom att titta på vyerna **Konton**, **Filer** och **Lagring**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I användningsrapporten för **OneDrive** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar. <br/>|
|3.  <br/> |Vyn **Konton** visar trenden för det totala antalet och aktiva OneDrive-konton. "Aktiva konton" är alla konton där användare visar, ändrar, laddar upp, laddar ned, delar eller synkroniserar filer.  <br/> |
|4.  <br/> |Vyn **filer** visar totalt antal och aktiva filer. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tids period.  <br/> Obs! en fil aktivitet kan förekomma flera gånger i en fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data.           |
|5.  <br/> |I vyn **Lagring** visas trenden för mängden lagringsutrymme som du använder i OneDrive. Om du vill kontrol lera lagrings gränserna läser du [kontrol lera om en användare har standard lagrings gränsen eller en viss gräns](https://docs.microsoft.com/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit).  <br/> Obs! storleken inkluderar alla versioner och metadata som är kopplade till filerna.           |
|18.6.  <br/> | I diagrammet **Konton** visar Y-axeln antalet OneDrive-konton.  <br/>  I diagrammet **Filer** visar Y-axeln antalet filer som lagrats på OneDrive.  <br/>  I diagrammet **Lagring** visar Y-axeln hur mycket lagringsutrymme som används på OneDrive.  <br/>  X-axeln i alla diagram är det valda datumintervallet för den här specifika rapporten.  <br/> |
|borttagning.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **filer** väljer du till exempel **Totalt antal filer** eller **aktiva filer**. Välj **Total konton** eller **aktiva konton**i diagrammet **konton** . I diagrammet **lagring** väljer du **använt lagrings utrymme**. När du ändrar ditt val ändras inte informationen i tabellen.  <br/> |
|8.2.  <br/> | Tabellen visar en sammanfattning av data för varje användares OneDrive. För att visas i tabellen måste användaren ha tilldelats en produktlicens som innehåller OneDrive, och de måste ha SharePoint Online aktiverat. Användaren måste även antingen logga in på OneDrive-synkroniseringsklienten eller bläddra till sin egen OneDrive med hjälp av en webbläsare.  <br/>  Om OneDrive har haft filaktivitet visas det senaste datum som filaktiviteten utfördes. Raderna i tabellen sorteras efter **Datum för senaste aktivitet** så OneDrive-kontot med den senaste filaktiviteten visas därför högst upp i listan.  <br/>  Du kan lägga till eller ta bort kolumner i tabellen.  <br/> ![Kolumn alternativ](../../media/onedriveusage-columns.png)  <br/> **URL** är webb adressen för användarens OneDrive.  <br/> **Borttaget** är borttagningsstatusen för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> **Ägare** är användarnamnet på den primära administratören för OneDrive.  <br/> **Ägarens huvud namn** är e-postadressen till ägaren till OneDrive.  <br/> **Datum för senaste aktivitet (UTC)** är det senaste datum då en filaktivitet utfördes på OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> **Filer** är antalet filer på OneDrive.  <br/> **Aktiva filer** är antalet aktiva filer under tidsperioden.<br/> OBS! om filer togs bort under den angivna tids perioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer i OneDrive. Borttagna användare kommer att fortsätta att visas i rapporter för 180 dagar.<br/>**Använt lagringsutrymme (MB)** är mängden lagringsutrymme som används på OneDrive i MB. <br/>  Om organisationens principer hindrar dig från att visa rapporter där användar information är identifierbar kan du ändra sekretess inställningen för alla dessa rapporter. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Välj ikonen **Hantera kolumner** ![ Hantera kolumner ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) för att lägga till eller ta bort kolumner i rapporten.  <br/> |
|10.3.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för varje OneDrive och du kan göra en enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 OneDrive-konton kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 OneDrive-konton måste du exportera data för att kunna filtrera och sortera.  <br/> Obs! när data exporteras till en Excel-fil återges datumet då innehålls rapporten skapades i filen i kolumnen **data från och med** .  <br/> |
|||
   
