---
title: Microsoft 365-rapporter i administrationscentret – användning av postlåda
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Läs om hur du får användningsrapport för postlåda för att få information om aktiviteter för användare med en användarpostlåda.
ms.openlocfilehash: d7d36359801fe72ac1c3ffc210c7795030f0b2e2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807996"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-rapporter i administrationscentret – användning av postlåda

**Användningsrapporten för postlådan** innehåller information om användare med en användarpostlåda och aktivitetsnivån för var och en baserat på e-postöverföring, läsa, skapa avtalad tid, skicka möte, acceptera möte, avböja möte och avbryta mötesaktivitet. Du får även information om hur mycket lagringsutrymme som har förbrukats av varje användarpostlåda och hur många av dem som närmar sig lagringskvotens gräns. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint- eller Skype för företag-administratör för att kunna se rapporter. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Så här kommer du åt rapporten om postlådeanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj Användning av \> **Exchange-postlåda**i listrutan **Välj en rapport** . **Exchange**
  
## <a name="interpret-the-mailbox-usage-report"></a>Tolka rapporten om postlådeanvändning

Du kan få en inblick i organisationens **Postlådeanvändning** genom att titta på diagrammen **Postlåda**, **Lagring** och **Kvot**. 
  
|||
|:-----|:-----|
|1.  <br/> |I rapporten **Postlådeanvändning** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Postlådediagrammet visar det totala antalet användarpostlådor i organisationen och hur många som är aktiva på en viss dag under rapportperioden. En användarpostlåda anses vara aktiv om någon av följande aktiviteter har utförts: skicka e-post, läsa e-post, skapa avtalad tid, skicka möte, acceptera möte, avböja möte eller ställa in ett möte.  <br/> |
|4.  <br/> |Diagrammet **Lagring** visar hur stort lagringsutrymme som används i din organisation. Lagringsdiagram innehåller inte arkivpostlådor. Mer information om automatisk expanderande arkivering finns [i Översikt över obegränsad arkivering i Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/unlimited-archiving).<br/> |
|5.  <br/> | Diagrammet **Kvot** visar antalet användarpostlådor i varje kvotkategori. Det finns fyra kvotkategorier:  <br/>  Bra - antal användare vars använda lagring ligger under kvotvärdet då varning utfärdas.  <br/>  Varning - antalet användare vars använda lagring ligger på eller över värdet då varning utfärdas, men under kvoten då sändning förhindras  <br/>  Det går inte att skicka - antalet användare vars använda lagring ligger på eller över värdet då sändning förhindras, men under kvoten då både sändning och mottagning förhindras  <br/>  Det går inte att skicka/ta emot - antalet användare vars använda lagring ligger på eller över kvoten då både sändning och mottagning förhindras  <br/> |
|6.  <br/> | I diagrammet **Postlåda** är Y-axeln antalet användarpostlådor.  <br/>  I diagrammet **Lagring** är Y-axeln mängden lagringsutrymme som används av användarpostlådor i din organisation.  <br/>  I diagrammet **Kvot** är Y-axeln antalet användarpostlådor i varje lagringskvot.  <br/>  X-axeln i diagrammen Postlåda och Lagring är det valda datumintervallet för den här specifika rapporten.  <br/>  X-axeln i diagrammen för Kvot är kvotkategorin.  <br/> |
|7.  <br/> |Du kan filtrera diagram som du ser genom att markera ett objekt i förklaringen.  <br/> |
|8.  <br/> | Tabellen visar en uppdelning av postlådeanvändningen per användare. Du kan lägga till fler kolumner i tabellen.  <br/> **Användarnamn** är användarens e-postadress.  <br/> **Visningsnamn** är användarens fullständiga namn.  <br/> **Borttagen** refererar till den postlåda vars aktuella status är borttagen, men som var aktiv under en del av rapportens rapporteringsperiod.  <br/> **Borttagen den** är det datum postlådan togs bort.  <br/> **Skapad den** är det datum postlådan skapades.  <br/> **Datum för senaste aktivitet** refererar till det datum postlådan senast användes för att skicka eller läsa ett e-postmeddelande.  <br/> **Objektantal** refererar till det totala antalet objekt i postlådan.  <br/> **Använt lagringsutrymme (MB)** refererar till det totala använda lagringsutrymmet.  <br/> **Borttaget antal objekt** refererar till det totala antalet borttagna objekt i postlådan. <br/> **Borttagen artikelstorlek (MB)** refererar till den totala storleken på alla borttagna objekt i postlådan. <br/> **Kvot då varning utfärdas (MB)** refererar till lagringsgränsen då postlådans ägare får en varning om att lagringskvoten snart är nådd.  <br/> **Kvot då sändning förhindras (MB)** refererar till lagringsgränsen då postlådan inte längre får skicka e-postmeddelanden.  <br/> **Kvot då sändning/mottagning förhindras (MB)** refererar till lagringsgränsen då postlådan inte längre får skicka eller ta emot e-postmeddelanden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Läs avsnittet **Dölj användare i avsnittet Dölj i rapporterna** i [aktivitetsrapporterna i administrationscentret för Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.**  <br/> |
|||
   

