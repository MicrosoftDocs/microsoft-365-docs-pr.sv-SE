---
title: Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Läs om var du kan visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Teams och hur du vidtar åtgärder för dessa filer.
ms.openlocfilehash: 49c7e1668602a63b8b82339ad0cc7823146212a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807798"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams

[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från skadliga filer i dokumentbibliotek och gruppwebbplatser. När en skadlig fil identifieras blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den tills ytterligare åtgärder vidtas av organisationens säkerhetsteam. Läs den här artikeln om du vill lära dig hur du visar information om identifierade filer och vilka åtgärder som ska vidtas. 

För att kunna utföra de uppgifter som beskrivs i den här artikeln måste du ha de behörigheter som krävs [för Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visa rapporter med information om identifierade filer

Om du vill visa status och detaljerad information om filer som har upptäckts av Office 365 ATP kan du använda rapporten Status för hotskydd.
  
1. I [Office 365 &amp; Security Compliance Center](https://protection.office.com)väljer du **Status för rapporter** \> som skydd av **instrumentpanelen** \> **Threat Protection Status**.
    
2. Välj **Visa informationstabell**i det övre högra hörnet av rapporten .
    
3. Visa listan över filer som har upptäckts i rapporten.
    
4. Markera ett objekt i listan om du vill visa detaljerad information, inklusive åtgärder som vidtagits, filnamnet, filsökvägen med mera.
    
5. Välj fliken **Avancerad analys** om du vill visa information, till exempel observerat beteende och analysinformation. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visa och vidta åtgärder för filer i karantän

1. I Office 365 &amp; Security Compliance Center väljer du \> **Review** \> **Quarantine** **Hothanteringsgranskningskarantän** . (Du kan också [https://protection.office.com/quarantine](https://protection.office.com/quarantine)gå direkt till .)
    
2. I det övre vänstra hörnet ändrar du rullgardinsmenyn från **E-post** till **Filer**. Om listan med resultat innehåller för många objekt använder du **filterfunktionen** för att begränsa markeringen.
    
3. Markera ett objekt i listan om du vill visa detaljerad information, inklusive filens URL.
    
4. Välj en tillgänglig åtgärd.
    
  - Välj **Släpp fil** om du vill avblockera filen. 
    
    Välj **Skicka rapport till Microsoft** om du vill rapportera filen som ett falskt positivt till Microsoft. 
    
  - Välj **Hämta fil** om du vill undersöka filen ytterligare. 
    
  - Välj **Ta bort från karantän** om du vill ta bort filen från listan över objekt i karantän. Om du väljer det här alternativet måste du också ta bort filen från respektive bibliotek i SharePoint Online, OneDrive för företag eller Microsoft Teams. Det här alternativet avblockerar inte en fil från att öppnas eller delas. 
    
5. Välj **Stäng** om du vill stänga informationen för ett markerat objekt. 
  
  

