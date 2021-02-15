---
title: Microsoft 365-rapporter i administrationscentret – Enhetsanvändning i Microsoft Teams
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Få inblick i vilka Microsoft Teams-appar som används i organisationen genom att hämta appanvändningsrapporten för Microsoft Teams från Microsoft 365-rapporter.
ms.openlocfilehash: 54219b060767193e711c839d25780dd3b4a618bf
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233440"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365-rapporter i administrationscentret – Enhetsanvändning i Microsoft Teams

Instrumentpanelen Microsoft **365-rapporter** visar en översikt över aktiviteter för produkter i din organisation. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Läs [översiktsavsnittet om rapporter](activity-reports.md). I appanvändningsrapporten för Microsoft Teams får du inblick i vilka Microsoft Teams-appar som används inom organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Så här visar du appanvändningsrapporten för Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa mer** på Microsoft Teams aktivitetskort.
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Tolka appanvändningsrapporten för Microsoft Teams

Du kan visa enhetens användning i Teams-rapporten genom att välja **fliken Enhetsanvändning.**<br/>![Microsoft 365-rapporter – Enhetsanvändning i Microsoft Teams.](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport om användarenhet för Teams – välj kolumner](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

Du kan också exportera rapportdata till en CSV-fil för Excel genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 

I rapporten **Microsoft Teams enhetsanvändning** visas trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades).
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|Användarnamn  <br/> |Användarens visningsnamn.  <br/> |
|Windows  <br/> |Väljs om användaren var aktiv i Teams skrivbordsklient på en Windows-baserad dator.  <br/> |
|Mac  <br/> |Markerad om användaren var aktiv i Teams skrivbordsklient på en macOS-dator.  <br/> |
|iOS  <br/> |Markerad om användaren var aktiv på Teams mobila klient för iOS.  <br/> |
|Android-telefon  <br/> | Markerad om användaren var aktiv i Teams mobila klient för Android.  <br/> |
|Chrome OS  <br/> |Markerad om användaren var aktiv i Teams skrivbordsklient på en ChromeOS-dator.|
|Linux  <br/> | Väljs om användaren var aktiv i Teams skrivbordsklient på en Linux-dator.  <br/> |
|Webb  <br/> |Väljs om användaren var aktiv i Teams webbklient på enheter.|
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum (UTC) då användaren deltog i en Teams-aktivitet.  <br/> |
|Är licensierad|Väljs om användaren är licensierad att använda Teams.|
|||