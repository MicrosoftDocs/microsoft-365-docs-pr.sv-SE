---
title: Visa information om skadliga filer som identifieras av Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Lär dig hur du kan visa information om skadliga filer som identifieras i SharePoint, OneDrive eller teams och hur du åtgärdar dessa filer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e6cd0363b546fad063290ae20e8c6c82fd6d0dea
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202001"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokument bibliotek och grupp webbplatser. När en skadlig fil identifieras blockeras den så att ingen kan öppna, kopiera, flytta eller dela den innan ytterligare åtgärder vidtas av organisationens säkerhets team. Läs den här artikeln om du vill veta mer om hur du visar information om upptäckta filer och vilka åtgärder som ska vidtas. 

För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha nödvändig [behörighet för säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visa rapporter med information om identifierade filer

Om du vill visa status och detaljerad information om filer som upptäckts av Office 365 ATP kan du använda status rapporten för hotets skydd.
  
1. Välj **rapport** [ &amp; ](https://protection.office.com) \> **Dashboard** \> **skydds status**för instrument panel för säkerhets kontroll.
    
2. I det övre högra hörnet i rapporten väljer du **tabellen Visa information**.
    
3. Visa listan över filer som upptäcktes i rapporten.
    
4. Välj ett objekt i listan för att visa detaljerad information, inklusive utförda åtgärder, fil namnet, fil Sök vägen och annat.
    
5. Välj fliken **Avancerad analys** för att visa information, till exempel observerat beteende och analys information. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visa och vidta åtgärder för filer i karantän

1. &amp;Välj **Threat Management** \> **granskning** \> **Quarantine**i Center för säkerhets kontroll. (Du kan också gå direkt till [https://protection.office.com/quarantine](https://protection.office.com/quarantine) .)
    
2. I det övre vänstra hörnet ändrar du den nedrullningsbara menyn från **e-post** till **filer**. Om resultat listan innehåller för många objekt använder du **filter** funktionen för att begränsa markeringen.
    
3. Välj ett objekt i listan för att visa detaljerad information, inklusive filens URL.
    
4. Välj en tillgänglig åtgärd.
    
    - Välj **släpp filen** för att häva blockeringen av filen. 

      Välj **Skicka rapport till Microsoft** för att rapportera filen som en falsk positiv till Microsoft. 

    - Välj **Ladda ner fil** för att undersöka filen. 

    - Välj **ta bort från karantän** för att ta bort filen från listan med objekt i karantän. Om du väljer det här alternativet måste du även ta bort filen från dess bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams. Det här alternativet avblockerar inte en fil från att öppnas eller delas. 
    
5. Välj **Stäng** för att stänga informationen för ett markerat objekt. 
  
  

