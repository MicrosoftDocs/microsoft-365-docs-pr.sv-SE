---
title: Översikt över supporten som upphör för PerformancePoint Server 2007
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server supporten för 2007, ProClarity SharePoint och SharePoint Server 2007 har nått slutet av supporten. Läs den här artikeln om du vill ha hjälp med att planera uppgraderingen av BI-lösningen.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927342"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för PerformancePoint Server 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Office 2007-servrar och -program har nått supportens slut, inklusive servrar och program som du kanske använder som en del av BI-lösningar (Business Intelligence). I följande tabell visas de BI-program som påverkas:
  
|**Microsoft BI-program**|**Datum då supporten upphörde**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 juli 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 oktober 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 januari 2018  <br/> |
   
Mer information finns i Resurser [som hjälper dig att uppgradera från Office 2007-servrar och -klienter.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

Som de flesta Microsoft-produkter har PerformancePoint Server 2007 SP3, ProClarity-programvara, och SharePoint Server 2007 SP3, en supportlivscykel då Microsoft tillhandahåller nya funktioner, programkorrigeringar och säkerhetsuppdateringar. En produkts livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. Eftersom proClarity, PerformancePoint Server och SharePoint Server 2007 har nått supportens slut tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Programkorrigeringar för problem som upptäcks och kan påverka servrars stabilitet och användbarhet.
    
- Säkerhetskorrigeringar för säkerhetsproblem som upptäcks och som kan göra servrar eller program sårbara för säkerhetsbrister.
    
- Tidszonsuppdateringar.
    
Installationen av ProClarity, SharePoint Server 2007 SP3 och PerformancePoint Server 2007 SP3 fortsätter att köras även om supporten har upphört. Vi rekommenderar dock starkt att du migrerar från de här programmen så snart som möjligt.
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Det har gjorts många förändringar av MicrosoftS BI-program sedan 2007 och du kan överväga flera alternativ, enligt sammanfattningen i följande tabell.
  
|**Om du använde det här ...**|**Utforska de här alternativen ...**|**Och tänk på det här ...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 funktioner &amp; för övervakning av analys, inklusive:<br/>- PerformancePoint Monitoring Server <br/>- PerformancePoint Instrumentpanelsdesignern<br/>- Instrumentpanelsläsare för SharePoint Services (används för rendering av PerformancePoint-instrumentpaneler, styrkort och rapporter)<br/> |**Excel med Excel i en** webbläsare (i molnet eller lokalt). En översikt finns i [BI-funktioner i Excel och Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (i molnet eller lokalt). En översikt finns i [Vad är Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (lokalt). En översikt finns i [SQL Server Reporting Services (SSRS): Skapa, distribuera och hantera mobilrapporter och paginerade rapporter.](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports) <br/><br/> **PerformancePoint-tjänster** (lokalt). En översikt finns i [Vad är nytt i PerformancePoint-tjänster (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)) <br/> |Excel finns som en onlinelösning (molnbaserad) eller lokalt. Många rapporterings- och instrumentpanelbehov kan uppfyllas Excel.  <br/><br/> Power BI finns som en onlinelösning eller en lokal lösning. Power BI ingår inte i Microsoft 365. Men du kan börja använda Power BI gratis. Beroende på dina dataanvändnings- och affärsbehov kan du senare uppgradera till Power BI Pro med Microsoft 365 E5.<br/> <br/> Både Reporting Services PerformancePoint-tjänster lokala lösningar finns. <br/><br/> PerformancePoint-tjänster finns i SharePoint Server 2010, SharePoint Server 2013 och SharePoint Server 2016. <br/> <br/> Vissa funktioner och rapporttyper som var tillgängliga i PerformancePoint Server 2007 är inte tillgängliga i Excel, Power BI, Reporting Services eller PerformancePoint-tjänster. Granska de tillgängliga funktionerna för att avgöra den bästa lösningen för dina affärsbehov. <br/> |
| ProClarity-programvara, inklusive:<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint Viewer<br/> |**Arbeta med en Microsoft-partner** för att hitta en lösning som bäst passar dina behov. Besök [Microsoft-partnercenter.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> Du kan också använda Excel med Excel i en webbläsare, Power BI, SQL Server Reporting Services eller PerformancePoint-tjänster.  <br/> |Flera men inte alla funktioner i ProClarity-programvaran finns i andra Microsoft-erbjudanden, Excel, Power BI, Reporting Services och PerformancePoint-tjänster.  <br/> |
|SharePoint Server 2007-KPI:er (kallas även MOSS-KPI:er)  <br/> |**Excel med Excel Services**. En översikt finns i [Business Intelligence i Excel och Excel Services (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |MOSS-KPI:er som skapats med SharePoint Server 2007 kan användas i SharePoint Server 2010, SharePoint Server 2013 och SharePoint Server 2016. Men du kan inte skapa nya MOSS-KPI:er.  <br/> |
|Excel 2007  <br/> |**Excel** (i molnet eller lokalt). En översikt finns i [BI-funktioner i Excel och Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (i molnet eller lokalt). En översikt finns i [Vad är Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Både Excel och Power BI erbjuder organisationen molnbaserade och lokala lösningar, med stöd för en mängd olika datakällor.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Hjälp med att välja en lösning

Med så många tillgängliga BI-val kan det kännas överväldigande att avgöra vilket alternativ som passar bäst. Vi har en onlineguide som kan hjälpa dig. Se [Välja Microsoft BI-verktyg (Business Intelligence) för analys och rapportering.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>Vad händer om jag inte uppgraderar nu?

Du kan välja att inte uppgradera direkt. Dina befintliga servrar och program fortsätter att köras. Men du får inte några fler uppdateringar, inklusive säkerhetsuppdateringar, eftersom supporten har avslutats. Och om något går fel med serverprogrammen kan du inte få hjälp från Microsofts tekniska support.
  
## <a name="how-do-i-plan-my-upgrade"></a>Hur planerar jag min uppgradering?

När du har undersökt dina uppgraderingsalternativ är nästa steg att förbereda ett uppgraderingsplan. Följande avsnitt innehåller information och ytterligare resurser som kan vara till hjälp. Du har fyra huvudalternativ, bland annat två som fungerar både i molnet och lokalt och två som endast finns lokalt:
  
|**Alternativ**|**I molnet eller lokalt?**|
|:-----|:-----|
|[Excel med SharePoint server (lokal)](#excel-with-sharepoint-server-on-premises) <br/> |Båda  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Båda  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Endast lokalt  <br/> |
|[PerformancePoint-tjänster](#use-performancepoint-services-on-premises) <br/> |Endast lokalt  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Använd Excel (i molnet eller lokalt)

Med Excel, som också kallas *Excel Services* i SharePoint Server, kan du visa och använda arbetsböcker i ett webbläsarfönster, även om Excel inte är installerat på datorn. Du kan Excel skapa rapporter, styrkort och instrumentpaneler. Dela sedan dina arbetsböcker med andra som kan använda Excel i en webbläsare, oavsett om de använder SharePoint Online som en del av Microsoft 365 eller SharePoint Server lokalt. Du kan använda data som lagras lokalt eller i molnet, vilket gör att du kan använda en mängd olika datakällor.
  
I följande tabell jämförs viktiga fördelar med att Excel med Microsoft 365 med Excel med SharePoint Server. Mer information finns nedan.
  
|**Excel med Microsoft 365 (i molnet)**|**Excel med SharePoint server (lokal)**|
|:-----|:-----|
|**Du får den senaste och bästa versionen av Excel**. Med Microsoft 365 får du den senaste versionen av Excel som innehåller kraftfulla nya diagramtyper, möjligheten att snabbt och enkelt skapa diagram och tabeller samt stöd för fler datakällor. <br/> <br/> **Installationen är mycket enklare.** Excel ingår i Microsoft 365 för företag, så du behöver inte göra ett grovjobb. Registrera dig och logga in så kommer du att komma igång snabbare och mer effektivt än om du uppgraderar dina lokala servrar. <br/> <br/> **Användare har tillgång överallt till sina arbetsböcker.** Användare kan på ett säkert sätt visa arbetsböcker på sina datorer, smarta telefoner och surfplattor oavsett var de befinner sig. <br/> <br/> **Det finns mer!** Se [BI-funktioner i Excel och Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Du hanterar dina globala inställningar.** Som SharePoint administratör kan du ange globala inställningar, till exempel säkerhet, belastningsutjämning, sessioner, cachelagring av arbetsboken och externa dataanslutningar. <br/> <br/> **Du kan använda Excel Services med PerformancePoint-tjänster**. Du kan Excel Services och PerformancePoint-tjänster som en del av SharePoint Server-installationen och ta med dina Excel Services i PerformancePoint-instrumentpanelerna. <br/> <br/> **Det finns mer!** Se [Business Intelligence i Excel och Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel med Microsoft 365 (i molnet)

Om du flyttar Microsoft 365 har du de senaste tjänsterna och programmen, inklusive Excel 2016. PerformancePoint-tjänster är inte tillgängligt i Microsoft 365, så du kommer att ersätta ditt PerformancePoint-instrumentpanelinnehåll med Excel arbetsböcker eller andra rapporter. Den goda nyheten är att Excel 2016 har många nya diagramtyper och det är enklare än någonsin att skapa imponerande instrumentpaneler i Excel. Och nya funktioner läggs till regelbundet. Mer information finns i [Vad är nytt i Excel 2016 för Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Om du köper 50 eller fler platser Microsoft 365 kan Microsofts FastTrack-team hjälpa dig med detta. Mer information finns på [FastTrack.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel med SharePoint server (lokal)

Om du uppgraderar till en nyare version av SharePoint kan du använda Excel med Excel Services eller i en webbläsare enligt följande:
  
- Excel Services i SharePoint Server 2010
    
- Excel Services i SharePoint Server 2013
    
- Excel, som är en del av Office Online Server, installeras separat SharePoint Server 2016
    
Du kan PerformancePoint-tjänster i din nya version av SharePoint också, och använda den tillsammans med Excel.
  
Mer information om dina SharePoint finns i SharePoint översikt över slutet av supporten för [Server 2007.](sharepoint-2007-end-of-support.md)
  
Mer information om Excel Services finns i [Excel Services översikt (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Använd Power BI (i molnet eller lokalt)

Power BI är en uppsättning Business Analytics-verktyg som hjälper dig analysera data och dela insikter. Med Power BI kan du använda lokala datakällor eller onlinedatakällor för att skapa interaktiva rapporter och instrumentpaneler. Andra kan visa och använda dina rapporter och instrumentpaneler på sina datorer eller mobila enheter.
  
Power BI ingår inte i någon Microsoft 365 eller SharePoint Server. Det är en separat tjänst som innehåller Power BI Desktop, Power BI gateways och Power BI tjänsten. Power BI också integreras med SharePoint Online. Du kan komma igång med Power BI gratis. Baserat på din dataanvändning och affärsbehov kan du senare uppgradera till Power BI Pro med Microsoft 365 E5. Mer information finns i [Vad är Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Använda Reporting Services (lokalt)

SQL Server Reporting Services är en robust rapporteringslösning. Du kan konfigurera Reporting Services i ursprungligt läge eller SharePoint-integrerat läge. Du kan använda flera olika verktyg för att skapa rapporter, bland annat Report Designer, Report Builder och Power View. I och med den senaste SQL Server kan du även använda SQL Server Mobile Report Publisher att leverera rapporter som skalar till valfri skärmstorlek. Det gör att läsare kan använda rapporter på sina mobila enheter. Mer information finns i [SQL Server Reporting Services (SSRS): Skapa, distribuera och hantera mobilrapporter och paginerade rapporter.](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)
  
### <a name="use-performancepoint-services-on-premises"></a>Använda PerformancePoint-tjänster (lokalt)

PerformancePoint Server 2007 såldes separat från SharePoint Server 2007. Från och SharePoint Server 2010 är PerformancePoint-tjänster ett tjänstprogram i SharePoint Server. Du behöver alltså inte köpa separata serverlicenser eller maskinvara för att använda PerformancePoint-tjänster.
  
Om du vill PerformancePoint Server från 2007 till PerformancePoint-tjänster, flyttar du över till en nyare version av SharePoint Server och konfigurerar PerformancePoint-tjänster. Vilken version av SharePoint server som du flyttar till avgör om du kan importera ditt befintliga instrumentpanelinnehåll från PerformancePoint Server 2007 till PerformancePoint-tjänster.
  
- Om du uppgraderar till SharePoint Server 2010 kan du importera ditt PerformancePoint-instrumentpanelinnehåll från PerformancePoint Server 2007 till PerformancePoint-tjänster i SharePoint Server 2010. Mer information finns i [Importguiden: PerformancePoint Server 2007-innehåll till SharePoint Server 2010.](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))
    
- Om du går över till SharePoint Server 2013 eller SharePoint Server 2016 måste du förmodligen skapa nytt instrumentpanelinnehåll (datakällor, rapporter, styrkort och instrumentpanelsidor).
    
Information om hur du kommer PerformancePoint-tjänster ditt uppgraderingsabonnemang finns i följande resurser:
  
- [SharePoint Server 2007 – Översikt över slutet på supporten](sharepoint-2007-end-of-support.md)
    
- När du vet vilken version SharePoint du flyttar till kan du läsa motsvarande artikel för PerformancePoint-tjänster:
    
  - [Planera för PerformancePoint-tjänster (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [PerformancePoint-tjänster i SharePoint Server 2013 – översikt](/sharepoint/administration/performancepoint-services-overview)
    
  - [PerformancePoint-tjänster i SharePoint Server 2016 – översikt](/sharepoint/administration/performancepoint-services-overview)
    
När du uppgraderar PerformancePoint-tjänster funktioner får du flera nya funktioner och förbättringar. PerformancePoint-tjänster har förbättrade styrkort. Nya visualiseringar, till exempel nedbrytningsträdet och KPI-detaljrapporten. fler diagramtyper; bättre filtreringsfunktioner för tidsinformation. och förbättrad tillgänglighetsefterlevnad. Mer information finns i [Vad är nytt i PerformancePoint-tjänster (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Var kan jag få hjälp med min uppgradering?

Oavsett om du uppgraderar lokalt eller flyttar över Microsoft 365 rekommenderar vi att du arbetar med en Microsoft-partner. En kvalificerad partner kan hjälpa dig identifiera den lösning som bäst uppfyller dina affärsbehov och hjälpa dig med distributionen. Besök [Microsoft Partner Center och](https://go.microsoft.com/fwlink/?linkid=841249)använd sökfiltren för att hitta en lösningsleverantör.
  
## <a name="related-topics"></a>Relaterade ämnen

[Resurser som hjälper dig att uppgradera från Office 2007-servrar och -klienter](upgrade-from-office-2007-servers-and-products.md)