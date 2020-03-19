---
title: Förbereda mappade enheter för Microsoft Managed Desktop
description: Viktiga steg för att se till att
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8bdbbefb1fc3bfff324787eedb497afe781184f0
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "42806452"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Förbereda mappade enheter för Microsoft Managed Desktop

Många företagsmiljöer har äldre krav för mappade enheter så att användarna eller teamen kan dela och lagra filer eller för lokala program. Microsoft rekommenderar inte användning av mappade enheter med Microsoft Managed Desktop. I stället rekommenderar vi att du moderniserar yor-filåtkomstlösningar enligt följande:
  
- Migrera mappade enheter som används av enskilda användare till OneDrive för företag. 
- Migrera mappade enheter som används av team för att dela filer till SharePoint Online. 
- Modernisera eller ersätta alla program som använder lokala filresurser för att ta bort detta krav.
  
Genom att modernisera dessa tjänster kan du göra det möjligt att få den bästa slutanvändarupplevelsen med Microsoft Managed Desktop. Microsoft FastTrack Services kan hjälpa dig att modernisera din miljö med hjälp av Microsoft Cloud Services. Du kan kontrollera om du är berättigad till [FastTrack-tjänster](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) på kvalificerade tjänster och abonnemang och sedan kontakta dem direkt för att förbereda för Microsoft Managed Desktop. Om du har bakgrund om FastTrack OneDrive för företag eller SharePoint Online migrering finns i [Datamigrering](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Mappade enheter på Microsoft Managed Desktop
 
Om du inte kan ta bort eller ersätta mappade enheter för vissa användningsfall bör du skicka en supportbegäran i microsoft managed desktop-administratörsportalen för att få dem distribuerade till Användare på Microsoft Managed Desktop.
    
För en sådan begäran måste du ange följande information i supportbegäran: 

- Alla UNC-sökvägar till filresursplatser som måste mappas för Microsoft Managed Desktop-enheter 
- Användargrupper som kräver åtkomst till dessa filresursplatser 
- Alla specifika enhetsbeteckningar som måste tilldelas (om det behövs)

Till exempel:

| Enhetsbeteckning | UNC-sökväg | Användargrupp |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing (på 85) |

Det är helt och hållet ditt ansvar att se till att användare och grupper har och behålla rätt behörighet för att komma åt fildelningsplatser och att de lokala filtjänsterna förblir tillgängliga. Du bör också ta bort dina krav för sådana filresurser så snart som möjligt.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Så här distribueras mappade enheter på Microsoft Managed Desktop
 
Kontrollera att mappade enheter inte kan undvikas och du noggrant har granskat kraven innan du skickar en servicebegäran. Följ sedan dessa steg:

1. Navigera till [Portalen för Hanterade skrivbord i Microsoft](https://aka.ms/mmdportal).  
2. Skicka en supportbegäran med titeln "Mappad enhetsdistribution" via avsnittet **Support > Support-begäranden** och ange alla nödvändiga filresursdetaljer.  
3. Microsoft Managed Desktop IT-åtgärder kommer att ge råd, med hjälp av supportuppdateringar, när begäran har slutförts. Inledningsvis distribueras den här konfigurationen endast till enheter i gruppen Testa distribution.  
4. Du måste testa och bekräfta om konfigurationen som distribueras av Microsoft Managed Desktop IT-driften fungerar som förväntat. Svara med fliken Diskussion i supportbegäran om att meddela Microsoft Managed Desktop IT-åtgärder när du har slutfört testningen.  
5. Microsoft Managed Desktop IT Operations-teamet distribuerar sedan konfigurationen till de andra distributionsgrupperna. 
