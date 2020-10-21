---
title: Microsoft 365-rapporter i administrations Center – OneDrive för företag-användning
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
description: 'Få en rapport om OneDrive för företag-användning om du vill veta hur många filer och lagrings utrymme som används i din organisation. '
ms.openlocfilehash: 3855c7d06d202ee4d0590fcf5b8ca758d8120133
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649865"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporter i administrations Center – OneDrive för företag-användning

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
OneDrive-kortet på instrumentpanelen ger till exempel en övergripande bild av värdet som du får från OneDrive för företag vad gäller det totala antalet filer och lagringsutrymmet som används i din organisation. Du kan sedan öka detaljnivån för att förstå trender för aktiva OneDrive-konton, hur många filer som användare interagerar med samt hur mycket lagring som används. Det ger dig även information om varje användares OneDrive.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hur får jag fram OneDrive-aktivitetsrapporten?

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på OneDrive-kortet.
  
## <a name="interpret-the-onedrive-usage-report"></a>Förstå användningsrapporten i OneDrive

Du kan visa användningen i OneDrive-rapporten genom att välja fliken **användning** .<br/>![Microsoft 365-rapporter – Microsoft OneDrive användnings rapport.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Rapport över OneDrive-användning – Välj kolumner](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
  
|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|:  <br/> |Webb adressen för användarens OneDrive. <br/> |
|Deleted  <br/> |Borttagnings statusen för OneDrive. Det tar minst 7 dagar för konton att markeras som borttagna.  <br/> |
|Postlådeägare  <br/> |Namnet på den primära administratören av OneDrive.   <br/> |
|Ägarens huvud namn  <br/> |E-postadressen för ägaren till OneDrive. <br/> |
|Datum för senaste aktivitet (UTC)  <br/> | Det senaste datum då en fil aktivitet utfördes i OneDrive. Om OneDrive-kontot inte haft någon filaktivitet är värdet tomt.  <br/> |
|Hjälpfiler  <br/> |Antalet filer i OneDrive. <br/>|
|Aktiva filer  <br/> | Antalet aktiva filer inom tids perioden.<br/> OBS! om filer togs bort under den angivna tids perioden för rapporten kan antalet aktiva filer som visas i rapporten vara större än det aktuella antalet filer i OneDrive. >  Borttagna användare kommer att finnas med i rapporter under 180 dagar.  <br/> |
|Använt lagrings utrymme (MB)  <br/> |Mängden lagrings utrymme som OneDrive använder i MB. |
|||