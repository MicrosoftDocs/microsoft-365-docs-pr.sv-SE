---
title: Förbereda mappade enheter för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att användare kan komma åt data på mappade enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574575"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Förbereda mappade enheter för Microsoft Hanterat skrivbord

Många företagsmiljöer har äldre krav för mappade enheter för att deras användare eller team ska kunna dela och lagra filer eller för lokala program. Microsoft rekommenderar inte att du använder mappade enheter med Microsoft Managed Desktop. I stället rekommenderar vi att du moderniserar dina filåtkomstlösningar på följande sätt:
  
- Migrera mappade enheter som används av enskilda användare till OneDrive för företag. 
- Migrera mappade enheter som används av grupper för att dela filer till SharePoint Online. 
- Modernisera eller ersätt alla program som använder lokala filresurser för att ta bort det kravet.
  
Om du moderniseraer de här tjänsterna får du en så bra användarupplevelse som möjligt med Microsoft Managed Desktop. Microsoft FastTrack-tjänster kan hjälpa dig att modernisera miljön med hjälp av Microsofts molntjänster. Du kan kontrollera om du är berättigad till FastTrack-tjänster hos [Kvalificerade](/fasttrack/m365-eligible-services-and-plans) tjänster och abonnemang och sedan kontakta dem direkt för att förbereda dig för Microsoft Managed Desktop. Mer information om FastTrack-migrering av OneDrive för företag eller SharePoint Online finns i [Datamigrering.](/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Mappade enheter på Microsoft Managed Desktop
 
Om du inte kan ta bort eller ersätta mappade enheter i vissa användningsfall, bör du skicka en supportbegäran i administrationsportalen för Microsoft Managed Desktop så att de distribueras till användare av Microsoft Managed Desktop.
    
För en sådan begäran måste du ange följande information i supportbegäran: 

- Alla UNC-sökvägar till filresursplatser som måste mappas för Microsoft Managed Desktop-enheter 
- Användargrupper som kräver åtkomst till dessa platser för filresursen 
- Alla specifika enhetsbeteckningar som måste tilldelas (om det behövs)

Till exempel:

| Enhetsbeteckning | UNC-sökväg | Användargrupp |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Det är helt ditt ansvar att säkerställa att användare och grupper har och behåller rätt behörighet för att komma åt filresursplatser och att de lokala filtjänsterna förblir tillgängliga. Dessutom bör du ta bort kraven för sådana filresurser så snart som möjligt.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Så här har du mappade enheter distribuerat i Microsoft Managed Desktop
 
Se till att mappade enheter inte går att undvika och att du noggrant har granskat kraven innan du skickar in en servicebegäran. Följ sedan de här anvisningarna:

1. Gå till [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och välj "Felsökning + support" och leta sedan efter "Tjänstförfrågningar" under avsnittet Microsoft Managed Desktop.  
2. Skicka en supportbegäran med namnet "Distribution av mappade enheter" och ange all information som krävs för filresursen.  
3. Microsoft Managed Desktop IT Operations ger information om när begäran har slutförts med hjälp av uppdateringar av supportbegäran. Från början distribueras den här konfigurationen endast till enheter i testdistributionsgruppen.  
4. Du måste testa och bekräfta om konfigurationen som distribuerats av MICROSOFT Managed Desktop IT Operations fungerar som förväntat. Svara med hjälp av fliken Diskussion i informationen för samma supportbegäran för att meddela Microsoft Managed Desktop IT Operations när du har slutfört testningen.  
5. Microsoft Managed Desktop IT Operations-teamet distribuerar sedan konfigurationen till andra distributionsgrupper. 

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Managed Desktop](prerequisites.md).
2. [Använda utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverks konfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar på Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Managed Desktop](mapped-drives.md) (den här artikeln)
9. [Förbereda skrivarresurser för Microsoft Hanterat skrivbord](printing.md)
