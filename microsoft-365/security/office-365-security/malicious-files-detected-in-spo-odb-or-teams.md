---
title: Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams
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
description: Lär dig var du kan visa information om skadliga filer som identifierats i SharePoint, OneDrive eller Teams och hur du vidtar åtgärder för dessa filer.
ms.openlocfilehash: 95f497c5be16d1ba1d4fa9fc57f0dd9650450414
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635406"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams

[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokumentbibliotek och gruppwebbplatser. När en skadlig fil upptäcks blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den förrän ytterligare åtgärder vidtas av organisationens säkerhetsteam. Läs den här artikeln om du vill lära dig hur du visar information om identifierade filer och vilka åtgärder som ska vidtas. 

För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha de behörigheter som krävs [för Säkerhetsefterlevnadscenter &amp; ](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visa rapporter med information om identifierade filer

Om du vill visa status och detaljerad information om filer som har identifierats av Office 365 ATP kan du använda rapporten Status för hotskydd.
  
1. Välj **Rapporter om** \> skydd mot **instrumentpanelsskydd** \> **Threat Protection Status**i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com).
    
2. I det övre högra hörnet av rapporten väljer du **Visa informationstabell**.
    
3. Visa listan över filer som har identifierats i rapporten.
    
4. Markera ett objekt i listan om du vill visa detaljerad information, inklusive vidtagna åtgärder, filnamnet, filsökvägen med mera.
    
5. Välj fliken **Avancerad analys** om du vill visa information, till exempel observerad beteende- och analysinformation. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visa och vidta åtgärder för filer i karantän

1. I Security &amp; Compliance Center väljer du **Review** \> **Karantän** **för granskning av hothantering** \> . (Du kan också [https://protection.office.com/quarantine](https://protection.office.com/quarantine)gå direkt till .)
    
2. I det övre vänstra hörnet ändrar du rullgardinsmenyn från **e-post** till **filer**. Om resultatlistan innehåller för många objekt använder du **funktionen Filter** för att begränsa markeringen.
    
3. Markera ett objekt i listan om du vill visa detaljerad information, inklusive filens URL.
    
4. Välj en tillgänglig åtgärd.
    
    - Välj **Släpp-fil** för att avblockera filen. 

      Välj **Skicka rapport till Microsoft** om du vill rapportera filen som ett falskt positivt till Microsoft. 

    - Välj **Hämta fil** för att undersöka filen ytterligare. 

    - Välj **Ta bort från karantänen** om du vill ta bort filen från listan över objekt i karantän. Om du väljer det här alternativet måste du också ta bort filen från respektive bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams. Det här alternativet avblockerar inte en fil från att öppnas eller delas. 
    
5. Välj **Stäng** om du vill stänga informationen för ett markerat objekt. 
  
  

