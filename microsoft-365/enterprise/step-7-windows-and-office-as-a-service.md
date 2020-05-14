---
title: 'Steg 7: Underhåll av Windows och Office'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig hur du förbereder för underhåll av Windows och Office i din miljö.
ms.openlocfilehash: f30581408be1c69d7aec7e31e9b5d6461266adb1
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222679"
---
# <a name="step-7-windows-and-office-servicing"></a>Steg 7: Underhåll av Windows och Office

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Steg 7: Underhåll av Windows och Office</strong></p>
<p>Både Windows 10 och Microsoft 365-applikationer för företag får löpande nya funktioner för att ge bättre användarupplevelser och högre säkerhet tillsammans med de senaste nyheterna. Ta reda på hur du kan hålla dig uppdaterad med halvårsuppdateringar och månatliga uppdateringar, hur den nya underhållsmodellen fungerar och vilka verktyg och alternativ du har.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Underhåll av Windows och Office är det sjunde steget i vårt rekommenderade distributionsprocesshjul som innehåller planeringsaspekterna när det gäller förberedelser inför de halvårsvisa funktionsuppdateringarna. Om du vill se den fullständiga skrivbordsdistributionsprocessen kan du gå till [Center för skrivbordsdistribution](https://aka.ms/HowToShift).
>

Både Windows 10 och Microsoft 365-applikationer för företag inför nya underhållsalternativ, supportmodeller och tidslinjer för uppdatering. Dessa förändringar gör det enklare att hålla sig uppdaterad om de senaste funktionerna. Tillsammans med dessa uppdateringar finns nya konfigurationsalternativ för att aktivera underhållsplaner för dina behov. Nu ska gå igenom hur du förbereder dig inför uppdateringar i halvårskanalen som erbjuder nya funktioner i Windows 10 och Microsoft 365-applikationer för företag samtidigt som du använder de nya funktionerna i Microsoft Endpoint Configuration Manager (Current Branch).

[Hjälpa kunder att byta till Windows 10 och Microsoft 365-applikationer för företag](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Uppdateringstyper

Uppdateringarna är indelade i två huvudkategorier. Den ena kategorin är funktionsuppdateringar och den andra är kvalitets- och säkerhetsuppdateringar som innehåller kumulativa säkerhets-, tillförlitlighets- och felkorrigeringar. Både Windows och Office har en halvårskanal som levererar nya funktioner två gånger per år (kring mars och september), medan kvalitets- och säkerhetsuppdateringarna släpps varje månad. Något som är unikt för Office 365-program är att vi även erbjuder en månadskanal med fullständigt stöd där uppdateringarna innehåller både nya funktioner och kvalitetsuppdateringar.

Om du är van vid längre cykler mellan uppdateringar av operativsystem och appar kanske du har följande funderingar:

  - Kommer uppdateringarna att vara kompatibla?

  - Kommer användarna behöva skolas om?

  - Vad finns det för risker?

För att svara på dessa frågor och motivera varför nya funktioner levereras oftare ska vi gå igenom några av fördelarna med detta

### <a name="feature-update-benefits"></a>Fördelar med funktionsuppdatering

Vi har gått ifrån den tidigare modellen som innebar stora förändringar ungefär vart tredje år till att göra mindre löpande ändringar med funktionsuppdateringar två gånger per år. Varför? Eftersom utvecklingen av nya tekniker och säkerhetshoten går så snabbt är det här ett sätt att få de senaste upplevelserna och skydden. Vissa säkerhetsrelaterade uppdateringar kan till exempel inte bara levereras via månatliga säkerhetsuppdateringar eller signaturfiler för antivirusprogram. De kan vara lågnivåändringar i plattformen, till exempel virtualiseringsbaserad säkerhet.

[Snabbguide till Windows som en tjänst](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Skydda mot hot med hjälp av säkerhetsfunktionerna i Windows 10](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Fördelar med modellen med kumulativa uppdateringar

Att leverera kvalitets- och säkerhetsuppdateringar som ett kumulativt uppdateringspaket åtgärdar många problem som fanns tidigare. Då kanske du valde bland ett dussintal uppdateringar eller mer varje månad för både Windows och Office. Det skapar förstås nästan omöjliga testmatriser för support. Och om du skulle installera en version av Windows eller Office som är mer än ett år gammal kanske det skulle ta timmar, eller ibland dagar, att installera alla uppdateringar som gjorts sedan versionen gavs ut.

Med den kumulativa modellen behövs bara en uppdatering för att hålla dig uppdaterad med det senaste. Det innebär att du inte behöver distribuera lika många månadsuppdateringar. Varje uppdatering bygger på uppdateringarna från tidigare månader och innehåller alla korrigeringar som du behöver för att bli uppdaterad. Kumulativa uppdateringar är särskilt användbara när datorer har förvarats avstängda i flera månader i väntan på att delas ut till andra användare.

### <a name="expanded-validation-of-updates"></a>Utökad verifiering av uppdateringar

En annan fördel är att vi kan börja med att släppa versioner till små användargrupper via Insider-program för [Office](https://products.office.com/office-insider?tab=Windows-Desktop) och [Windows](https://insider.windows.com/), vilket ger oss möjlighet att samla in diagnostikdata och feedback innan vi släpper uppdateringarna till alla användare. Nu är Insider-programmen öppna för alla så att du kan utforska nya funktioner i förväg. När det är dags att göra uppdateringarna allmänt tillgängliga har vi fått diagnostikdata från miljontals konfigurationer, vilket innebär att uppdateringarna får bättre kvalitet och stabilitet.

Och eftersom Insider-versionerna av Microsoft 365-applikationer för företag återspeglar uppdateringarna i månadskanalen kan du verifiera dessa versioner tidigt och använda versionerna i halvårskanalen, om du använder halvårskanalen för Office för att leverera funktionsuppdateringar två gånger per år som för Windows.

### <a name="supporting-management-tools"></a>Hanteringsverktyg

Vi har även funderat på vi kan underlätta din distribution av uppdateringarna. Configuration Manager (aktuell gren) uppdateras ofta för att stödja distributionen av uppdateringarna till Windows och Office och alla nya funktioner.

[Distribuera Windows 10-uppdateringar med Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Hantera Microsoft 365-applikationer för företag med Configuration Manager](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Översikt över Windows- och Office-kanalerna

Windows 10 har tre underhållskanaler:

- [**Windows Insider Program**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) för organisationer som vill testa och ge feedback om funktioner som levereras i nästa funktionsuppdatering
- **Halvårskanalen** tillhandahåller ny funktionalitet med funktionsuppdateringar två gånger per år
- **Den långsiktiga underhållskanalen** är endast avsedd för specialiserade enheter som behöver ett längre underhållsalternativ

Microsoft 365 har fyra underhållskanaler:

- [**Office Insider Program**](https://products.office.com/office-insider) för organisationer som vill testa och ge feedback om de nyaste funktionerna i Office som fortfarande är under utveckling
- **Månatliga kanaler** för att ge användarna de senaste Office-funktionerna så snart de blir tillgängliga
- **Halvårskanalen** tillhandahåller ny funktionalitet med nya funktioner två gånger per år
- **Halvårskanalen (riktad)** är en version av Office med fullständigt stöd som gör det möjligt för pilotanvändare och programkompatibilitstestare att testa och verifiera nästa halvårskanal

Detaljerad information om underhållskanalerna för Windows och Office finns i dokumentationen nedan:

- [Översikt över Windows som en tjänst](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Översikt över uppdateringskanaler för Microsoft 365-applikationer](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>Fasindelad distribution av uppdateringar

Nu ska vi gå igenom hur de här uppdateringarna ska distribueras. För varje version rekommenderar vi minst tre distributionsfaser för IT – verifiering, pilottestning och bred distribution. När du har kommit igång med Windows 10 och Microsoft 365-applikationer för företag använder du månadsunderhåll för att få de senaste kritiska säkerhets- och kvalitetsuppdateringarna och sedan övergår du till halvårsunderhåll för nya funktioner.

### <a name="monthly-updating"></a>Månatliga uppdateringar

Tjänstmodellen är utformad så att du kan välja att begränsa distributionen av nya funktioner till två gånger per år, och om det behövs kan du även hoppa över en halvårsuppdatering och fortsätta få kvalitets- och säkerhetsuppdateringar. Som vi nämnde tidigare innebär de kumulativa månadsuppdateringarna att de blir större för varje månad.

#### <a name="express-updates"></a>Express-uppdateringar

Nedladdningsstorleken kan minskas markant med hjälp av en teknik som heter ”Express-uppdateringar” i Windows och komprimering av binärfilsförändring i Office. Båda dessa metoder innebär att uppdateringsmotorerna kontrollerar vad som redan finns på datorn och bara uppdaterar skillnaden mellan de gamla och nya filerna.

[Förklaring av kvalitetsuppdateringar i Windows 10 och upphörandet av uppdateringar av ändringar](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update för företag och Windows Server Update Services har länge kunnat använda Express-uppdateringar, men nu har stödet utökats så att Express-uppdateringar även kan användas av Microsoft Endpoint Configuration Manager (aktuell gren).

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Komprimering av binärfilsförändring

Komprimering av binärfilsförändring (Binary Delta Compression) i Office används bara om du uppdaterar från den senaste versionen av Microsoft 365-applikationer för företag. Om du vill använda den här metoden måste du alltså uppdatera från den tidigare versionen och du kan inte hoppa över uppdateringar.

Uppdateringskanalerna för Windows och Office kan hanteras via Configuration Manager via den vanliga processen för godkännande och målanpassning. Du kan också använda principinställningar i Office och Windows till att tillämpa uppdateringskanaler och relaterade inställningar.

### <a name="semi-annual-updates"></a>Halvårsuppdateringar

Det var övervägandena för månadsuppdateringarna. Nu går vi vidare till de större halvårsuppdateringarna.

Som vi nämnde i Beredskap för enheter och appar börjar du med att förbereda för dessa större uppdateringar med hjälp av samma beredskapsverktyg som vi konfigurerade i steg 1 i distributionsprocesshjulet.

När det gäller verktyg kan du använda principinställningarna med Windows Update för företag, hantering av programvaruuppdateringar via Microsoft Endpoint Configuration Manager (aktuell gren), Windows Server Update Services (WSUS) eller uppdateringsprinciper som angetts av Microsoft Intune. Om du är orolig för nätverksbandbredden kan du se Steg 2: Katalog- och nätverksberedskap. Där kan du läsa mer om alternativ för att minska nätverkstrafiken via leveransoptimering och andra P2P-cachelagringstekniker.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Windows halvårskanal](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Halvårskanal för Microsoft 365-applikationer](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Aktivitetssekvenser för uppgradering

Det går att installera stora funktionsuppdateringar via de vanliga rutinerna för hantering av programvaruuppdatering, men många organisationer väljer att använda en aktivitetssekvens för uppgradering med Microsoft Endpoint Configuration Manager (aktuell gren) eller Microsoft Deployment Toolkit.

Med en aktivitetssekvens kan du skapa anpassade kontroller eller aktiviteter innan du installerar funktionsuppdateringen. Och du kan utföra anpassade aktiviteter efter att själva uppdateringen har slutförts. Aktiviteter efter uppdateringen kan till exempel vara att tillfälligt pausa tjänster om det behövs under uppdateringen, installation och ersättning av drivrutiner, programuppgraderingar eller anpassade inställningar för Aktivitetsfältet eller Start i Windows 10.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

Om du redan använder aktivitetssekvenser för att migrera dina Windows 7-datorer till Windows 10 och vet hur dessa verktyg fungerar, ger detta bästa möjliga kontroll och är en bra plats att börja på. Du kan använda en enda aktivitetssekvens för hela uppgraderingen, men det är ganska vanligt att organisationer använder två aktivitetssekvenser. Det vill säga en aktivitetssekvens för att säkerställa att datorerna är redo för uppgraderingen (som tyst förinstallerar alla nödvändiga installationsfiler på måldatorerna) och en aktivitetssekvens för att utföra den faktiska uppgraderingen. Användarna störs inte lika mycket av uppgraderingen om du använder den här metoden.

[Skapa en aktivitetssekvens för att uppgradera ett operativsystem i Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Support för funktionsuppdateringar i halvårskanalen

[Som vi meddelade i september 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) används följande modell för supporttider för uppdateringar i halvårskanalen.

  - Alla funktionsuppdateringar i Windows 10 Enterprise och Education som för närvarande stöds, från och med version 1607, får support i 30 månader från den ursprungliga utgivningsdagen.

  - Alla framtida funktionsuppdateringar, från och med version 1809, med september som mål, får support i 30 månader från utgivningsdagen.

  - Kommande funktionsuppdateringar, från och med version 1903, med mars som mål får support i 18 månader från utgivningsdagen.

  - Halvårsuppdateringarna för Microsoft 365-applikationer för företag fortsätter att få support i 18 månader

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Ytterligare alternativ för automatiserad installation utöver aktivitetssekvenser

Om du inte använder aktivitetssekvenser för uppgradering kan du nu köra anpassade åtgärder eller använda drivrutinsfiler under funktionsuppdateringar i förinstallationsfasen innan installationsprogrammet kör kompatibilitetskontroller, eller i förallokeringsfasen innan uppgraderingen tillämpas.

[Nyheter om installationsprogrammet för Windows 10, version 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Nästa steg 

## <a name="step-8-user-communications-and-training"></a>[Steg 8: Kommunikation och utbildning för användare](https://aka.ms/mdd8)

## <a name="previous-step"></a>Föregående steg 

## <a name="step-6-os-deployment-and-feature-updates"></a>[Steg 6: Distribution av operativsystem och uppdateringar av funktioner](https://aka.ms/mdd6)
