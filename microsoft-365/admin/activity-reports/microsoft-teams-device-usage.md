---
title: Enhetsanvändning för Microsoft Teams
f1.keywords:
- NOCSH
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
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Få insikter i de Microsoft Teams-appar som används i din organisation genom att hämta rapporten Microsoft Teams-programmet användning från Microsoft 365-rapporter.
ms.openlocfilehash: 9c96f4fce962b49081cc93ff802b1e2bc250ec98
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949114"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365-rapporter i administrations Center – användning av Microsoft Teams-enheter

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Läs [översiktsavsnittet om rapporter](activity-reports.md). I appanvändningsrapporten för Microsoft Teams får du inblick i vilka Microsoft Teams-appar som används inom organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Så här visar du appanvändningsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du  **Microsoft Teams** - \> **enhet**.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Tolka appanvändningsrapporten för Microsoft Teams

Genom att titta på diagrammen **Användare** och **Fördelning** kan du få insyn i användarnas användning av Microsoft Teams-appar. 
  
![Microsoft 365-rapporter – program användning för Microsoft Teams](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft Teams enhetsanvändning** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).  <br/> |
|2.  <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste 24 till 48 timmar.  <br/> |
|3.  <br/> |I vyn **Användare** visas antalet unika användare dagligen per app.  <br/> |
|4.  <br/> |I vyn **Fördelning** visas antalet unika användare per app under den valda tidsperioden.  <br/> |
|5.  <br/> | I diagrammet **Användare** visar Y-axeln antalet användare per app.  <br/>  I diagrammet **Fördelning** visar Y-axeln antalet användare som använder den angivna appen.  <br/>  X-axeln i diagrammen visar det valda datumintervallet för den specifika rapporten.  <br/> |
|18.6.  <br/> |Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **användare** väljer du till exempel **Windows**, **Mac**, **samtal**, **webb**, Android- **telefon**eller **Windows Phone** för att bara se informationen som hör till var och en. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> ![Du kan filtrera diagram för användning av Microsoft Teams-program genom att välja program typ.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|borttagning.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längsta (180 dagar) rapportperioden. Antal aktiviteter varierar beroende på vilka datum som väljs.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/> **Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> **Datum för senaste aktivitet (UTC)** anger det senaste datum då användaren deltog i en Microsoft Teams-aktivitet i en app.  <br/> **Borttagen** anger om teamet har tagits bort. Om teamet har tagits bort, men det förekom aktiviteter under rapporteringsperioden visas det i tabellen med alternativet Borttagen angett till Sant.  <br/> **Borttaget datum** är det datum då teamet togs bort.  <br/> **Windows** markeras om användaren varit aktiv i en Windows-app under den angivna tidsperioden.  <br/> **Mac** markeras om användaren varit aktiv i en Mac-app under den angivna tidsperioden.  <br/> **Webb** markeras om användaren varit aktiv i en webbapp under den angivna tidsperioden.  <br/> **iOS** markeras om användaren varit aktiv i en iOS-app under den angivna tidsperioden.  <br/> **Android-telefon** markeras om användaren varit aktiv i en Android-telefonapp under den angivna tidsperioden.  <br/> **Windows-telefon** markeras om användaren varit aktiv i en Windows Phone-app under den angivna tidsperioden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in **hur du döljer information om användar nivå?** i [aktivitets rapporterna i Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|8.2.  <br/> |Välj **kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
  

