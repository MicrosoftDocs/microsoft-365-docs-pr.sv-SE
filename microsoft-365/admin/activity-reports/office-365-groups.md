---
title: Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper
ms.author: sirkkuw
author: Sirkkuw
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
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Hämta en Microsoft 365-grupprapport om du vill veta om grupperna och deras aktiviteter.
ms.openlocfilehash: f1d1c333946f20ecfb76223d79a38e1a18783550
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516859"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I rapporten Microsoft 365 groups kan du få insikter om aktiviteten i grupper i organisationen och se hur många grupper som skapas och används.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.  
  
## <a name="how-to-get-to-the-groups-report"></a>Så här kommer du till grupprapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **aktivitet**för **Välj** \> en rapport i listrutan Välj **en rapport** .
  
## <a name="interpret-the-groups-report"></a>Tolka grupprapporten

Du kan hämta en vy i gruppaktiviteten genom att titta på diagrammen **Grupper,** **Aktivitet,** **Filer**och **Lagring.** 
  
![Microsoft 365-rapporter - grupperaktiviteter](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|||
|:-----|:-----|
|1.  <br/> |**Microsoft 365-grupprapporten** kan visas för trender under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i tabellen (7) i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Uppgifterna i varje rapport omfattar vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |Vyn **Grupper** visar ett totalt antal grupper som fanns på en viss dag och aktiva grupper den dagen baserat på e-postkonversationer, Yammer-inlägg och SharePoint-filaktiviteter och SharePoint-sidor visade.  <br/> |
|4.  <br/> |Vyn **Aktivitet** visar antalet gruppaktiviteter jämfört med gruppens arbetsbelastning. Du kan visa de Exchange-e-postmeddelanden som gruppostlådor i alla grupper sammanlagt tagit emot en given dag under rapporteringsperioden. Du kan också se meddelanden som har publicerats, läst och gillats i Yammer-grupperna som är associerade med en grupp. <br/> |
|5.  <br/> |I **filvyn** visas antalet summa och aktiva filer på alla gruppwebbplatser som är associerade med en grupp.  <br/> |
|6.  <br/> |Vyn **Lagring** visar använt lagringsutrymme för alla gruppostlådor och gruppwebbplatser.  <br/> |
|7.  <br/> | I diagrammet **Grupper** är Y-axeln antalet grupper (som kan visas som totalt jämfört med aktiva).  <br/>  I **aktivitetsdiagrammet** är Y-axeln det antal gånger en aktivitet utfördes i grupper.  <br/>  I diagrammet **Filer** är Y-axeln antingen det totala antalet filer eller aktiva filer.  <br/>  I diagrammet **Lagring** är Y-axeln totalt lagringsutrymme som används av gruppostlådan eller webbplatsen.  <br/>  X-axeln i alla tre diagram är det valda datumintervallet för den specifika rapporten.  <br/> |
|8.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **Grupper** väljer du till exempel **Totalt** eller](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) **Aktivt** ![totalt och Aktivt antal grupper om du bara vill visa information som är relaterad till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|9.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längst (180 dagar) rapporterade tidsperioden. Antal aktiviteter (e-postkonversationer, inlägg i Yammer och filaktiviteter på SharePoint) varierar beroende på valda datum.  <br/> Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Gruppnamn** är namnet på gruppen.  <br/> **Borttagna** är antalet borttagna grupper. Om gruppen tagits bort, men uppvisade aktivitet under rapporteringsperioden visas det i tabellen om här flaggan är satt till sant.  <br/> **Gruppägare** är namnet på den som äger gruppen.  <br/> **Senaste aktivitetsdatum** är det senaste datumet då ett meddelande togs emot av gruppen. - Detta är det senaste datumet då en aktivitet inträffade i en e-postkonversation, Yammer eller webbplatsen.  <br/> **Typ** är grupptypen. Det kan vara en privat eller offentlig grupp.  <br/> **Medlemmar** är antalet medlemmar i gruppen.  <br/> **Externa medlemmar** är antalet externa användare i gruppen.  <br/> **Exchange** <br/> **Mottagna e-postmeddelanden** är antalet meddelanden som tagits emot av gruppen.  <br/> **Objektantal** är det totala antalet meddelanden i gruppens postlåda.  <br/> **Använt lagringsutrymme** är det lagringsutrymme som används av gruppens postlåda.  <br/> **SharePoint-filer** <br/> **Totalt antal filer** är antalet filer som lagras på SharePoint-gruppwebbplatser.  <br/> **Aktiva filer** är antalet filer i SharePoint-gruppwebbplatsen som har påverkat (visas eller ändras, synkroniseras, delats internt eller externt) under rapporteringsperioden  <br/> **Använt lagringsutrymme** är lagringsutrymme i MB som används under rapporteringsperioden.  <br/> **Yammer-meddelanden** <br/> **Publicerade** är antalet meddelanden som publicerats i Yammer-gruppen under rapporteringsperioden.  <br/> **Lästa** är antalet konversationer som lästs i Yammer-gruppen under rapporteringsperioden.  <br/> **Gillade** är antalet meddelanden som gillats i Yammer-gruppen under rapporteringsperioden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|10,  <br/> |Markera eller **More Actions** tryck ![på Knappen Fler](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) åtgärder Mobil OWA Fler åtgärder bredvid en kolumnrubrik för att lägga till eller ta bort kolumner från rapporten.  <br/> ![Grupprapport - välj kolumner](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|11,  <br/> |Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

