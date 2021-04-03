---
title: Microsoft 365-rapporter i administrationscentret – OneDrive för företag-användning
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 'Få information i användningsrapporten för OneDrive för företag om det totala antalet filer och lagring som används i organisationen. '
ms.openlocfilehash: 54a3b1e041ee6155b5ce89d6cd5bc73233d1f69b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579548"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporter i administrationscentret – OneDrive för företag-användning

På instrumentpanelen Rapporter **i** Microsoft 365 ser du en översikt över aktiviteter i organisationens produkter. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller Exchange-, SharePoint-, Teams-tjänst, Teams Communications- eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. På startsidan för instrumentpanelen klickar du på **knappen Visa** mer på OneDrive-kortet.
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan visa användningen i OneDrive-rapporten genom att välja **fliken** Användning.<br/>![Microsoft 365-rapporter – Microsoft OneDrive-användningsrapport.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Välj **Välj kolumner för** att lägga till eller ta bort kolumner i rapporten.  <br/> ![OneDrive-användningsrapport – välj kolumner](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Du kan också exportera rapportdata till en Excel-CSV-fil genom att välja **länken** Exportera. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Metrisk**|**Definition**|
|URL  <br/> |Webbadressen för användarens OneDrive. <br/> |
|Borttagen  <br/> |Borttagningsstatus för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> |
|Ägare  <br/> |Användarnamnet på den primära administratören för OneDrive.   <br/> |
|Ägarens huvudnamn  <br/> |E-postadressen till ägaren av OneDrive. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Det senaste datum då en filaktivitet utfördes på OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> |
|Filer  <br/> |Antalet filer på OneDrive. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer under tidsperioden.<br/> Obs! Om du tog bort filer under den angivna tidsperioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer i OneDrive. >  Borttagna användare kommer att finnas med i rapporter under 180 dagar.  <br/> |
|Använt lagringsutrymme (MB)  <br/> |Mängden lagringsutrymme som används på OneDrive i MB. |
|||