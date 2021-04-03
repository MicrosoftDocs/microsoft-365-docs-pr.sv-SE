---
title: Microsoft 365-rapporter i administrationscentret – användning av Microsoft 365-appar
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
description: Läs om hur du får en rapport om Microsoft 365-appar för användning med instrumentpanelen Rapporter i Microsoft 365 i administrationscentret för Microsoft 365.
ms.openlocfilehash: 362697ba8dd40a12107e1b2d9ad6ef1bededda7d
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579584"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365-rapporter i administrationscentret – användning av Microsoft 365-appar

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).

 Du kan till exempel få information om aktiviteten för varje användare som har en licens för att använda Microsoft 365-appar genom att titta på deras aktivitet i apparna och hur de används på olika plattformar.


 > [!NOTE]
 > Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint- eller Skype för företag-administratör för att kunna se rapporter.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Öppna användningsrapporten för Microsoft 365-appar

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

 2. I **listrutan Välj en rapport** väljer du Användning **av Office 365**   \>  **Microsoft 365-appar.**

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Tolka användningsrapporten för Microsoft 365-appar

Du kan få en uppfattning om användarnas aktiviteter i Microsoft 365-appar genom att titta på **diagrammen Användare** **och** Plattform.

![Användningsrapport för Microsoft 365-appar](../../media/proplususagenumbers.png)

|Objekt|Beskrivning|
 |:-----|:-----|
 |1. <br/> |I **användningsrapporten för Microsoft 365-appar** kan du se trender för de senaste 7, 30, 90 eller 180 dagarna. Men om du väljer en viss dag i rapporten visar tabellen (7) data för de senaste 28 dagarna (inte från det datum då rapporten skapades). <br/> |
 |2. <br/> |Data i varje rapport täcker vanligtvis upp till de senaste sju dagarna. <br/> |
 |3. <br/> |Vyn **Användare** visar trenden för antalet aktiva användare för varje app – Outlook, Word, Excel, PowerPoint, OneNote och Teams. "Aktiva användare" är alla användare som utför alla avsiktliga åtgärder i dessa appar. <br/> |
 |4. <br/> |I **vyn** Plattformar visas trenden för aktiva användare i alla appar för varje plattform – Windows, Mac, Webben och Mobil. <br/> |
 |5.<br/>|I **diagrammet** Användare visar Y-axeln antalet unika aktiva användare för respektive app. I **diagrammet Plattformar**   är Y-axeln antalet unika användare för respektive plattform. X-axeln i båda diagrammen är det datum då en app användes på en viss plattform.<br/>|
 6.<br/>|Du kan filtrera serierna du ser i diagrammet genom att välja ett objekt i förklaringen. Exempel: I diagrammet **Användare väljer** du Outlook, Word, Excel, PowerPoint, OneDrive eller Teams om du bara vill se den relaterade informationen. När du ändrar det här valet ändras inte informationen i rutnätstabellen nedanför den.|
 |7.<br/>|I tabellen visas en uppdelning av data per användare. Du kan lägga till eller ta bort kolumner i tabellen. <br/><br/>**Användarnamn** är e-postadressen till den användare som utförde aktiviteten på Microsoft-appar.<br><br/>**Senaste aktiveringsdatum (UTC)** är det senaste datum då användaren aktiverade sin Microsoft 365 Apps-prenumeration.<br/><br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en avsiktlig aktivitet utfördes av användaren. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/><br/>Följande kolumner motsvarar varje program som identifierar om användaren varit aktiv i programmet under den valda perioden:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> Följande kolumner motsvarar varje plattform som identifierar om användaren var aktiv på den plattformen för en app (inom Microsoft 365-appar) under den valda perioden:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (webb)** <br>**Outlook (mobil)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (webb)**<br> **Word (mobil)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (webb)**<br> **Excel (mobil)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (webb)**<br> **PowerPoint (mobil)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (webb)**<br>**OneNote (mobil)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (webb)**<br>**Teams (mobila enheter)** |
 |8.<br/>|Välj ikonen **Hantera kolumner för** att lägga till eller ta bort kolumner i rapporten.|
 |9.<br/>|Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkla aggregeringar, sortering och filtrering för vidare analys. Om du har mindre än 100 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|
