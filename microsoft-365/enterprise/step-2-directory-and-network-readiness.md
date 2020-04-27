---
title: Steg 2 – Katalog- och nätverksberedskap
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig att utvärdera katalog- och nätverksberedskap i miljön.
ms.openlocfilehash: 4db179a2ed4c2aada841e8f7a4ed824aa1e190ff
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636814"
---
# <a name="step-2-directory-and-network-readiness"></a>Steg 2: Katalog- och nätverksberedskap

Kontrollera att katalog och nätverk är konfigurerade och kan stöda övergången till Windows 10 och Microsoft 365-applikationer för företag. Det innebär att användarna måste ha Azure Active Directory-tjänster och nätverket måste ha den kapacitet som krävs för att kunna hantera både den normala trafiken och rörelsen av potentiellt stora data när datorerna uppgraderas och användarnas filer, inställningar och program återställs.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Steg 2: Katalog- och nätverksberedskap</strong></p>
<p>Molnanslutna tjänster i Microsoft 365-applikationer för företag och nya distributionsalternativ som Windows Autopilot kräver Azure Active Directory. Ditt nätverk och dina anslutningar är också viktiga när du planerar att flytta Windows-avbildningar, appar, drivrutiner och relaterade filer till datorerna. Lär dig hur nya verktyg och distributionsalternativ minskar och effektiviserar nätverkstrafiken.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Katalog- och nätverksberedskapen är det andra steget i vår rekommenderade distributionsprocess som fokuserar på Azure Active Directory och optimerar nätverket. Om du vill se en fullständig skrivbordsdistribution kan du besöka [Center för skrivbordsdistribution](https://aka.ms/HowToShift).
>

Katalog- och nätverksberedskapen är grundläggande i att säkerställa en smidig distribution av operativsystem och skrivbord. Precis som med all automatisk distribution är det viktigt att se till att dina filresurser går att nå och att nätverket kan överföra mycket stora filer åt gången. Det kan röra sig om hundratals eller till och med tusentals datorer.

När du övergår till Windows 10 och Microsoft 365-applikationer för företag måste du se till att den molnbaserade identiteten är konfigurerad med Azure Active Directory. Det är viktigt inte bara för att aktivera Microsoft 365-applikationer för företag, utan också för att du då kan dra nytta av moderna etableringslösningar som Windows Autopilot.

I den här artikeln ska vi utforska verktygen och alternativen för att förbereda katalogtjänster och användar- och enhetsbehörigheter så att de är redo för distribution till Windows 10 och Microsoft 365-applikationer för företag.

## <a name="adding-azure-active-directory"></a>Lägga till Azure Active Directory

Om din organisation redan använder Office 365, Exchange Online, Microsoft Intune eller andra Microsoft Online-tjänster, använder du redan Azure Active Directory. I så fall behöver du bara säkerställa att de användare som omfattas av skrivbordsdistributionen finns i din Azure Active Directory och att licenserna har tilldelats.

Om du inte använder Azure Active Directory för närvarande finns det [flera resurser](https://docs.microsoft.com/azure/active-directory/) som hjälper dig att installera det. Du kan vara berättigad till personlig hjälp via Microsoft FastTrack som en del av din licens. Mer information om Microsoft FastTrack finns [här](https://fasttrack.microsoft.com).

När du har Azure Active Directory på plats kan användarna logga in på och aktivera sina appar i Microsoft 365-applikationer för företag. Du kan även använda Microsoft Intune eller Windows Autopilot-distribution för att distribuera appar och principer automatiskt.

## <a name="network-readiness"></a>Nätverksberedskap

Du måste överväga bandbreddskraven när du planerar distributionerna. Det finns tre huvudsakliga komponenter i en distribution som påverkar nätverket – datoravbildning, programvaruuppdateringar och användaranpassning. Detta kan innebära att mer än 20 GB per dator används vid den första migreringen och sedan att 1 GB eller mer krävs per månad och dator för att vara uppdaterad.

Vi börjar med att granska kraven för var och en av de tre huvudkomponenterna:

### <a name="pc-imaging"></a>Datoravbildning

Vid Windows-avbildningar utan anpassning bör du vanligtvis planera för 3 GB per dator, men vid anpassade avbildningar med appar kan du behöva tillåta 6 GB eller mer. Du kan även behöva fundera över drivrutinspaketen. De kan bestå av flera hundra megabyte per dator, ibland upp till 1 GB.

### <a name="software-updates"></a>Programuppdateringar

Du måste planera nätverksbandbredden vid programuppdateringar. Windows 10 och Microsoft 365-applikationer för företag använder en ny tjänstmodell som levererar månatliga och halvårsvisa uppdateringar. Om du inte har använt den här modellen förut, kan du lära dig mer om hur den fungerar [här](https://docs.microsoft.com/windows/deployment/update/waas-overview).

Den nya tjänstmodellen innehåller funktionsuppdateringar för Windows två gånger om året, uppdateringar av Office halvårskanal och månatliga kvalitetsuppdateringar. Funktionsuppdateringar är vanligtvis 2–4 GB i storlek och uppdateringar av Office halvårskanal är 300–400 MB per uppdatering. Det finns även månatliga kvalitetsuppdateringar. De kan variera från några hundra megabyte till drygt en gigabyte. Det beror på att månatliga uppdateringar är kumulativa, så storleken ökar under tjänstens livstid för varje Windows 10-version. Det finns verktyg som kan hjälpa till att minska mängden data som måste överföras via nätverket när uppdateringar implementeras. Vi kommer att beskriva detta mer detaljerat nedan.

### <a name="user-personalization"></a>Användaranpassning

Den tredje komponenten att tänka på är användaranpassning. Här måste du planera nätverksbandbredden för att få plats med att återställa användarfiler, deras inställningar och program i processen att uppdatera eller ersätta datorn. Tillsammans överstiger objekten ofta 20 GB per dator, men för vissa användare kan de överstiga 100 GB.

## <a name="limiting-bandwidth"></a>Begränsa bandbredden

Ett sätt att begränsa effekten av distributionsrelaterad trafik i nätverket, är att begränsa den genom att använda BITS-inställningen (Background Intelligent Transfer Service) på klienterna. I BITS används en ABR (Adaptive Bit Rate) för att justera tillgänglig bandbredd för distributionsändamål. Den kan konfigureras på klienter med hjälp av grupprinciper.

[Om BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Om du använder konfigurationshanteraren för Microsoft Endpoint (aktuell förgrening) kan du också konfigurera BITS-aktiverade distributionsplatser eller aktivera multicast med WDS.

Att begränsa specifik trafik innebär att normal nätverkstrafik påverkas mindre av att datorerna laddar ned uppdateringar och program. Men genom att tilldela en viss procentandel av bandbredden till de här aktiviteterna, påverkas produktiviteten inte alls av Windows- eller Office-distributionen. Processerna fortsätter att fungera, men distributionsrelaterade driftstopp kan förvärras och användare kan vara utelåsta från sina datorer medan distributionen körs.

Som tur är finns det nya verktyg som gör det enklare för dig att hantera nätverkets påverkan vid en storskalig skrivbordsdistribution, exempelvis LEDBAT som optimerar användningen av tillgänglig bandbredd och P2P-alternativ som flyttar bort distributionstrafiken från mitten av nätverket och ut i perimeternätverket

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Rensa bandbredden

LEDBAT (Low Extra Delay Background Transport) som stöds i Windows Server 2019 och konfigurationshanteraren för Microsoft Endpoint (aktuell förgrening), är utformad för att optimera nätverkstrafiken till Windows-klienter.

[De 10 viktigaste nätverksfunktionerna i Windows Server 2019: \#9 LEDBAT – Svarstidsoptimerad bakgrundstransport](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Till skillnad från traditionella begränsningar kan LEDBAT använda all tillgänglig bandbredd i nätverket som en bakgrundsaktivitet, vilket ger direkt bandbredd när annan trafik begär det. Till skillnad från BITS finns inte någon fördröjning. Allt sker automatiskt – ingen manuell justering eller schemaläggning krävs och allt konfigureras på serversidan. Detta ger potentiellt enorma prestandavinster.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Peer to peer-alternativ

Peer to peer-alternativen används allt mer i Windows 10-migreringar, för datoravbildning, programuppdatering och användaranpassning. De är också värdefulla för att underlätta build till build-uppgraderingar efter din första Windows 10-distribution. Här visar vi flera exempel som hjälp vid flytt av Windows 10- och Office-relaterad trafik från mitten av nätverket, för att minska behovet av klassiska begränsningar och låta datorerna hitta de uppdateringsfiler de behöver i det lokala nätverket i stället för att hämta dem från en distributionsplats eller Internet.

Med **BranchCache** kan du ladda ned innehåll i distribuerade miljöer utan att påverka nätverket negativt. Det finns två alternativ: Värdbaserat cacheläge, där du använder lokala servrar för att cachelagra innehåll och Distribuerat cacheläge (stöds i konfigurationshanteraren), som innebär att klienterna delar redan hämtat innehåll med varandra.

**Peer-cachelagring** Klienter som stöds av konfigurationshanteraren kan också använda peer-cachelagring. På så sätt kan tillgängliga datorer i nätverket vara värdar för innehållsdistribution. Du bör endast aktivera målenheter med pålitliga nätverksanslutningar som värdar (t.ex. stationära datorer, minitorn och torndatorer). Peer-cachelagring kan även användas för distributionsuppgifter som körs i Windows PE under installationen.

Obs! BranchCache och Peer-cachelagring kompletterar varandra och kan användas tillsammans i samma miljö.

[BranchCache jämfört med Peer-cachelagring](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Leveransoptimering** Leveransoptimering är en annan peer-to-peer-cachelagring som tillhandahåller nätverksbaserade kontroller av distributioner. Leveransoptimeringen i Windows 10 uppdaterar inbyggda UWP-appar, installerar program från Microsoft Store och programuppdateringar med hjälp av Express Updates. Den fanns redan i tidiga versioner av Windows 10, men den har nyligen integrerats med konfigurationshanteraren för Microsoft Endpoint (aktuell förgrening). Sedan Windows 10 version 1803 innebär de nya konfigurationsalternativen att du kan ange fristående bandbreddsbegränsningar för bakgrundsuppdateringar och förgrundsjobb, t.ex. en programinstallation från Store. Leveransoptimeringen i Windows har också stöd för Microsoft 365-applikationer för företag under klientuppdateringar, vilka finns i alla klientuppdateringskanaler som stöds. Stöd för leveransoptimering i Windows under den initiala klientinstallationen kommer snart.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Ytterligare överväganden för Microsoft 365-applikationer för företag**

Förutom leveransoptimeringen finns det tre saker som bidrar till att minska belastningen på nätverket vid distributioner av Microsoft 365-applikationer för företag.

**Binary Delta Compression** Microsoft 365-applikationer för företag använder Binary Delta Compression (komprimering av binärfilsförändring) för att minska bandbredden som används av programuppdateringar vid uppdatering från den senaste Microsoft 365-applikationer för företag-versionen till nästa version. Genom att bara hämta de binära nivåändringarna från föregående version, minimeras påverkan från de ökade storlekarna per månad vid kumulativa uppdateringar. Det går att spara hundratals megabyte data per dator varje månad. För att kunna använda den här funktionen kan du inte hoppa över några versioner. Om du gör det måste du ladda ned den fullständiga kumulativa uppdateringen.

[Ladda ned uppdateringar för Office 365](https://docs.microsoft.com/deployoffice/overview-of-the-update-process-for-office-365-proplus#download-the-updates-for-office-365-proplus)

**Outlook-datafiler** Outlook är ofta konfigurerat att cachelagra användarens hela postlåda lokalt för användning offline. I de flesta Windows-distributioner, utom vid på-plats-uppgraderingar, kräver detta att användarens Outlook-datafiler återskapar sig själva efter uppgraderingen. Det här är en automatisk process, men med begränsningarna i Outlook-postlådan som vanligtvis är upp till 100 GB, innebär en ny cachelagring av hela postlådan lokalt för alla användare stora dataöverföringar. Om du vill minska belastningen på nätverket kan du använda en grupprincip för att minska inställningen ”E-post som ska behållas offline”. I Microsoft 365-applikationer för företag eller Office 2016 är standardvärdet för Outlook inställt på 12 månader. Om du vill minska risken för nätverkspåverkan kan du ställa in offlinecachen på mellan 1 och 6 månader. Att ändra inställningen påverkar inte din onlinepostlådas storlek och hela postlådan kan fortfarande sökas igenom i Outlook när du är online.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**OneDrive-filer på begäran och Flytt av känd mapp** OneDrive är ett bra sätt att synkronisera och skydda användarfiler från datorer och andra enheter i molnet. Med Flytt av känd mapp kan du framtvinga filsynkronisering från en användares mappar Skrivbord, Dokument och Bilder till OneDrive, så att filerna blir tillgängliga när de loggar in på en ny enhet eller en dator med en återställd avbildning. Kom ihåg att den totala storleken och antalet filer som finns i Skrivbord, Dokument och Bilder innebär att du bör planera distributionen av principer som aktiverar och tillämpar OneDrive på datorerna. Ett alternativ är att använda nätverkskontrollerna för grupprinciper till att begränsa bandbredden som används av OneDrive-synkroniseringstjänsten.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Konfigurera Flytt av känd mapp](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[OneDrive-filer på begäran](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Om du inte redan har distribuerat OneDrive är övergången från Windows 7 till Windows 10 en perfekt tidpunkt att aktivera OneDrive och integrera Microsoft 365-applikationer för företag. Det kan vara en bra idé att börja distribuera samtidigt som du granskar beredskapen för appar och enheter. Detta ger filsynkroniseringen ett försprång innan du börjar flytta Windows-avbildningar och distribuera appar via nätverket.

## <a name="next-step"></a>Nästa steg 

## <a name="step-3-office-and-lob-app-delivery"></a>[Steg 3: Leverans av Office och verksamhetsspecifika appar](https://aka.ms/mdd3)

## <a name="previous-step"></a>Föregående steg:

## <a name="step-1-device-and-app-readiness"></a>[Steg 1: Beredskap för enheter och appar](https://aka.ms/mdd1)

## <a name="feedback"></a>Feedback

Vi vill gärna höra vad du tycker. Välj önskad typ:

Produktfeedback Logga in för att ge feedback om dokumentationen

Vårt nya feedbacksystem bygger på GitHub-ärenden. Läs mer om den här ändringen i vårt blogginlägg.
