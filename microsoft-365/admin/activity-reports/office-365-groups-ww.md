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
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612002"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-rapporter i administrations Center – Microsoft 365-grupper

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I rapporten Microsoft 365 Groups kan du få insikter i gruppen med grupper i din organisation och se hur många grupper som skapas och används.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter.  
  
## <a name="how-to-get-to-the-groups-report"></a>Så här kommer du till gruppen rapporter

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>. 
2. Från instrument panelens start sida klickar du på knappen **Visa mer** på aktiva användare – Microsoft 365-appar eller aktiva användare-Microsoft 365-kort för att gå till sidan Office 365-rapporter.
  
## <a name="interpret-the-groups-report"></a>Tolka rapporten grupper

Du kan visa aktiveringarna i rapporten Office 365 genom att välja fliken **grupper aktivitet** .<br/>![Microsoft 365-rapporter – aktivitet i Microsoft Office 365-grupper.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Välj **Välj kolumner** för att lägga till eller ta bort kolumner i rapporten.  <br/> ![Aktivitets rapport för Office 365 – Välj kolumner](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 

|Objekt|Beskrivning|
|:-----|:-----|
|**Mät**|**Definition**|
|Grupp namn  <br/> |Namnet på gruppen.  <br/> |
|Deleted  <br/> |Antalet grupper som tagits bort. Om gruppen tagits bort, men uppvisade aktivitet under rapporteringsperioden visas det i tabellen om här flaggan är satt till sant.  <br/> |
|Grupp ägare  <br/> |Grupp ägarens namn.  <br/> |
|Datum för senaste aktivitet (UTC)  <br/> |Det senaste datum då ett meddelande togs emot av gruppen. -Det här är det senaste datumet en aktivitet inträffade i en e-postkonversation, Yammer eller webbplatsen.  <br/> |
|Type (Typ)  <br/> |Typ av grupp. Det kan vara en privat eller offentlig grupp.  <br/> |
|E-postmeddelanden mottagna i Exchange  <br/> |Antalet meddelanden som tagits emot av gruppen.|
|E-postmeddelanden i Exchange (totalt)  <br/> |Totalt antal objekt i gruppens post låda.  <br/> |
|Post lådans lagrings utrymme för Exchange (MB)  <br/> |Det lagrings utrymme som används av gruppens post låda. <br/>|
|SharePoint-filer (totalt)  <br/> |Antalet filer som lagras på SharePoint-gruppwebbplatser.  <br/> |
|SharePoint-filer (aktiva)  <br/> |Antalet filer i SharePoint-gruppwebbplatsen som har påverkat (visats eller ändrats, synkroniserats internt eller externt) under rapporterings perioden.  <br/> |
|Total webbplats lagring som används för SharePoint (MB)  <br/> |Mängden lagrings utrymme i MB som används under rapporterings perioden.  <br/> |
|Meddelanden i Yammer (anslaget)  <br/> |Antalet meddelanden som publicerats i Yammer-gruppen under rapporterings perioden.  <br/> |
|Meddelanden i Yammer (läsa)  <br/> |Antalet konversationer som lästs i Yammer-gruppen under rapporterings perioden.  <br/> |
|Meddelanden i Yammer (gillade)  <br/> |Antalet meddelanden som gillats i Yammer-gruppen under rapporterings perioden.  <br/> |
|Gruppen  <br/> |Antalet medlemmar i gruppen.  <br/> |
|Externa medlemmar |Antalet externa användare i gruppen.|
|||