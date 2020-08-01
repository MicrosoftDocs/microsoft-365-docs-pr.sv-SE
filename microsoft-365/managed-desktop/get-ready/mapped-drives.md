---
title: Förbereda mappade enheter för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e6311c0ad11d68c870b0c8185974b8913735e2a2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530181"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Förbereda mappade enheter för Microsoft Hanterat skrivbord

Många företagsmiljöer har äldre krav på mappade enheter så att deras användare eller team kan dela och lagra filer eller för lokala program. Microsoft rekommenderar inte användning av mappade enheter med Microsoft Managed Desktop. I stället rekommenderar vi att du moderniserar filåtkomstlösningarna enligt följande:
  
- Migrera mappade enheter som används av enskilda användare till OneDrive för företag. 
- Migrera mappade enheter som används av team för att dela filer till SharePoint Online. 
- Modernisera eller ersätta program som använder lokala filresurser för att ta bort det kravet.
  
Genom att modernisera dessa tjänster kan du få den bästa slutanvändarupplevelsen med Microsoft Managed Desktop. Microsoft FastTrack Services kan hjälpa dig att modernisera din miljö med hjälp av Microsoft Cloud Services. Du kan kontrollera om du är berättigad till FastTrack-tjänster på [Kvalificerade tjänster och abonnemang](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) och sedan kontakta dem direkt för att förbereda för Microsoft Managed Desktop. Bakgrund om FastTrack OneDrive för företag eller SharePoint Online-migrering finns i [Datamigrering](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Mappade enheter på Microsoft Managed Desktop
 
Om du inte kan ta bort eller ersätta mappade enheter för vissa användningsfall bör du skicka en supportbegäran i Microsoft Managed Desktop-administratörsportalen för att få dem distribuerade till Microsoft Managed Desktop-användare.
    
För en sådan begäran måste du ange följande information i supportbegäran: 

- Alla UNC-sökvägar till filresursplatser som måste mappas för Microsoft Managed Desktop-enheter 
- Användargrupper som kräver åtkomst till dessa filresursplatser 
- Alla specifika enhetsbeteckningar som måste tilldelas (om det behövs)

Till exempel:

| Enhetsbeteckning | UNC-sökväg | Användargrupp |
|--------------|----------|------------|
| X:  | \\\server\dela\Marknadsföring | ContosoMarketing |

Det är helt och hållet ditt ansvar att se till att användare och grupper har och har rätt behörighet att komma åt fildelningsplatser och att de lokala filtjänsterna förblir tillgängliga. Du bör också ta bort dina krav för sådana filresurser så snart som möjligt.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Så här har mappade enheter distribuerats i Microsoft Managed Desktop
 
Se till att mappade enheter inte kan undvikas och du har noggrant granskat kraven innan du skickar en servicebegäran. Följ sedan dessa steg:

1. Navigera till [Microsoft Managed Desktop-portalen](https://aka.ms/mmdportal).  
2. Skicka en supportbegäran med titeln "Mappad enhetsdistribution" via avsnittet **Support > supportbegäranden** och ange all information om filresurs som krävs.  
3. Microsoft Managed Desktop IT Operations kommer att ge råd, genom att använda uppdateringar för supportbegäran, när begäran har slutförts. Inledningsvis kommer den här konfigurationen endast att distribueras till enheter i testdistributionsgruppen.  
4. Du måste testa och bekräfta om konfigurationen som distribueras av Microsoft Managed Desktop IT Operations fungerar som förväntat. Svara med fliken Diskussion i supportbegäran för att meddela Microsoft Managed Desktop IT Operations när du har slutfört testningen.  
5. Microsoft Managed Desktop IT Operations-teamet distribuerar sedan konfigurationen till de andra distributionsgrupperna. 
