---
title: Microsoft 365 Rapporter i administrationscentret – OneDrive för företag användning
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
description: 'Få information OneDrive för företag användningsrapport och få information om det totala antalet filer och lagring som används i organisationen. '
ms.openlocfilehash: 20b9ce6aff01942c23c0f8a98234432ea54d5953
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242055"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 Rapporter i administrationscentret – OneDrive för företag användning

På Microsoft 365 **Rapporter** ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på OneDrive kort.
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan visa användningen i OneDrive genom att välja **fliken** Användning.<br/>![Microsoft 365 – Microsoft OneDrive användningsrapport.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![OneDrive användningsrapport – välj kolumner](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Du kan också exportera rapportdata till en Excel .csv fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|URL  <br/> |Webbadressen till användarens OneDrive. <br/> |
|Borttagen  <br/> |Borttagningsstatus för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> |
|Ägare  <br/> |Användarnamnet på den primära administratören för OneDrive.   <br/> |
|Ägarens huvudnamn  <br/> |E-postadressen till ägaren av OneDrive. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Det senaste datum då en filaktivitet utfördes i OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> |
|Filer  <br/> |Antalet filer i OneDrive. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer under tidsperioden.<br/> Obs! Om du tog bort filer under den angivna tidsperioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer i OneDrive. >  Borttagna användare kommer att finnas med i rapporter under 180 dagar.  <br/> |
|Storage (MB)  <br/> |Mängden lagringsutrymme som används OneDrive MB. |
|||