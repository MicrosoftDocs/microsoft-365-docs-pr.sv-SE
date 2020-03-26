---
title: Office 365 ProPlus-distribution för Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Endpoint Configuration Managerför att distribuera Office 365 ProPlus.
ms.openlocfilehash: 45c9933ea04632b255acfa1062ae7ecaf9810030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812565"
---
# <a name="office-365-proplus-deployment-for-contoso"></a>Office 365 ProPlus-distribution för Contoso

Contoso uppgraderade datorerna till Windows 10 Enterprise och Office 365 ProPlus för att få effektivare samarbete, bättre säkerhet och en modernare skrivbordsanvändning. Efter att ha uppskattat deras infrastruktur- och företagsbehov identifierade Contoso de viktigaste kraven för distributionen:

- Alla datorer ska köra Office 365 ProPlus
- Distribution bör använda befintliga hanteringsverktyg och infrastruktur när det är möjligt
- Distributionen måste ha stöd för flera språk och befintliga arkitekturer på slutanvändarens enheter
- Datorerna ska vara uppdaterade och säkra med minimala IT-administrativa kostnader och minsta möjliga påverkan på slutanvändarna

## <a name="deployment-tools"></a>Distributionsverktyg

Contoso valde att distribuera Windows 10 Enterprise och Office 365 ProPlus med Configuration Manager (Current Branch) baserat på sina krav. Configuration Manager kan skalas för stora miljöer och tillhandahåller omfattande kontroll över installation, uppdateringar och inställningar. Den har också inbyggda funktioner som gör det enklare och mer effektivt att distribuera och hantera Office, däribland:

- Peer-cachelagring, som kan hjälpa dig med begränsad nätverkskapacitet vid distribution till enheter på fjärranslutna platser
- Instrumentpanelen Office Client Management, som gör det enkelt att distribuera Office och övervaka uppdateringar och ger administratörer tillgång till de senaste funktionerna för distribution och hantering
- Installation av intelligent språkpaket, inklusive automatisk distribution av samma språk som operativsystemet
- Komplett och lättanvänd metod för att ta bort befintliga versioner av Office från en klient under distributionen

Förutom Configuration Manager använde Contoso [Readiness Toolkit](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro), ett kostnadsfritt verktyg från Microsoft, för att utvärdera kompatibilitetsproblem med Office-makron och -tillägg.

## <a name="managing-the-deployment-and-updates"></a>Hantera distribution och uppdateringar

Office 365 ProPlus har en ny versionsmodell: Office som tjänst. Med tjänstmodellen kan du enkelt hålla dig uppdaterad om nya funktioner, men oftast krävs en förändring av IT-avdelningarna för hur nya versioner distribueras och testas. För att minimera kompatibilitetsproblem och säkerställa att datorerna är uppdaterade distribuerade Contoso Windows och Office i två steg: 

- För det första steget distribuerade Office 365 ProPlus till en liten uppsättning representativa enheter i organisationen. Den här pilotgruppen användes för att testa appar, tillägg och maskinvara med Office 365 ProPlus
- Fyra månader senare distribuerade Contoso Office 365 ProPlus till resten av enheterna i organisationen (den omfattande gruppen) när du har åtgärdat alla kritiska problem med appar, tillägg och maskinvara i pilotgruppen. 

I stället för att hantera uppdateringar för Office med Configuration Manager har Contoso aktiverat automatiska uppdateringar i molnet. Molnbaserade uppdateringar minskade administrationsbehovet medan enheterna är uppdaterade. 

Contoso följde samma två steg för funktionsuppdateringar som de använde för att distribuera Office: enheter i pilotgruppen mottog uppdateringar fyra månader tidigare än enheter i resten av organisationen (den omfattande gruppen). För att aktivera detta för Office använde Contoso två rekommenderade [uppdateringskanaler](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus): 

- Halvårsvis kanal (riktad) för uppdateringar till pilotgruppen 
- Halvårsvis kanal för uppdateringar till den omfattande gruppen. 

Eftersom den halvårsvisa kanalen (riktad) lanserar en version av Office 365 ProPlus fyra månader tidigare än den halvårsvisa kanalen har Contoso tid att validera uppdateringarna utan att behöva hantera dem. 

## <a name="deployment-process"></a>Distributionsprocess

För att slutföra distributionen av Office genomför Contoso följande process, som innehåller rekommendationer från Microsoft:

1. Före distributionen använde de verktyg för beredskap för att testa apparna och Office-tilläggen för att bedöma deras kompatibilitet med Office 365 ProPlus.
2. I Configuration Manager aktiverade Contoso peer-cachelagring på klientenheterna, som hjälpte dem med begränsad nätverkskapacitet vid distribution till klientenheter på fjärranslutna platser. 
3. De definierade två distributionsgrupper som enhetssamlingar i Configuration Manager: en pilotgrupp och en omfattande grupp. Pilotgruppen, som innehöll en liten uppsättning representativa enheter i hela organisationen, användes för att göra ytterligare tester av program, tillägg och maskinvara med Windows 10 Enterprise och Office 365 ProPlus. 
4. De skapade distributionspaket för Office med hjälp av instrumentpanelen Office Client Management och installationsguiden för Office 365, som båda är en del av Configuration Manager-konsolen. De har skapat två Office 365-ProPlus-paket, ett för pilotgruppen på den halvårsvisa kanalen (riktad) och en för den omfattande gruppen för den halvårsvisa kanalen. 
5. Som en del av ett Office-paket innehöll de språkpaket på engelska, franska och tyska. Om en enhet krävde ett språk som inte ingår i Office-paketet laddades det ned automatiskt från Office Content Delivery Network (CDN).
6. De använde den inbyggda funktionen i Office-paketet för att automatiskt ta bort alla befintliga MSI-versioner av Office innan de installerade Office 365 ProPlus.
7. I Configuration Manager distribuerade de Windows- och Office-paket till distributionsplatser via nätverket, och körde sedan aktivitetssekvenser för Configuration Manager-distribution för att distribuera Office 365 ProPlus-paketet till pilotgruppen.
8. När de hade stött på kompatibilitetsproblem med pilotgruppen körde Contoso aktivitetssekvenser för distribution av det bredaste Office 365 ProPlus-paketet till den omfattande gruppen.

Eftersom Contoso valde att uppdatera enheter automatiskt från molnet behövde processen inte hanteras i Configuration Manager. Deras enheter uppdateras automatiskt direkt från molnet, baserat på uppdateringen som definierades som en del av den första distributionen. 

Här är Contosos Office 365-ProPlus installation och pågående uppdateringars distributionsarkitektur.

![Contosos Office 365 ProPlus-distributionsinfrastruktur](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Nästa steg

[Ta reda på mer](contoso-mdm.md) om hur Contoso använder Microsoft Intune i Microsoft 365 Enterprise för att hantera sina enheter och apparna som körs på dem i sin organisation.

## <a name="see-also"></a>Snabbreferens

[Office 365 ProPlus för Microsoft 365 Enterprise](office365proplus-infrastructure.md)

[Distributionsguide](deploy-microsoft-365-enterprise.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)
