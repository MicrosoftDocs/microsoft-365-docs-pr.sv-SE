---
title: Microsoft 365-rapporter i administrations Center – använde brev Låde användning
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
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Lär dig hur du får en rapport om hur du kan få information om användarnas aktiviteter med en post låda.
ms.openlocfilehash: 8d942f507c1e3102f909fb33eb16e00f7ebf05ea
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126573"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-rapporter i administrations Center – använde brev Låde användning

**Rapporten om användning av post lådan** innehåller information om användare med en post låda och aktivitetens aktivitets nivå baserat på e-postmeddelandet skicka, läsa, skapa avtalad tid, skicka möte, acceptera möte, avböja möte och avsluta Mötes aktivitet. Du får även information om hur mycket lagringsutrymme som har förbrukats av varje användarpostlåda och hur många av dem som närmar sig lagringskvotens gräns. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Så här kommer du åt rapporten om postlådeanvändning

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

2. Välj **Visa mer** under **aktiva användare – Microsoft 365-tjänster**. 
3. I list rutan **aktiva användare** väljer du Använd användning av **Exchange** - \> **postlåda**.
  
## <a name="interpret-the-mailbox-usage-report"></a>Tolka rapporten om postlådeanvändning

Du kan få en inblick i organisationens **Postlådeanvändning** genom att titta på diagrammen **Postlåda**, **Lagring** och **Kvot**. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Postlådeanvändning** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |Postlådediagrammet visar det totala antalet användarpostlådor i organisationen och hur många som är aktiva på en viss dag under rapportperioden. En användarpostlåda anses vara aktiv om någon av följande aktiviteter har utförts: skicka e-post, läsa e-post, skapa avtalad tid, skicka möte, acceptera möte, avböja möte eller ställa in ett möte.  <br/> |
|4.  <br/> |Diagrammet **Lagring** visar hur stort lagringsutrymme som används i din organisation. Lagrings diagrammet innehåller inte Arkiv post lådor. Mer information om automatisk utökande arkivering finns i Översikt över [obegränsad arkivering i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving).<br/> |
|5.  <br/> | Diagrammet **Kvot** visar antalet användarpostlådor i varje kvotkategori. Det finns fyra kvotkategorier:  <br/>  Bra - antal användare vars använda lagring ligger under kvotvärdet då varning utfärdas.  <br/>  Varning - antalet användare vars använda lagring ligger på eller över värdet då varning utfärdas, men under kvoten då sändning förhindras  <br/>  Det går inte att skicka - antalet användare vars använda lagring ligger på eller över värdet då sändning förhindras, men under kvoten då både sändning och mottagning förhindras  <br/>  Det går inte att skicka/ta emot - antalet användare vars använda lagring ligger på eller över kvoten då både sändning och mottagning förhindras  <br/> |
|18.6.  <br/> | I diagrammet **Postlåda** är Y-axeln antalet användarpostlådor.  <br/>  I diagrammet **Lagring** är Y-axeln mängden lagringsutrymme som används av användarpostlådor i din organisation.  <br/>  I diagrammet **Kvot** är Y-axeln antalet användarpostlådor i varje lagringskvot.  <br/>  X-axeln i diagrammen Postlåda och Lagring är det valda datumintervallet för den här specifika rapporten.  <br/>  X-axeln i diagrammen för Kvot är kvotkategorin.  <br/> |
|borttagning.  <br/> |Du kan filtrera diagram som visas genom att markera ett objekt i förklaringen.  <br/> |
|8.2.  <br/> | Tabellen visar en uppdelning av postlådeanvändningen per användare. Du kan lägga till fler kolumner i tabellen.  <br/> **Användarnamn** är användarens e-postadress.  <br/> **Visningsnamn** är användarens fullständiga namn.  <br/> **Borttagen** refererar till den postlåda vars aktuella status är borttagen, men som var aktiv under en del av rapportens rapporteringsperiod.  <br/> **Borttagen den** är det datum postlådan togs bort.  <br/> **Skapad den** är det datum postlådan skapades.  <br/> **Datum för senaste aktivitet** refererar till det datum postlådan senast användes för att skicka eller läsa ett e-postmeddelande.  <br/> **Objektantal** refererar till det totala antalet objekt i postlådan.  <br/> **Använt lagringsutrymme (MB)** refererar till det totala använda lagringsutrymmet.  <br/> **Antal borttagna objekt** refererar till det totala antalet borttagna objekt i post lådan. <br/> **Borttaget objekt storlek (MB)** syftar på total storleken på alla borttagna objekt i post lådan. <br/> **Kvot då varning utfärdas (MB)** refererar till lagringsgränsen då postlådans ägare får en varning om att lagringskvoten snart är nådd.  <br/> **Kvot då sändning förhindras (MB)** refererar till lagringsgränsen då postlådan inte längre får skicka e-postmeddelanden.  <br/> **Kvot då sändning/mottagning förhindras (MB)** refererar till lagringsgränsen då postlådan inte längre får skicka eller ta emot e-postmeddelanden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Ta en titt på ikonen **Dölj användare i avsnittet rapporter** i [aktivitets rapporterna i administrations centret för Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken.  <br/> |
|||
   
