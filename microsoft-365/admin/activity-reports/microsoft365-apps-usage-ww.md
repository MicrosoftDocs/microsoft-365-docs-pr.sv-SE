---
title: Microsoft 365-rapporter i administrations Center – användning av Microsoft 365-appar
ms.author: sirkkuw
author: sirkkuw
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
description: Lär dig hur du skaffar en Microsoft 365-app för användnings rapport med instrument panelen för Microsoft 365-rapporter i Microsoft 365 Admin Center.
ms.openlocfilehash: 0c30cee0c1abd76553d3adfebebb8fe38e92c56a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611983"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365-rapporter i administrations Center – användning av Microsoft 365-appar

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).

 Du kan till exempel förstå aktiviteten för varje användare som är licensierad för att använda Microsoft 365-appar genom att titta på deras aktivitet bland apparna och hur de används mellan olika plattformar.


 > [!NOTE]
 > Du måste vara global administratör, global läsare eller rapporter läsare i Microsoft 365 eller en Exchange-, SharePoint-eller Skype för företag-administratör för att se rapporter.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Så här kommer du till rapporten om användning av Microsoft 365-appar

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på kortet aktiva användare-Microsoft 365-program.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Tolka rapport om användning av Microsoft 365-appar

Du kan få en vy i användarens Microsoft 365-program-aktivitet genom att titta på **användarna** och **plattforms** diagrammen.

![Microsoft 365 program rapport](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Objekt|Beskrivning|
 |:-----|:-----|
 |1. <br/> |**Användnings rapporten för Microsoft 365-apparna** kan ses för trender under de senaste 7, 30, 90 eller 180 dagar. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades). <br/> |
 |2. <br/> |Informationen i varje rapport täcker vanligt vis upp till de senaste sju dagarna. <br/> |
 |3. <br/> |Vyn **användare** visar trenden för antalet aktiva användare för varje app – Outlook, Word, Excel, PowerPoint, OneNote och Teams. "Aktiva användare" är alla som utför avsiktliga åtgärder i dessa program. <br/> |
 |4. <br/> |Vyn **plattformar** visar trenden för aktiva användare i alla program för varje plattform – Windows, Mac, Internet och mobil. <br/> |
 |5.<br/>|I diagrammet **användare** är Y-axeln antalet unika aktiva användare för respektive app. I diagrammet **plattformar**   är Y-axeln antalet unika användare för respektive plattform. X-axeln i båda diagrammen är det datum då ett program användes på en viss plattform.<br/>|
 18.6.<br/>|Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet **användare** väljer du till exempel Outlook, Word, Excel, PowerPoint, OneDrive eller teams för att bara se informationen som hör till var och en. Om du ändrar den här markeringen ändras inte informationen i rutnäts tabellen nedanför den.|
 |borttagning.<br/>|I tabellen visas en uppdelning av data per användare. Du kan lägga till eller ta bort kolumner i tabellen. <br/><br/>**Username** är e-postadressen för den användare som utförde aktiviteten på Microsoft-appar.<br><br/>**Senaste aktiverings datum (UTC)** är det senaste datum då användaren aktiverade prenumerationen på Microsoft 365-apparna.<br/><br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en avsiktlig aktivitet utfördes av användaren. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/><br/>De andra kolumnerna anger om användaren varit aktiv på den plattformen för den programmet (i Microsoft 365-appar) i den valda perioden. |
 |8.2.<br/>|Välj ikonen **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.|
 |9.<br/>|Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Detta exporterar data för alla användare och gör att du kan utföra enkel agg regering, sortering och filtrering för ytterligare analyser. Om du har färre än 100 användare kan du sortera och filtrera i tabellen i rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|
