---
title: Microsoft 365-rapporter i administrationscentret – Användning av OneDrive för företag
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Läs användningsrapporten för OneDrive för företag om du vill veta hur många filer och lagringsutrymme som används i hela organisationen. '
ms.openlocfilehash: 4c7cfaeed03627b6dfab6c694f3a5e858b125c40
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2020
ms.locfileid: "43047113"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporter i administrationscentret – Användning av OneDrive för företag

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Hur får jag fram OneDrive-användningsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **OneDrive-användning** \> **Usage**i listrutan **Välj en rapport** . 
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan få en inblick i hur OneDrive för företag används genom att titta på vyerna **Konton**, **Filer** och **Lagring**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |I användningsrapporten för **OneDrive** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna. <br/>|
|3.  <br/> |Vyn **Konton** visar trenden för det totala antalet och aktiva OneDrive-konton. "Aktiva konton" är alla konton där användare visar, ändrar, laddar upp, laddar ned, delar eller synkroniserar filer.  <br/> |
|4.  <br/> |I vyn **Filer** visas det totala antalet filer och antalet aktiva filer. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  <br/> En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data.           |
|5.  <br/> |I vyn **Lagring** visas trenden för mängden lagringsutrymme som du använder i OneDrive.  <br/> > OBS: Storleken innehåller alla versioner och metadata som är associerade med filerna.           |
|6.  <br/> | I diagrammet **Konton** visar Y-axeln antalet OneDrive-konton.  <br/>  I diagrammet **Filer** visar Y-axeln antalet filer som lagrats på OneDrive.  <br/>  I diagrammet **Lagring** visar Y-axeln hur mycket lagringsutrymme som används på OneDrive.  <br/>  X-axeln i alla diagram är det valda datumintervallet för den här specifika rapporten.  <br/> |
|7.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I **fildiagrammet** väljer du till exempel **Summafiler** eller **Aktiva filer**. I **kontodiagrammet** väljer du **Totalt antal konton** eller Aktiva **konton**. Eller i **lagringsdiagrammet** väljer du **Lagring som används**. När du ändrar ditt val ändras inte informationen i tabellen.  <br/> |
|8.  <br/> | Tabellen visar en sammanfattning av data för varje användares OneDrive. För att visas i tabellen måste användaren ha tilldelats en produktlicens som innehåller OneDrive, och de måste ha SharePoint Online aktiverat. Användaren måste även antingen logga in på OneDrive-synkroniseringsklienten eller bläddra till sin egen OneDrive med hjälp av en webbläsare.  <br/>  Om OneDrive har haft filaktivitet visas det senaste datum som filaktiviteten utfördes. Raderna i tabellen sorteras efter **Datum för senaste aktivitet** så OneDrive-kontot med den senaste filaktiviteten visas därför högst upp i listan.  <br/>  Du kan lägga till eller ta bort kolumner i tabellen.  <br/> ![Kolumnalternativ](../../media/onedriveusage-columns.png)  <br/> **URL** är webbadressen till användarens OneDrive.  <br/> **Borttaget** är borttagningsstatusen för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> **Ägare** är användarnamnet på den primära administratören för OneDrive.  <br/> **Ägarens huvudnamn** är e-postadressen till ägaren av OneDrive.  <br/> **Datum för senaste aktivitet (UTC)** är det senaste datum då en filaktivitet utfördes på OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> **Filer** är antalet filer på OneDrive.  <br/> **Aktiva filer** är antalet aktiva filer under tidsperioden. En fil anses vara aktiv om den har sparats, synkroniserats, ändrats eller delats inom en viss tidsperiod.  <br/> En filaktivitet kan inträffa flera gånger för en enskild fil, men räknas bara som en aktiv fil. Du kan till exempel spara och synkronisera samma fil flera gånger under en viss tidsperiod, men den räknas bara som en enda aktiv fil och en enda synkroniserad fil i dina data. >  Om du tog bort filer under tidsperioden som angetts för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer på OneDrive. >  Borttagna användare kommer att finnas med i rapporter under 180 dagar.<br/>**Använt lagringsutrymme (MB)** är mängden lagringsutrymme som används på OneDrive i MB. Detta inkluderar alla versioner och metadata som är kopplade till filerna.  <br/>  Om organisationens principer hindrar dig från att visa rapporter där användarinformation kan identifieras kan du ändra sekretessinställningen för alla dessa rapporter. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center Preview](activity-reports.md)  <br/> |
|9.  <br/> |Markera **Manage columns** ikonen ![Hantera kolumner](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Hantera kolumner om du vill lägga till eller ta bort kolumner från rapporten.  <br/> |
|10.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för varje OneDrive och du kan göra en enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 OneDrive-konton kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 OneDrive-konton måste du exportera data för att kunna filtrera och sortera.  <br/> När data exporteras till en Excel-fil bör du tänka på att datumet då innehållsrapporten genererades återspeglas i filen i kolumnen **Data från** och med.  <br/> |
|||
   

