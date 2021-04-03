---
title: Microsoft 365-rapporter i administrationscentret – Aktivitet i Yammer-grupper
f1.keywords:
- NOCSH
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
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Få information om antalet Yammer-grupper som skapas och används i organisationen och deras aktivitet i rapporten Aktivitet i Yammer-grupper.
ms.openlocfilehash: 7cd06c76b8a1a38eb7ebe1c45d099f7f554acdb3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579440"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365-rapporter i administrationscentret – Aktivitet i Yammer-grupper

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I rapporten Aktivitet i Yammer-grupper får du inblick i aktiviteten i Yammer-grupperna i organisationen och du kan se hur många Yammer-grupper som används.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Komma åt rapporten Aktivitet i Yammer-grupper

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I **listrutan Välj en** rapport väljer du **Aktivitet i** \> **Yammer-grupper.**
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Tolka rapporten Aktivitet i Yammer-grupper

Du kan få en överblick över aktiviteten i Yammer-grupper genom att titta på diagrammen **Grupper** och **Aktivitet**.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Aktivitet i Yammer-grupper** kan du se trender under de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna. <br/> |
|3.  <br/> |I vyn **Grupper** visas det totala antalet grupper som finns och hur många gruppkonversationsaktiviteter som utförts.  <br/> |
|4.  <br/> |I vyn **Aktivitet** visas hur många Yammer-meddelanden som har publicerats och gillats i grupper.  <br/> |
|5.  <br/> | I diagrammet **Grupper** är Y-axeln antalet grupper, totalt eller aktiva.  <br/>  I diagrammet **Aktivitet** är Y-axeln antalet för den angivna aktiviteten för Yammer-grupper.  <br/>  X-axeln i alla tre diagram är det valda datumintervallet för den specifika rapporten.  <br/> |
|6.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. I diagrammet Grupper kan du **till** exempel välja **Totalt eller** **Aktiv** summa och Aktiva ikoner om du bara vill se den ![ relaterade ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) informationen.   När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> |
|7.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längst (180 dagar) rapporterade tidsperioden. Antal meddelanden (mottagna meddelanden) är olika beroende på vilka datum som väljs.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/>**Gruppnamn** är namnet på gruppen.  <br/> **Gruppadministratör** är namnet på gruppadministratören eller ägaren.  <br/> **Borttagna** är antalet borttagna Yammer-grupper. Om gruppen tagits bort, men uppvisade aktivitet under rapporteringsperioden visas det i tabellen om här flaggan är satt till sant.  <br/> **Typ** är typen av grupp, offentlig eller privat.  <br/> **Ansluten till Office 365 anger** om Yammer-gruppen också är en Microsoft 365-grupp.  <br/> **Datum för senaste aktivitet** är det senaste datumet som ett meddelande lästs, publicerats eller gillats av gruppen.  <br/> **Medlemmar** är antalet medlemmar i gruppen.  <br/> **Publicerade** är antalet meddelanden som publicerats i Yammer-gruppen under rapporteringsperioden.  <br/> **Lästa** är antalet konversationer som lästs i Yammer-gruppen under rapporteringsperioden.  <br/> **Gillade** är antalet meddelanden som gillats i Yammer-gruppen under rapporteringsperioden. <br/> **Nätverksnamn** är det fullständiga namnet på nätverket som gruppen tillhör. <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information finns **i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i administrationscentret för Microsoft 365.](activity-reports.md)  <br/> |
|8.  <br/> |Välj **Kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Yammer groups activity - choose columns](../../media/c56c807f-fbc0-4d37-8bd3-e779bd0606a7.png)|
|9.  <br/> |Du kan också exportera rapportdata till en CsV-fil för Excel genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   

