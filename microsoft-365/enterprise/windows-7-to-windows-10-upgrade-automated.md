---
title: Automatiserade uppgraderingar av Windows 7 till Windows 10
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 07/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Automatiserade uppgraderingar av Windows 7 till Windows 10 för stora organisationer
ms.openlocfilehash: f9ba1022b4c7f702f6cb9b815deee59047c4b704
ms.sourcegitcommit: 9ca28ae8f7804eb488cf76ca4b09fe88787e0a49
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43113487"
---
# <a name="windows-7-to-windows-10-automated-in-place-upgrades-for-large-organizations"></a>Automatiserade på plats-uppgraderingar av Windows 7 till Windows 10 för stora organisationer

Från den 14 januari 2020 tillhandahålls inte längre säkerhetsuppdateringar eller support för datorer med Windows 7. Eftersom det finns många distributionsalternativ för att byta från Windows 7 till Windows 10 är en vanlig fråga i IT-communityn vilket som är det snabbaste sättet att gå över från Windows 7 till Windows 10. Det korta svaret är att göra på plats-uppgraderingar för befintliga datorer och därefter minska fokus på flera aspekter av datordistributionsprocessen.

<center><img src="../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-1.png" alt="wheel" height="421" width="500" /></center>

Med på plats-uppgraderingar minskas omfattningen för flera datordistributionsprocesser dramatiskt, särskilt:

  - **Programpaketering** och omleverans av nödvändiga verksamhetsspecifika appar – dessa överförs helt enkelt från Windows 7-miljön

  - **Filmigrering** och grundläggande användarinställningar – dessa överförs också från den tidigare installationen när samma användare behåller enheten

De nedtonade uppgifterna i distributionsprocessen är inte objekt som du kan ignorera helt och hållet, men för att spara tid förutsätter detta att du för fram din säkerhetskonfiguration, ändrar programuppdateringsprocesser efter distributionen och vi antar att din användarutbildning för Windows-komponenten till största del har skett hemma för dina användare, då privat köpta Windows-datorer sedan 2012 för det mesta inte har haft Windows 7 förinläst och sedan släppet av Windows 10 2015 majoriteten av Windows 7-hemmasystemen också har uppgraderats till Windows 10.

## <a name="in-place-upgrade-reliability-safeguards-and-scale"></a>Tillförlitlighet, skydd och skalning för på plats-uppgraderingar

På plats-uppgraderingar till Windows 10 är en tillförlitlig metod för att flytta en befintlig enhet med Windows 7 eller senare till Windows 10, utan att kräva filmigrering eller ominstallation av program. Efter en på plats-uppgradering är användarens filer, inställningar och tillgängliga appar är konsekventa med deras tidigare Windows 7-installation. Uppgraderingar fungerar även när du flyttar från och till samma slags arkitektur (32-bitars till 32-bitars eller 64-bitars till 64-bitars) och från och till samma slags versioner av Windows (Professional till Pro eller Enterprise to Enterprise).

Uppgraderingsprocessen säkerhetskopierar som standard din tidigare Windows-installation som en del av uppgraderingen, så att vid ett uppgraderingsfel eller om en enhet eller ett program inte fungerar på rätt sätt efter uppgraderingen kan datorn återställas till Windows 7. Uppgraderade datorer har som standard 10 dagar, så du kan manuellt starta en återställning till Windows 7 om det behövs.

På plats-uppgraderingar kan automatiseras med hjälp av distributionsverktyg i operativsystemet som [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) eller [Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit). I den här artikeln beskrivs de automatiserade metoderna och optimeringarna och länkar ges till relaterade resurser där du kan få mer hjälp.

## <a name="upgrading-a-small-number-of-computers"></a>Uppgradera ett litet antal datorer

