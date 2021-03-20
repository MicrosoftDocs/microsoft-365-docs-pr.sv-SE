---
title: Microsoft 365-applikationer för företagsdistribution av Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso använder Microsoft Endpoint Configuration Manager för att distribuera Microsoft 365-applikationer för företag.
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907680"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Microsoft 365-applikationer för företagsdistribution av Contoso

Contoso uppgraderade datorerna till Windows 10 Enterprise och Microsoft 365-applikationer för företag för att få effektivare samarbete, bättre säkerhet och en modernare skrivbordsanvändning. Efter att contoso granskat deras infrastruktur- och affärsbehov identifierade contoso följande nyckelkrav för distributionen:

- Alla datorer bör köra Microsoft 365-appar för företag.
- Distributionen bör när det är möjligt använda befintliga hanteringsverktyg och infrastruktur.
- Distributionen måste ha stöd för flera språk och befintliga arkitekturer på användarnas enheter.
- Datorer bör hålla sig uppdaterade och skyddade med minimala administrativa kostnader och en minimal påverkan på användarna.

## <a name="deployment-tools"></a>Distributionsverktyg

Utifrån deras krav har Contoso valt att distribuera Windows 10 Enterprise- och Microsoft 365-appar för företag via Configuration Manager (Current Branch). Configuration Manager kan skalas för stora miljöer och tillhandahåller omfattande kontroll över installation, uppdateringar och inställningar. Den har också inbyggda funktioner som gör det enklare och mer effektivt att distribuera och hantera Office, däribland:

- Peer cache, som kan hjälpa till med begränsad nätverkskapacitet när du distribuerar till enheter på fjärranslutna platser.
- Instrumentpanelen för klienthantering i Office, som gör det enkelt att distribuera Office och övervaka uppdateringar och ger administratörer tillgång till de senaste distributions- och hanteringsfunktionerna.
- Intelligent språkpaketsdistribution, inklusive automatisk distribution av samma språk som operativsystemet.
- En metod som stöds och är enkel att använda för att ta bort befintliga versioner av Office från en klient under distributionen.

Utöver Configuration Manager använde Contoso readiness toolkit för [Office-tillägg](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)och VBA , ett kostnadsfritt verktyg från Microsoft, för att bedöma kompatibilitetsproblem med sina Office-makron och tillägg.

## <a name="managing-deployment-and-updates"></a>Hantera distribution och uppdateringar

Microsoft 365-applikationer för företag har en ny versionsmodell: Office som tjänst. Med tjänstmodellen är det enkelt att hålla dig uppdaterad med nya funktioner. Men det kräver ofta att IT-avdelningarna ändrar hur de distribuerar och testar nya versioner. För att minimera kompatibilitetsproblem och se till att deras datorer är uppdaterade har Contoso distribuerat Windows och Office i två steg:

- Först distribuerade de Microsoft 365-appar för företag till ett litet antal representativa enheter i hela organisationen. Den här pilotgruppen användes för att testa appar, tillägg och maskinvara med Microsoft 365-appar för företag.
- Fyra månader senare distribuerade Contoso Microsoft 365-applikationer för företag till resten av enheterna i organisationen (den omfattande gruppen) när du har åtgärdat alla kritiska problem med appar, tillägg och maskinvara i pilotgruppen.

I stället för att hantera uppdateringar till Office med hjälp av Konfigurationshanteraren aktiverade Contoso automatiska uppdateringar från molnet. Molnbaserade uppdateringar minskar det administrativa arbetet samtidigt som du ser till att enheterna är uppdaterade.

Contoso följde samma metod i två steg för funktionsuppdateringar som de använde för att distribuera Office: Enheter i pilotgruppen tog emot funktionsuppdateringar fyra månader tidigare än enheter i resten av organisationen (den breda gruppen). För att aktivera detta för Office använde Contoso två rekommenderade [uppdateringskanaler](/DeployOffice/overview-update-channels):

- Halvårsvis kanal (riktad) för uppdateringar av pilotgruppen
- Semi-Annual Enterprise-kanalen för uppdateringar för den breda gruppen

Eftersom den halvårsvisa kanalen (riktad) lanserar en version av Microsoft 365-applikationer för företag fyra månader tidigare än den halvårsvisa kanalen har Contoso tid att validera uppdateringarna utan att behöva hantera dem.

## <a name="deployment-process"></a>Distributionsprocess

För att slutföra distributionen av Office genomför Contoso följande process, som innehåller rekommendationer från Microsoft:

1. Före distributionen använde Contoso tillägget Readiness Toolkit för Office och VBA för att testa sina appar och Office-tillägg för att bedöma deras kompatibilitet med Microsoft 365-appar för företag.
1. I Konfigurationshanteraren aktiverade de peer cache på sina klientenheter, vilket hjälper till med begränsad nätverkskapacitet vid distribution till klientenheter på fjärranslutna platser. 
1. Contoso definierade två distributionsgrupper som enhetssamlingar i Konfigurationshanteraren: en pilotgrupp och en bred grupp. Pilotgruppen, som innehöll en liten uppsättning representativa enheter i hela organisationen, användes för ytterligare testning av appar, tillägg och maskinvara med Windows 10 Enterprise och Microsoft 365-appar för företag.
1. De skapade distributionspaket för Office med hjälp av instrumentpanelen för Klienthantering i Office och Office 365-installationsguiden, som båda är en del av konfigurationshanterarens konsol. De har skapat två paket för Microsoft 365-applikationer för företag, ett för pilotgruppen på den halvårsvisa kanalen (riktad) och en för den omfattande gruppen för den halvårsvisa kanalen.
2. Varje Office-paket innehåller språkpaket för engelska, franska och tyska. Om en enhet krävde ett språk som inte inkluderades i Office-paketet laddades det språkpaketet ned automatiskt från Office Content Delivery Network (CDN).
3. De använde den inbyggda funktionen i Office-paketet för att automatiskt ta bort alla befintliga MSI-versioner av Office innan de installerade Microsoft 365-applikationer för företag.
4. I Configuration Manager distribuerade de Windows- och Office-paketen till distributionspunkter över deras nätverk. Sedan körde de distributionssekvenser för Konfigurationshanteraren för att distribuera Microsoft 365-pilotpaketet Program för företag till pilotgruppen.
5. När de har åtgärdat kompatibilitetsproblem med pilotgruppen körde Contoso aktivitetsserierna för att distribuera Microsoft 365-programmen för företag-paketet till den breda gruppen.

Eftersom Contoso valde att uppdatera enheter automatiskt från molnet behövde processen inte hanteras i Configuration Manager. Deras enheter uppdateras automatiskt direkt från molnet baserat på uppdateringskanalen som definierades i den första distributionen.

Här är Contoso Microsoft 365-programmen för företagsinstallation och ständiga distributionsarkitekturen för uppdateringar.

![Contoso-distributionsinfrastrukturen för Microsoft 365-program för företag](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Nästa steg

Läs om hur Contoso använder [Microsoft Intune](contoso-mdm.md) i Microsoft 365 för företag för att hantera dess enheter och appar som de kör i organisationen.

## <a name="see-also"></a>Se även

[Microsoft 365 Apps för företag](/deployoffice/deployment-guide-microsoft-365-apps)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)