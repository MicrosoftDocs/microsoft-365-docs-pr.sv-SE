---
title: Söka efter eDiscovery-aktiviteter i granskningsloggen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Lär dig vilka händelser som loggas när användare tilldelade eDiscovery-behörigheter utför innehållssökning, grundläggande eDiscovery och Advanced eDiscovery-uppgifter i Microsoft 365 efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b1f3f235f3411e2f637e4e32104c6179643757d
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657699"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Söka efter eDiscovery-aktiviteter i granskningsloggen

Aktiviteter för innehållssökning och eDiscovery-relaterade aktiviteter (för Core eDiscovery och Advanced eDiscovery) som utförs i kompatibilitetscentret för Microsoft 365 eller genom att köra motsvarande PowerShell-cmdlets loggas i granskningsloggen. Händelser loggas när administratörer eller eDiscovery-hanterare (eller alla användar tilldelade eDiscovery-behörigheter) utför följande aktiviteter för innehållssökning och bas-eDiscovery i efterlevnadscentret för Microsoft 365:
  
- Skapa och hantera core- Advanced eDiscovery ärenden

- Skapa, starta och redigera innehållssökningar

- Utföra sökåtgärder, till exempel förhandsgranska, exportera och ta bort sökresultat

- Hantera korenterare och granskningsuppsättningar i Advanced eDiscovery

- Konfigurera behörighetsfiltrering för innehållssökning

- Hantera eDiscovery-administratörsrollen
  
Mer information om hur du söker i granskningsloggen, vilka behörigheter som krävs och exporterar sökresultat finns i Söka i granskningsloggen i [Microsoft 365 kompatibilitetscenter.](search-the-audit-log-in-security-and-compliance.md)
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Söka efter och visa eDiscovery-aktiviteter

För närvarande behöver du göra några saker för att visa eDiscovery-aktiviteter i granskningsloggen. Gör så här:
  
1. Gå till <https://compliance.microsoft.com> och logga in med ditt arbets- eller skolkonto.

2. I det vänstra navigeringsfönstret i Microsoft 365, klickar du på **Visa alla** och sedan på **Granska**.

3. I **listrutan** Aktiviteter under **eDiscovery-aktiviteter eller eDiscovery Advanced eDiscovery** **klickar** du på en eller flera aktiviteter att söka efter.

    > [!NOTE]
    > **Listrutan** Aktiviteter innehåller också en grupp aktiviteter med namnet **eDiscovery-cmdlet-aktiviteter** som returnerar poster från cmdlet-granskningsloggen.
  
4. Välj ett datum- och tidsintervall för att visa eDiscovery-händelser som inträffat under perioden.

5. Välj en **eller** flera användare som du vill visa sökresultat för i rutan Användare. Lämna rutan tom om du vill returnera poster för alla användare.

6. Klicka på **Sök** för att köra sökningen med dina sökvillkor.

7. När sökresultaten visas kan du klicka på Filtrera resultat **för att** filtrera eller sortera de resulterande aktivitetsposterna. Tyvärr kan du inte använda filtrering för att uttryckligen utesluta vissa aktiviteter. 