För en enstaka dator eller ett fåtal datorer är den manuella uppgraderingsmetoden vanligtvis det bästa alternativet jämfört med mer automatiserade metoder. Du hittar den nödvändiga programvaran och de licenser som behövs i [Microsoft Store](https://go.microsoft.com/fwlink/p/?LinkId=808282), hos andra programvaruåterförsäljare eller i [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx) om du har volymlicensiering. För detaljerade anvisningar om uppgradering av en enstaka dator till Windows 10 och återställningsalternativ efter uppgradering finns i [steg för steg-guiden för manuell uppgradering av Windows 7 till Windows 10](https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade).

## <a name="how-to-upgrade-many-computers"></a>Uppgradera många datorer

Om du hanterar dussintals eller tusentals datorer är det bästa alternativet att utföra på plats-uppgraderingar med aktivitetssekvensautomatisering med Microsoft Endpoint Configuration Manager eller Microsoft Deployment Toolkit. Processen är mycket tillförlitlig i de flesta fall men, beroende på hur många datorer du uppgraderar, är det ändå bra att ha nödvändig tester och kontroller på plats för att säkerställa framgång vid skalning.

Det betyder att du kan hoppa över katalogberedskap eller aktiviteter kopplade till leverans och paketering samt filmigrering för Azure Active Directory, Office och verksamhetsspecifika appar eftersom de aspekterna behålls som en del av uppgraderingen och säkerheten bör som minimum överföras. Alla dessa områden kan förbättras med tiden.

Alternativet för distributionsuppgradering tas upp i [OS-distribution och funktionsuppdateringar](https://www.aka.ms/mdd6) och trots att du enkelt kan skapa skriptlösningar som körs Windows 10-konfiguration på ett automatiserat sätt med minimal eller ingen administrationsinteraktion kan en aktivitetssekvens ge dig mer detaljerad kontroll för att:

  - utföra kontroller före distribution,

  - hantera enhetens krypteringstillstånd före uppgradering,

  - avinstallera kända problematiska drivrutiner och appar före uppgradering,

  - Installera ytterligare drivrutiner och appar efter uppgradering,

  - hantera enhetens krypteringstillstånd efter uppgradering,

  - återställa en dator till ett tidigare tillstånd – där avinstallerade appar eller drivrutiner återinstalleras – vid misslyckad uppgradering,

  - Förutom allt annat måste du konfigurera för att uppnå ett Business Ready-tillstånd

![](../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-2.png)

De vanligaste orsakerna till att uppgraderingar kanske inte slutföras eller inte är möjliga är utmaningar med följande:

  - Inaktuella enhetsdrivrutiner

  - Diskkryptering från tredje part

  - Kodlösningar på låg nivå, till exempel skydd mot skadlig kod, VPN eller virtualisering

Mallar för [uppgraderingsaktivitetssekvenser](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) är inbyggda i Microsoft Endpoint Configuration Manager (Current Branch) och har vari tillgängliga för flera versioner. I de senaste versionerna har det skett betydande tekniska förbättringar av Configuration Manager som gör processen ännu effektivare för att fastställa beredskapen för enhets- och Office-kompatibilitet, minska nätverkstrafik och konfigurera nya alternativ som OneDrive-säkerhetskopiering Titta på det här [Microsoft Mechanics-programmet](https://youtu.be/CYRnAmCD7ls) så får du mer information om de senaste uppdateringarna av OS-distribution med Configuration Manager.

Om du inte använder Microsoft Endpoint Configuration Manager kan du använda Microsoft Deployment Toolkit till att skapa och köra aktivitetssekvenser för uppgraderingsdistribution.

## <a name="pre-cache-task-sequence-upgrades"></a>Uppgraderingar med förcacheaktivitetssekvenser

Med [förcachealternativet](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system#configure-pre-cache-content) för Configuration Manager-distributionsaktivitetssekvens kan klienter ladda ned relevant innehåll i OS-uppgraderingspaketet innan aktivitetssekvensen uppgraderar operativsystemet. Tidigare skulle start av aktivitetssekvensen starta nedladdningen av paketinnehåll. Med förcacheinnehåll får du även alternativet för klienten att bara ladda ned det gällande OS-uppgraderingspaketet och allt annat refererat innehåll så snart distributionen tas emot.

Förcacheaktivitetssekvenser kombinerat med kompatibilitetskontroller

Förutom att spara tid för paketnedladdningen kan du förcachelagra uppgraderingspaketet och använda installationsprogrammet för Windows till att bedöma om på plats-uppgradering kommer att lyckas innan du kör den faktiska Windows-uppgraderingen. Följande kommandoradssyntax kan användas för att köra en kompatibilitetskontroll i bakgrunden och ta reda på om installationsprogrammet för Windows Setup bedömer att enheten är redo för uppgradering.

Loggar skickas sedan till din definierade serversökväg och installationsprogrammet för Windows visas inte för användaren och stängs utan användarinteraktion.

Resultatet av själva loggarna är följande:

1.  Om installationsprogrammet inte hittar något kompatibilitetsproblem och datorn verkar uppfylla alla krav returneras MOSETUP\_E\_COMPAT\_SCANONLY (0xC1900210)

2.  Om installationsprogrammet hittar kompatibilitetsproblem som kan åtgärdas, till exempel kända inkompatibla appar, returneras MOSETUP\_E\_COMPAT\_INSTALLREQ\_BLOCK (0xC1900208)

3.  Om installationsprogrammet finner att datorn inte är kvalificerad för Windows 10 returneras MOSETUP\_E\_COMPAT\_SYSREQ\_BLOCK (0xC1900200)

4.  Om installationsprogrammet finner att datorn inte har tillräckligt mycket ledigt utrymme för installationen returneras MOSETUP\_E\_INSTALLDISKSPACE\_BLOCK (0xC190020E)

När du har distribuerat förcachesekvenser med kompatibilitetskontroller för ett stort antal datorer i en samling kan du börja parsa loggfilerna för enhetsberedskap. Med hjälp av resultatet ovan kan \#1 (0xC1900210) åtgärdas som ”redo att distribueras” och \#4 (0xC190020E) kan åtgärdas genom att frigöra diskutrymme. Här är det viktigt att vara försiktig med vad som tas bort men Windows Update-rensning, Papperskorgen och Cleanup, Recycle Bin och Tillfälliga filer är bra ställen att börja och i många fall får du tillräckligt mycket utrymme för att uppgraderingen ska lyckas. Du kan köra kompatibilitetskontrollen så ofta det behövs till datorn är redo för på plats-uppgraderingen. Mer information om kommandoradsalternativ för installationsprogrammet för Windows på <https://aka.ms/setupswitches>

## <a name="desktop-deployment-center"></a>[Center för skrivbordsdistribution](https://aka.ms/howtoshift)
