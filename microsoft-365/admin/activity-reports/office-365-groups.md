---
title: Microsoft 365-rapporter i administrations Center – Microsoft 365-grupper
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Få en rapport från Microsoft 365-grupper om du vill veta mer om grupperna och deras aktiviteter.
ms.openlocfilehash: 1d329efa4fe7cdf12b6c7452b6480d237fb3d5c1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948994"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-rapporter i administrations Center – Microsoft 365-grupper

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I rapporten Microsoft 365 Groups kan du få insikter i gruppen med grupper i din organisation och se hur många grupper som skapas och används.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
  
## <a name="how-to-get-to-the-groups-report"></a>Så här kommer du till gruppen rapporter

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du aktivitet i **Office 365** - \> **grupper**.
  
## <a name="interpret-the-groups-report"></a>Tolka rapporten grupper

Du kan få en vy i grupp aktivitet genom att titta på **grupperna grupper**, **aktivitet**, **filer**och **lagring** . 
  
![Microsoft 365-rapporter – grupp aktiviteter](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft 365-grupper** kan du se trender under de senaste 7, 30, 90 eller 180 dagar. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |I vyn **grupper** visas det totala antalet grupper som fanns under en given dag och aktiva grupper på den dagen baserat på e-postkonversationer, Yammer-inlägg och SharePoint-filaktiviteter och SharePoint-sidor som visas.  <br/> |
|4.  <br/> |Vyn **Aktivitet** visar antalet gruppaktiviteter jämfört med gruppens arbetsbelastning. Du kan visa de Exchange-e-postmeddelanden som gruppostlådor i alla grupper sammanlagt tagit emot en given dag under rapporteringsperioden. Du kan också se meddelanden som publicerats, lästs in och gillats i Yammer-grupper som är kopplade till en grupp. <br/> |
|5.  <br/> |I vyn **filer** visas totalt antal och aktiva filer på alla grupp webbplatser som är kopplade till en grupp.  <br/> |
|18.6.  <br/> |Vyn **Lagring** visar använt lagringsutrymme för alla gruppostlådor och gruppwebbplatser.  <br/> |
|borttagning.  <br/> | I diagrammet **Grupper** är Y-axeln antalet grupper (som kan visas som totalt jämfört med aktiva).  <br/>  I diagrammet **aktivitet** är Y-axeln antalet gånger som en aktivitet utförts i grupper.  <br/>  I diagrammet **Filer** är Y-axeln antingen det totala antalet filer eller aktiva filer.  <br/>  I diagrammet **Lagring** är Y-axeln totalt lagringsutrymme som används av gruppostlådan eller webbplatsen.  <br/>  X-axeln i alla tre diagram är det valda datumintervallet för den specifika rapporten.  <br/> |
|8.2.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **grupper** kan du till exempel välja **Total** eller **aktiv** ![ Total och aktiva antal grupper ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) för att bara se informationen relaterad till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|9.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längst (180 dagar) rapporterade tidsperioden. Antal aktiviteter (e-postkonversationer, inlägg i Yammer och filaktiviteter på SharePoint) varierar beroende på valda datum.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Gruppnamn** är namnet på gruppen.  <br/> **Borttagna** är antalet borttagna grupper. Om gruppen tagits bort, men uppvisade aktivitet under rapporteringsperioden visas det i tabellen om här flaggan är satt till sant.  <br/> **Gruppägare** är namnet på den som äger gruppen.  <br/> **Datum för senaste aktivitet** är det senaste datum då ett meddelande togs emot av gruppen. -Det här är det senaste datumet en aktivitet inträffade i en e-postkonversation, Yammer eller webbplatsen.  <br/> **Typ** är grupptypen. Det kan vara en privat eller offentlig grupp.  <br/> **Medlemmar** är antalet medlemmar i gruppen.  <br/> **Externa medlemmar** är antalet externa användare i gruppen.  <br/> **Exchange** <br/> **Mottagna e-postmeddelanden** är antalet meddelanden som tagits emot av gruppen.  <br/> **Objektantal** är det totala antalet meddelanden i gruppens postlåda.  <br/> **Använt lagringsutrymme** är det lagringsutrymme som används av gruppens postlåda.  <br/> **SharePoint-filer** <br/> **Totalt antal filer** är antalet filer som lagras på SharePoint-gruppwebbplatser.  <br/> **Aktiva filer** är antalet filer i SharePoint-gruppwebbplatsen som har påverkat (visas eller ändras, synkroniseras, delats internt eller externt) under rapporteringsperioden  <br/> **Använt lagringsutrymme** är lagringsutrymme i MB som används under rapporteringsperioden.  <br/> **Yammer-meddelanden** <br/> **Publicerade** är antalet meddelanden som publicerats i Yammer-gruppen under rapporteringsperioden.  <br/> **Lästa** är antalet konversationer som lästs i Yammer-gruppen under rapporteringsperioden.  <br/> **Gillade** är antalet meddelanden som gillats i Yammer-gruppen under rapporteringsperioden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|10.3  <br/> |Välj eller tryck på knappen **fler åtgärder** ![ Mobile OWA fler åtgärder ](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) bredvid en kolumn rubrik för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport över grupper – Välj kolumner](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|Nr  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