8. Om du vill visa information om en aktivitet klickar du på aktivitetsposten i listan med sökresultat. 

    En  utfällsida för Information visas med detaljerade egenskaper från händelseposten. Om du vill visa ytterligare information klickar du **på Mer information.** En beskrivning av dessa egenskaper finns i avsnittet [Detaljerade egenskaper för eDiscovery-aktiviteter.](#detailed-properties-for-ediscovery-activities)

9. Om du vill kan du exportera granskningsloggens sökresultat till en CSV-fil och sedan använda Power Query Excel för att formatera och filtrera posterna. Mer information finns i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>eDiscovery-aktiviteter

I följande tabell beskrivs de aktiviteter för innehållssökning och bas-eDiscovery som loggas när en administratör eller eDiscovery-hanterare utför en eDiscovery-relaterad aktivitet med efterlevnadscentret eller kör motsvarande cmdlet i Säkerhets- och efterlevnadscenter för & PowerShell. Observera också att vissa aktiviteter som utförs i Advanced eDiscovery returneras när du söker efter aktiviteter i den här listan.
  
> [!NOTE]
> De eDiscovery-aktiviteter som beskrivs i det här avsnittet ger liknande information till eDiscovery-cmdlet-aktiviteterna som beskrivs i nästa avsnitt. Vi rekommenderar att du använder de eDiscovery-aktiviteter som beskrivs i det här avsnittet eftersom de visas i granskningsloggens sökresultat inom 30 minuter. Det tar upp till 24 timmar innan eDiscovery-cmdlet-aktiviteterna visas i granskningsloggens sökresultat.
  
|**Visningsnamn**|**Åtgärd**|**Motsvarande cmdlet**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|Medlem tillagd i eDiscovery-ärende  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |En användare har lagts till som medlem i ett eDiscovery-ärende. Som medlem i ett ärende kan en användare utföra olika ärenderelaterade uppgifter beroende på om de har tilldelats nödvändiga behörigheter.  <br/> |
|Innehållssökning ändrad  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |En befintlig innehållssökning har ändrats. Ändringar kan innefatta att lägga till eller ta bort innehållsplatser eller redigera sökfrågan.  <br/> |
|EDiscovery-administratörsmedlemskap ändrades  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Listan med eDiscovery-administratörer i organisationen har ändrats. Den här aktiviteten loggas när listan med eDiscovery-administratörer ersätts med en grupp med nya användare. Om en enskild användare läggs till eller tas bort loggas åtgärden CaseAdminAdded.  <br/> |
|E-dataidentifieringsfall ändrade  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Ett e-dataidentifieringsfall har ändrats. Du kan t.ex. stänga ett öppet ärende eller öppna ett stängt ärende igen.  <br/> |
|EDiscovery-ärendemedlemskap ändrades  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Medlemslistan för ett e-dataidentifieringsfall har ändrats. Den här aktiviteten loggas när alla medlemmar ersätts med en grupp med nya användare. Om en enskild medlem läggs till eller tas bort loggas åtgärden CaseMemberAdded eller CaseMemberRemoved.  <br/> |
|Filter för ändrade sökbehörigheter  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Ett filter för sökbehörigheter har ändrats.  <br/> |
|Ändrad sökfråga för eDiscovery-fall  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har ändrats. Bland de möjliga ändringarna går det att redigera frågan eller datumintervallet för ett frågebaserat intervall.  <br/> |
|Förhandsgranskningsobjekt för innehållssökning nedladdat  <br/> |PreviewItemDownloaded  <br/> |Uppgift saknas  <br/> |En användare laddade ned ett objekt till sin lokala dator (genom att klicka på länken Ladda ned **ursprungligt** objekt) när de förhandsgranskar sökresultat.  <br/> |
|Förhandsgranskningsobjekt för innehållssökning visas  <br/> |PreviewItemListed  <br/> |Uppgift saknas  <br/> |En användare har **klickat på** Förhandsgranska sökresultat för att visa sidan med sökresultat för förhandsgranskning, som visar upp till 1 000 objekt från resultatet av en innehållssökning.  <br/> |
|Förhandsgranskningsobjekt för innehållssökning visad  <br/> |PreviewItemRendered  <br/> |Uppgift saknas  <br/> |En eDiscovery-hanterare visade ett objekt genom att klicka på det när du förhandsgranskade sökresultat.  <br/> |
|Innehållssökning skapad  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |En ny innehållssökning har skapats.  <br/> |
|EDiscovery-administratör skapad  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |En användare har lagts till som eDiscovery-administratör i organisationen.  <br/> |
|Skapat eDiscovery-fall  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Ett eDiscovery-ärende har skapats. När ett ärende skapas behöver du bara ge det ett namn. Andra ärenderelaterade uppgifter som att lägga till medlemmar, skapa innehåll som sätts i innehåll och skapa innehållssökningar kopplade till ärendet resulterar i att ytterligare händelser loggas.  <br/> |
|Filter för sökbehörighet skapad  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Ett filter för sökbehörigheter har skapats.  <br/> |
|Skapad sökfråga för eDiscovery-fall  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har skapats.  <br/> |
|Borttagna innehållssökning  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |En befintlig innehållssökning har tagits bort.  <br/> |
|Borttagna eDiscovery-administratörer  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |En eDiscovery-administratör har tagits bort från din organisation.  <br/> |
|Borttagna eDiscovery-fall  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Ett eDiscovery-ärende har tagits bort. Eventuella väntande ändringar som är kopplade till ärendet måste tas bort innan ärendet kan tas bort.  <br/> |
|Filter för borttagna sökbehörigheter  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Ett filter för sökbehörigheter har tagits bort.  <br/> |
|Borttagna sökfrågor för eDiscovery-fall  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har tagits bort. Att ta bort frågan från ett behörighets hold är ofta resultatet av att ett hold-objekt tas bort. När en fråga om att hålla på plats eller ett väntande objekt tas bort, frisläpps de innehållsplatser som var på plats.  <br/> |
|Hämtad export av innehållssökning  <br/> |SearchExportDownloaded  <br/> |Uppgift saknas  <br/> |En användare har laddat ned resultatet av en innehållssökning till sin lokala dator. En **startad export av** innehållssökningsaktivitet måste initieras innan sökresultat kan laddas ned.  <br/> |
|Förhandsgranskade resultat av innehållssökning  <br/> |SearchPreviewed  <br/> |Uppgift saknas  <br/> |En användare förhandsgranskade resultatet av en innehållssökning.  <br/> |
|Bortrensade resultat av innehållssökning  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |En användare rensade resultatet av en innehållssökning genom att köra **kommandot New-ComplianceSearchAction -Purge.**  <br/> |
|Analys av innehållssökning borttagen  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |En förberedelseåtgärd för innehållssökning (för att förbereda sökresultat för Advanced eDiscovery) har tagits bort. Om förberedelseåtgärden var mindre än två veckor gammal togs sökresultaten som förberetts för Advanced eDiscovery bort från den Microsoft Azure lagringsutrymmet. Om förberedelseåtgärden är äldre än 2 veckor anger den här händelsen att endast motsvarande förberedelseåtgärd har tagits bort.  <br/> |
|Export av innehållssökning borttagen  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |En exportåtgärd för innehållssökning har tagits bort. Om exportåtgärden var mindre än två veckor gammal togs sökresultatet som laddades upp till Microsoft Azure lagringsutrymmet bort. Om exportåtgärden är äldre än 2 veckor anger den här händelsen att endast motsvarande exportåtgärd har tagits bort.  <br/> |
|Medlem borttagen från eDiscovery-ärende  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |En användare togs bort som medlem i ett eDiscovery-ärende.  <br/> |
|Resultat av innehållssökning borttaget  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |En förhandsgranskningsåtgärd för innehållssökning har tagits bort.  <br/> |
|Åtgärd för borttagen rensning utförs vid innehållssökning  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |En åtgärd för att rensa innehåll har tagits bort.  <br/> |
|Sökrapport borttagen  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |En exportrapportåtgärd för innehållssökning har tagits bort.  <br/> |
|Startad analys av innehållssökning  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Resultatet av en innehållssökning förbereddes för analys i Advanced eDiscovery.  <br/> |
|Startad innehållssökning  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |En innehållssökning startades. När du skapar eller ändrar en innehållssökning med hjälp Microsoft 365 med ett GUI för efterlevnadscenter startas sökningen automatiskt. Om du skapar eller ändrar en sökning med hjälp av cmdleten **New-ComplianceSearch** eller **Set-ComplianceSearch** måste du köra cmdleten **Start-ComplianceSearch** för att starta sökningen.  <br/> |
|Startad export av innehållssökning  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |En användare exporterade resultatet av en innehållssökning.  <br/> |
|Startad exportrapport  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |En användare har exporterat en rapport för innehållssökning.  <br/> |
|Stoppad innehållssökning  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |En användare har stoppat en innehållssökning.  <br/> |
|(inget)|CaseViewed|Get-ComplianceCase|En användare har visat en lista över ärenden på sidan **Bas-eDiscovery** eller **sidan Advanced eDiscovery** i efterlevnadscentret eller genom att köra cmdleten Get-ComplianceCase Core.|
|(inget)|SearchViewed|Get-ComplianceSearch|En användare har visat listan på  innehållssökningar (visas på fliken Sökningar) i efterlevnadscentret eller genom att köra cmdleten. Den här aktiviteten loggas också när en användare visar listan med innehållssökningar som  är kopplade till ett eDiscovery-ärende (genom att klicka på fliken Sökningar i ett ärende) eller genom att köra kommandot **Get-ComplianceSearch -Case.**|
|(inget)|ViewedSearchExported|Get-ComplianceSearchAction -Exportera|En användare har visat listan över exportjobb för innehållssökning (listas på fliken **Exporter)** i efterlevnadscentret eller genom att köra cmdleten. Den här aktiviteten loggas även när en användare visar listan över exportjobb i ett eDiscovery-ärende (visas på fliken **Exporter** i ett ärende) eller genom att köra kommandot **Get-ComplianceSearchAction -Case -Export.**|
|(inget)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|En användare förhandsgranskar resultatet av en innehållssökning i efterlevnadscentret eller genom att köra cmdleten.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Advanced eDiscovery-aktiviteter

I följande tabell beskrivs de Advanced eDiscovery som loggas i granskningsloggen. De här aktiviteterna kan användas för att hjälpa dig att följa upp aktivitetens förlopp i Advanced eDiscovery fall.

|**Visningsnamn**|**Åtgärd**|**Beskrivning**|
|:-----|:-----|:-----|
|Lade till data i en annan granskningsuppsättning|AddWorkingSetQueryToWorkingSet|Användaren har lagt till dokument från en granskningsuppsättning till en annan granskningsuppsättning.|
|Lade till data att granska uppsättning|AddQueryToWorkingSet|Användaren lade till sökresultatet från en innehållssökning som är kopplad Advanced eDiscovery ett ärende i en granskningsuppsättning.|
|Lade till icke-Microsoft 365 data att granska uppsättning|AddNonOffice365DataToWorkingSet|Användaren lade till icke-Microsoft 365 data i en granskningsuppsättning.|
|Dokument som har åtgärdats för granskningsuppsättning|AddRemediatedData|Användaren laddar upp dokument som hade indexeringsfel som har åtgärdats med en granskningsuppsättning.|
|Analyserade data i granskningsuppsättning|RunAlgo|Användaren körde analys på dokument i en granskningsuppsättning.|
|Kommenterat dokument i granskningsuppsättning|AnnotateDocument|Användaren har kommenterat ett dokument i en granskningsuppsättning. Anteckning omfattar att göra om innehåll i ett dokument.|
|Jämförda belastningsuppsättningar|LoadComparhusJob|Användaren jämförde två olika inläsningsuppsättningar i en granskningsuppsättning. En inläsningsuppsättning är när data från en innehållssökning som är kopplad till ärendet läggs till i en granskningsuppsättning.|
|Konverterade dokument som konverterats till PDF|Burn Job|Användaren har konverterat alla omaktiverade dokument i en granskning som är inställd på PDF-filer.|
|Granskningsuppsättning skapad|CreateWorkingSet|Användaren har skapat en granskningsuppsättning.|
|Sökning i granskningsuppsättning skapad|CreateWorkingSetSearch|Användaren har skapat en sökfråga som söker i dokument i en granskningsuppsättning.|
|Skapad tagg|CreateTag|Användaren skapade en tagggrupp i en granskningsuppsättning. En tagggrupp kan innehålla en eller flera underordnade taggar. De här taggarna används sedan för att tagga dokument i granskningsuppsättningen.|
|Sökning med en borttagna granskningsuppsättning|DeleteWorkingSetSearch|Användaren har tagit bort en sökfråga i en granskningsuppsättning.|
|Borttagna taggar|DeleteTag|Användaren har tagit bort en tagg eller en tagggrupp i en granskningsuppsättning.|
|Laddade ned dokument|DownloadDocument|Användaren har laddat ned ett dokument från en granskningsuppsättning.|
|Redigerad tagg|UpdateTag|Användaren ändrade en tagg i en granskningsuppsättning.|
|Dokument exporterade från granskningsuppsättning|ExportJob|Användaren exporterade dokument från en uppsättning med granskare.|
|Inställning för ändrat ärende|UpdateCaseSettings|Användaren har ändrat inställningarna för ett ärende. Ärendeinställningarna omfattar ärendeinformation, åtkomstbehörigheter och inställningar som styr sök- och analysbeteendet.|
|Ändrad granskningsuppsättningssökning|UpdateWorkingSetSearch|Användaren har redigerat en sökfråga i en granskningsuppsättning.|
|Förhandsgranskningsuppsättningssökning för granskad|PreviewWorkingSetSearch|Användaren förhandsgranskade resultatet av en sökfråga i en granskningsuppsättning.|
|Åtgärdade feldokument|ErrorRemediation Job|Användaren åtgärdar filer som innehöll indexeringsfel.|
|Taggat dokument|TagFiles|Användaren taggar ett dokument i en granskningsuppsättning.|
|Taggade resultat för en fråga|TagJob|Användaren taggar alla dokument som matchar sökfrågans villkor i en granskningsuppsättning.|
|Dokument som visats i en granskningsuppsättning|ViewDocument|Användaren har visat ett dokument i en granskningsuppsättning.|
|||

## <a name="ediscovery-cmdlet-activities"></a>eDiscovery-cmdlet-aktiviteter

I följande tabell visas de cmdlet-granskningsloggposter som loggas när en administratör eller användare utför en eDiscovery-relaterad aktivitet med hjälp av efterlevnadscentret eller genom att köra motsvarande cmdlet i Security & Compliance Center PowerShell. Den detaljerade informationen i granskningsloggposten skiljer sig för cmdlet-aktiviteterna som visas i den här tabellen och eDiscovery-aktiviteterna som beskrivs i föregående avsnitt.
  
Som tidigare nämnts tar det upp till 24 timmar innan eDiscovery-cmdlet-aktiviteter visas i granskningsloggens sökresultat.
  
> [!TIP]
> Cmdletarna i kolumnen **Operation** i följande tabell är länkade till motsvarande hjälpavsnitt för cmdlet på TechNet. Gå till cmdlet-hjälpavsnittet för en beskrivning av tillgängliga parametrar för varje cmdlet. Parametern och parametervärdet som användes med en cmdlet ingår i granskningsloggposten för varje eDiscovery-cmdlet-aktivitet som loggas. 
  
|**Visningsnamn**|**Operation (cmdlet)**|**Beskrivning**|
|:-----|:-----|:-----|
|Skapat ärende för håll i e-dataidentifieringsfall  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Ett sådant ärende har skapats för ett eDiscovery-ärende. Ett värde kan skapas med eller utan att ange en innehållskälla. Om innehållskällor anges identifieras de i granskningsloggposten.  <br/> |
|Borttagna rader från e-dataidentifieringsfall  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Ett ärende som är kopplat till ett eDiscovery-ärende har tagits bort. Om du tar bort ett väntande objekt tas alla innehållsplatser bort från platsen. Om du tar bort det här antalet innebär det också att du tar bort reglerna för att hålla ärendet kvar (se **Remove-CaseHoldRule** nedan).  <br/> |
|Ändrat håll för e-dataidentifieringsfall  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Ett håll som är kopplat till en eDiscovery har ändrats. Möjliga ändringar är att lägga till eller ta bort innehållsplatser eller inaktivera (inaktivera) holden.  <br/> |
|Skapad sökfråga för eDiscovery-fall  <br/> |[New-CaseHoldrule](/powershell/module/exchange/new-caseholdrule) <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har skapats.  <br/> |
|Borttagna sökfrågor för eDiscovery-fall  <br/> |[Remove-CaseHoldrule](/powershell/module/exchange/remove-caseholdrule) <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har tagits bort. Att ta bort frågan från ett behörighets hold är ofta resultatet av att ett hold-objekt tas bort. När en fråga om att hålla på plats eller ett väntande objekt tas bort, frisläpps de innehållsplatser som var på plats.  <br/> |
|Ändrad sökfråga för eDiscovery-fall  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Ett frågebaserat ärende som associerats med ett eDiscovery-ärende har ändrats. Bland de möjliga ändringarna går det att redigera frågan eller datumintervallet för ett frågebaserat intervall.  <br/> |
|Skapat eDiscovery-fall  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Ett eDiscovery-ärende har skapats. När ett ärende skapas behöver du bara ge det ett namn. Andra ärenderelaterade uppgifter som att lägga till medlemmar, skapa innehåll som sätts i innehåll och skapa innehållssökningar kopplade till ärendet resulterar i att ytterligare händelser loggas.  <br/> |
|Borttagna eDiscovery-fall  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Ett eDiscovery-ärende har tagits bort. Eventuella väntande ändringar som är kopplade till ärendet måste tas bort innan ärendet kan tas bort.  <br/> |
|E-dataidentifieringsfall ändrade  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Ett e-dataidentifieringsfall har ändrats. Du kan t.ex. stänga ett öppet ärende eller öppna ett stängt ärende igen.  <br/> |
|Medlem tillagd i eDiscovery-ärende  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |En användare har lagts till som medlem i ett eDiscovery-ärende. Som medlem i ett ärende kan en användare utföra olika ärenderelaterade uppgifter beroende på om de har tilldelats nödvändiga behörigheter.  <br/> |
|Medlem borttagen från eDiscovery-ärende  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |En användare togs bort som medlem i ett eDiscovery-ärende.  <br/> |
|EDiscovery-ärendemedlemskap ändrades  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |Medlemslistan för ett e-dataidentifieringsfall har ändrats. Den här aktiviteten loggas när alla medlemmar ersätts med en grupp med nya användare. Om en enskild medlem läggs till eller tas bort loggas åtgärden **Add-ComplianceCaseMember** eller **Remove-ComplianceCaseMember.**  <br/> |
|Innehållssökning skapad  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |En ny innehållssökning har skapats.  <br/> |
|Borttagna innehållssökning  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |En befintlig innehållssökning har tagits bort.  <br/> |
|Innehållssökning ändrad  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |En befintlig innehållssökning har ändrats. Ändringar kan innefatta att lägga till eller ta bort innehållsplatser som genomsöks och att redigera sökfrågan.  <br/> |
|Startad innehållssökning  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |En innehållssökning startades. När du skapar eller ändrar en innehållssökning med hjälp av guid för efterlevnadscentret startas sökningen automatiskt. Om du skapar eller ändrar en sökning med hjälp av cmdleten **New-ComplianceSearch** eller **Set-ComplianceSearch** måste du köra cmdleten **Start-ComplianceSearch** för att starta sökningen.  <br/> |
|Stoppad innehållssökning  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |En innehållssökning som kördes stoppades.  <br/> |
|Innehållssökningsåtgärd skapad  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |En innehållssökningsåtgärd har skapats. Innehållssökningsåtgärder omfattar att förhandsgranska sökresultat, exportera sökresultat, förbereda sökresultat för analys i Advanced eDiscovery och permanent ta bort objekt som matchar sökvillkoren för en innehållssökning.  <br/> |
|Sökåtgärden Borttagna innehåll  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |En innehållssökningsåtgärd har tagits bort.  <br/> |
|Filter för sökbehörighet skapad  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Ett filter för sökbehörigheter har skapats.  <br/> |
|Filter för borttagna sökbehörigheter  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Ett filter för sökbehörigheter har tagits bort.  <br/> |
|Filter för ändrade sökbehörigheter  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Ett filter för sökbehörigheter har ändrats.  <br/> |
|EDiscovery-administratör skapad  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |En användare har lagts till som eDiscovery-administratör i organisationen.  <br/> |
|Borttagna eDiscovery-administratörer  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |En eDiscovery-administratör har tagits bort från din organisation.  <br/> |
|EDiscovery-administratörsmedlemskap ändrades  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |Listan med eDiscovery-administratörer i organisationen har ändrats. Den här aktiviteten loggas när listan med eDiscovery-administratörer ersätts med en grupp med nya användare. Om en enskild användare läggs till eller tas bort loggas åtgärden **Add-eDiscoveryCaseAdmin** eller **Remove-eDiscoveryCaseAdmin.**  <br/> |

## <a name="detailed-properties-for-ediscovery-activities"></a>Detaljerade egenskaper för eDiscovery-aktiviteter

I följande tabell beskrivs de egenskaper som ingår när  du klickar på **Mer information** på sidan Information för en eDiscovery-aktivitet som visas i sökresultatet. De här egenskaperna ingår också i CSV-filen när du exporterar granskningsloggens sökresultat. En granskningsloggpost för en eDiscovery-aktivitet innehåller inte varje detaljerad egenskap som anges nedan.
  
> [!TIP]
> När du exporterar sökresultaten innehåller CSV-filen en kolumn med namnet **Information,** som innehåller de detaljerade egenskaper som beskrivs i följande tabell i en egenskap med flera värden. Du kan använda Power Query-funktionen i Excel för att dela upp kolumnen i flera kolumner så att varje egenskap har en egen kolumn. Då kan du sortera och filtrera efter en eller flera av de här egenskaperna. Mer information finns i avsnittet "Exportera sökresultatet till en fil" i [Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file) 
  
|**Egenskap**|**Beskrivning**|
|:-----|:-----|
|Ärende  <br/> |Identiteten (GUID) för eDiscovery-ärendet som skapades, ändrades eller togs bort.  <br/> |
|ClientApplication  <br/> |eDiscovery-cmdlet-aktiviteter har värdet **EMC** för den här egenskapen. Det här anger aktiviteten som utfördes med hjälp av GUI för efterlevnadscenter eller genom att köra cmdleten i PowerShell.  <br/> |
|ClientIP  <br/> |IP-adressen för den enhet som användes när aktiviteten loggades. IP-adressen visas i IPv4- eller IPv6-adressformat.  <br/> |
|ClientRequestId  <br/> | För eDiscovery-aktiviteter är den här egenskapen vanligtvis tom.  <br/> |
|CmdletVersion  <br/> |Versionsnumret för den version av efterlevnadscentret som körs i organisationen.  <br/> |
|CreationTime  <br/> |Datum och tid i UTC (Coordinated Universal Time) när eDiscovery-aktiviteten slutfördes.  <br/> |
|EffectiveOrganization  <br/> |Namnet på Microsoft 365-organisationen.  <br/> |
|ExchangeLocations  <br/> |De Exchange Online postlådor som ingår i en innehållssökning eller som har satts i ett ärende för e-dataidentifiering.  <br/> |
|Undantag  <br/> |Postlådor eller webbplatsplatser som undantas från en innehållssökning eller ett undantag i ett eDiscovery-ärende.  <br/> |
|ExtendedProperties  <br/> |Ytterligare egenskaper från en innehållssökning, en åtgärd för innehållssökning eller håll kvar i ett eDiscovery-ärende, till exempel objekt-GUID och motsvarande cmdlet och cmdlet-parametrar som användes när aktiviteten utfördes.  <br/> |
|ID  <br/> |ID för rapportposten. ID:t identifierar granskningsloggposten unikt.  <br/> |
|NonPIIParameters  <br/> |En lista över parametrarna (utan några värden) som användes med cmdleten som identifieras i egenskapen Operation. Parametrarna som visas i den här egenskapen är samma som de som anges i egenskapen Parametrar.  <br/> |
|ObjectId  <br/> |GUID eller namn på objektet (till exempel en innehållssökning eller ett eDiscovery-fall) som skapades, ändrades eller togs bort av aktiviteten som anges i egenskapen Åtgärd. Det här objektet identifieras också i kolumnen Objekt i granskningsloggens sökresultat.  <br/> |
|ObjectType  <br/> |Den typ av eDiscovery-objekt som användaren har skapat, tagit bort eller ändrat. Till exempel en åtgärd för innehållssökning (förhandsgranska, exportera eller rensa), ett eDiscovery-ärende eller en innehållssökning.  <br/> |
|Åtgärd  <br/> |Namnet på åtgärden som motsvarar den eDiscovery-aktivitet som utfördes.  <br/> |
|OrganizationId  <br/> |GUID för din Microsoft 365 organisation.  <br/> |
|Parametrar  <br/> |Namn och värde för parametrarna som användes med motsvarande cmdlet.  <br/> |
|PublicFolderLocations  <br/> |De offentliga mappplatserna i Exchange Online som ingår i en innehållssökning eller som har satts på plats i ett eDiscovery-ärende.  <br/> |
|Fråga  <br/> |Sökfrågan som är kopplad till aktiviteten, till exempel en innehållssökning eller ett frågebaserat väntande.  <br/> |
|RecordType  <br/> |Typen av åtgärd som anges av posten. Värdet för **18 anger** en händelse som är relaterad till en aktivitet som listas i [avsnittet för eDiscovery-cmdlet-aktiviteter.](#ediscovery-cmdlet-activities) Värdet **24 anger en händelse** relaterad till en aktivitet som listas i avsnittet Så här söker du efter och visar [eDiscovery-aktiviteter.](#how-to-search-for-and-view-ediscovery-activities)  <br/> |
|ResultStatus  <br/> |Anger om åtgärden (som anges i egenskapen Åtgärd) lyckades eller inte.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Anger att aktiviteten var ett efterlevnadscenter. Alla eDiscovery-aktiviteter har värdet **0** för den här egenskapen.  <br/> |
|SharepointLocations  <br/> |Den SharePoint onlinewebbplatser som ingår i en innehållssökning eller som har satts i ett eDiscovery-ärende.  <br/> |
|StartTime  <br/> |Datum och tid i UTC (Coordinated Universal Time) när eDiscovery-aktiviteten startades.  <br/> |
|UserId  <br/> |Användaren som utförde aktiviteten (anges i operation-egenskapen) som resulterade i att posten loggades. Poster för eDiscovery-aktivitet som utförs av systemkonton (t.ex. NT AUTHORITY\SYSTEM) ingår också i granskningsloggen.  <br/> |
|UserKey  <br/> |Ett alternativt ID för användaren som identifieras i UserId-egenskapen. För eDiscovery-aktiviteter är värdet för den här egenskapen vanligtvis detsamma som egenskapen UserId.  <br/> |
|UserServicePlan  <br/> |Prenumerationen som används av din organisation. För eDiscovery-aktiviteter är den här egenskapen vanligtvis tom.  <br/> |
|UserType  <br/> |Typen av användare som utförde åtgärden. Följande värden anger användartypen.  <br/> 0 En vanlig användare. 2 En administratör i organisationen. 3 En Microsoft-datacenteradministratör eller ett datacentersystemkonto. 4 Ett systemkonto. 5 Ett program. 6 Ett huvudnamn för en tjänst. |
|Version  <br/> |Anger versionsnumret för aktiviteten (identifieras av egenskapen Operation) som har loggats.  <br/> |
|Arbetsbelastning  <br/> |Tjänsten där aktiviteten inträffade. För eDiscovery-aktiviteter är värdet **SecurityComplianceCenter.**  <br/> |
