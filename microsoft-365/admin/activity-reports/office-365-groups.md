---
title: Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper
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
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Få en Microsoft 365-grupprapport som visar grupperna och deras aktiviteter.
ms.openlocfilehash: d123e3beb55ba6e636084fabe995f4dd0ff56707
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939144"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I Microsoft 365-grupprapporten kan du få kunskap om gruppernas aktivitet i organisationen och se hur många grupper som skapas och används.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
  
## <a name="how-to-get-to-the-groups-report"></a>Så här kommer du åt grupprapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

2. Bland alternativen väljer du **Visa mer** under Aktiva användare – **Microsoft 365-tjänster.**
3. I **listrutan Välj en** rapport väljer du Aktivitet **i Office 365-grupper.** \> 
  
## <a name="interpret-the-groups-report"></a>Tolka grupprapporten

Du kan få en uppfattning om gruppaktivitet genom att titta på **diagrammen** **Grupper,** **Aktivitet,** Filer **och Lagring.** 
  
![Microsoft 365-rapporter – gruppaktiviteter](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I **rapporten Microsoft 365-grupper** kan du se trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |I **vyn** Grupper visas det totala antalet grupper som fanns en viss dag, och aktiva grupper den dagen baserat på e-postkonversationer, Yammer-inlägg och filaktiviteter på SharePoint och visade SharePoint-sidor.  <br/> |
|4.  <br/> |Vyn **Aktivitet** visar antalet gruppaktiviteter jämfört med gruppens arbetsbelastning. Du kan visa de Exchange-e-postmeddelanden som gruppostlådor i alla grupper sammanlagt tagit emot en given dag under rapporteringsperioden. Du kan också se meddelanden som publicerats, lästs och gillats i Yammer-grupper som är kopplade till en grupp. <br/> |
|5.  <br/> |I **vyn** Filer visas det totala antalet filer och antalet aktiva filer på alla gruppwebbplatser som är kopplade till en grupp.  <br/> |
|6.  <br/> |Vyn **Lagring** visar använt lagringsutrymme för alla gruppostlådor och gruppwebbplatser.  <br/> |
|7.  <br/> | I diagrammet **Grupper** är Y-axeln antalet grupper (som kan visas som totalt jämfört med aktiva).  <br/>  I diagrammet **Aktivitet** är Y-axeln antalet gånger en aktivitet utförts i grupper.  <br/>  I diagrammet **Filer** är Y-axeln antingen det totala antalet filer eller aktiva filer.  <br/>  I diagrammet **Lagring** är Y-axeln totalt lagringsutrymme som används av gruppostlådan eller webbplatsen.  <br/>  X-axeln i alla tre diagram är det valda datumintervallet för den specifika rapporten.  <br/> |
|8.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Grupper kan du **till** exempel välja **Totalt** eller **Aktivt** totalt och Aktivt antal grupper om du bara vill se den ![ relaterade ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) informationen. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|9.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längst (180 dagar) rapporterade tidsperioden. Antal aktiviteter (e-postkonversationer, inlägg i Yammer och filaktiviteter på SharePoint) varierar beroende på valda datum.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Gruppnamn** är namnet på gruppen.  <br/> **Borttagna** är antalet borttagna grupper. Om gruppen tagits bort, men uppvisade aktivitet under rapporteringsperioden visas det i tabellen om här flaggan är satt till sant.  <br/> **Gruppägare** är namnet på den som äger gruppen.  <br/> **Datum för senaste** aktivitet är det senaste datum som ett meddelande togs emot av gruppen. Det här är det senaste datumet som en aktivitet inträffade i en e-postkonversation, Yammer eller på webbplatsen.  <br/> **Typ** är grupptypen. Det kan vara en privat eller offentlig grupp.  <br/> **Medlemmar** är antalet medlemmar i gruppen.  <br/> **Externa medlemmar** är antalet externa användare i gruppen.  <br/> **Exchange** <br/> **Mottagna e-postmeddelanden** är antalet meddelanden som tagits emot av gruppen.  <br/> **Objektantal** är det totala antalet meddelanden i gruppens postlåda.  <br/> **Använt lagringsutrymme** är det lagringsutrymme som används av gruppens postlåda.  <br/> **SharePoint-filer** <br/> **Totalt antal filer** är antalet filer som lagras på SharePoint-gruppwebbplatser.  <br/> **Aktiva filer** är antalet filer i SharePoint-gruppwebbplatsen som har påverkat (visas eller ändras, synkroniseras, delats internt eller externt) under rapporteringsperioden  <br/> **Använt lagringsutrymme** är lagringsutrymme i MB som används under rapporteringsperioden.  <br/> **Yammer-meddelanden** <br/> **Publicerade** är antalet meddelanden som publicerats i Yammer-gruppen under rapporteringsperioden.  <br/> **Lästa** är antalet konversationer som lästs i Yammer-gruppen under rapporteringsperioden.  <br/> **Gillade** är antalet meddelanden som gillats i Yammer-gruppen under rapporteringsperioden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information finns **i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i administrationscentret för Microsoft 365.](activity-reports.md)  <br/> |
|10,  <br/> |Välj eller tryck **på knappen Fler** åtgärder Mobile ![ OWA Fler åtgärder bredvid en ](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) kolumnrubrik för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Grupprapport – välj kolumner](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|11,  <br/> |Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||


