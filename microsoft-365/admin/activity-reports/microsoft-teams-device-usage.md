---
title: Enhetsanvändning för Microsoft Teams
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
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Få inblick i de Microsoft Teams som används i organisationen genom att hämta rapporten Microsoft Teams om appanvändning från Microsoft 365 Rapporter.
ms.openlocfilehash: 453b5767a6da1361ba8121fa2d49d9db8224aa68
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579632"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365 Rapporter i administrationscentret – Microsoft Teams enhetsanvändning

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Läs [översiktsavsnittet om rapporter](activity-reports.md). I appanvändningsrapporten för Microsoft Teams får du inblick i vilka Microsoft Teams-appar som används inom organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Så här visar du appanvändningsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I **listrutan Välj en** rapport väljer du Välj **Microsoft Teams** \> **Enhetsanvändning**.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Tolka appanvändningsrapporten för Microsoft Teams

Genom att titta på diagrammen **Användare** och **Fördelning** kan du få insyn i användarnas användning av Microsoft Teams-appar. 
  
![Microsoft 365 - Microsoft Teams appanvändning](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Microsoft Teams enhetsanvändning** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).  <br/> |
|2.  <br/> |Data i varje rapport täcker vanligtvis upp till de senaste 24 till 48 timmarna.  <br/> |
|3.  <br/> |I vyn **Användare** visas antalet unika användare dagligen per app.  <br/> |
|4.  <br/> |I vyn **Fördelning** visas antalet unika användare per app under den valda tidsperioden.  <br/> |
|5.  <br/> | I diagrammet **Användare** visar Y-axeln antalet användare per app.  <br/>  I diagrammet **Fördelning** visar Y-axeln antalet användare som använder den angivna appen.  <br/>  X-axeln i diagrammen visar det valda datumintervallet för den specifika rapporten.  <br/> |
|6.  <br/> |Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. Exempel: I diagrammet **Användare** väljer du **Windows**, **Mac,** **Samtal,** **Webb,** **Android-telefon** eller **Windows** telefon om du bara vill se den relaterade informationen. När du ändrar det här valet ändras inte informationen i rutnätstabellen.  <br/> ![Du kan filtrera Microsoft Teams av appanvändningsdiagram genom att välja apptyp.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | Listan över grupper som visas bestäms av totala uppsättningen grupper som fanns (inte togs bort) under den längsta (180 dagar) rapportperioden. Antal aktiviteter varierar beroende på vilka datum som väljs.  <br/> Obs! Du kanske inte ser alla objekt i listan nedan i kolumnerna förrän du lägger till dem.<br/> **Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.  <br/> **Datum för senaste aktivitet (UTC)** anger det senaste datum då användaren deltog i en Microsoft Teams-aktivitet i en app.  <br/> **Borttagen** anger om teamet har tagits bort. Om teamet har tagits bort, men det förekom aktiviteter under rapporteringsperioden visas det i tabellen med alternativet Borttagen angett till Sant.  <br/> **Borttaget datum** är det datum då teamet togs bort.  <br/> **Windows** markeras om användaren varit aktiv i en Windows-app under den angivna tidsperioden.  <br/> **Mac** markeras om användaren varit aktiv i en Mac-app under den angivna tidsperioden.  <br/> **Webb** markeras om användaren varit aktiv i en webbapp under den angivna tidsperioden.  <br/> **iOS** markeras om användaren varit aktiv i en iOS-app under den angivna tidsperioden.  <br/> **Android-telefon** markeras om användaren varit aktiv i en Android-telefonapp under den angivna tidsperioden.  <br/> **Windows-telefon** markeras om användaren varit aktiv i en Windows Phone-app under den angivna tidsperioden.  <br/>  Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Mer information **finns i avsnittet Hur döljer jag information på användarnivå?** i [Aktivitetsrapporter i Microsoft 365 administrationscenter](activity-reports.md).  <br/> |
|8.  <br/> |Välj **Kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera.  <br/> |
|||
   
  

