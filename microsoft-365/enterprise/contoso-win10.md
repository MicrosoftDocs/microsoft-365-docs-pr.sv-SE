---
title: Windows 10 Enterprise-driftsättning för Contoso
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
description: Förstå hur Contoso använder Microsoft Endpoint Configuration Manager för att distribuera på plats-uppgraderingar av Windows 10 Enterprise.
ms.openlocfilehash: 7907bf64acce3af8b21459202cb6f5cbc1e9f990
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907692"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Windows 10 Enterprise-driftsättning för Contoso

Innan den omfattande utrullningen av Microsoft 365 för företag hade Contoso Windows-kompatibla datorer och enheter som körde en blandning av Windows 7 (10 %) Windows 8,1 (65 %) och Windows 10 (25 %). Contoso ville uppgradera datorerna för Windows 10 Enterprise för att dra nytta av avancerad säkerhet och lägre IT-kostnader jämfört med automatiska distributioner av uppdateringar. 

Efter att ha uppskattat deras infrastruktur- och företagsbehov identifierade Contoso de viktigaste kraven för distributionen:

- Så många datorer och enheter som möjligt skulle köra Windows 10 Enterprise
- Lanseringen av på plats-uppgraderingar utnyttjar befintlig Configuration Manager-infrastruktur
- Styr vilka versioner av Windows 10 Enterprise som ska distribueras och vilka uppdateringar som görs via ringar
- Datorerna och enheterna ska vara uppdaterade med minimala IT-administrativa kostnader och minsta möjliga påverkan på slutanvändarna

Uppdaterat definieras som den version av Windows 10 Enterprise som stöds och som uppfyller organisationens affärsbehov, och det kan skilja sig från att ha alla Windows-kompatibla datorer med den senaste versionen av Windows 10 Enterprise.

## <a name="deployment-tools"></a>Distributionsverktyg

Före och under på plats-uppgraderingar av Windows 10 Enterprise använde Contoso följande lösningar i Windows Analytics:

- Uppgraderingsberedskap  

  Samlar in system-, program- och drivrutinsdata för analys och identifierar kompatibilitetsproblem som kan blockera en uppgradering och förslag på problem som är kända för Microsoft.

- Uppdateringsefterlevnad  

  Visar status för dina enheter med hänsyn till Windows-uppdateringarna, så att du kan se till att de är uppdaterade med de senaste uppdateringarna.

- Enhetshälsotillstånd  

  Identifierar enheter som kraschar ofta och därför kan behöva återskapas eller ersättas samt drivrutiner som orsakar att enheten kraschar, med förslag på alternativa versioner av drivrutiner som kan minska antalet krascher. Skickar meddelanden om informativa Windows-felkonfigurationer som skickar uppmaningar till slutanvändare.
 
Contoso har en befintlig infrastruktur för Configuration Manager (Current Branch). Configuration Manager kan skalas för stora miljöer och tillhandahåller omfattande kontroll över installation, uppdateringar och inställningar. Den har också inbyggda funktioner som gör det enklare och mer effektivt att distribuera och hantera Windows 10 Enterprise.

## <a name="planning-process"></a>Planeringsprocessen

Contoso använde Upgrade Readiness i Windows Analytics för att fastställa vilka installerade appar och deras kompatibilitet med Windows 10 Enterprise.

## <a name="deployment-process"></a>Distributionsprocess

För att slutföra distributionen av på plats-uppgradering av Windows 10 Enterprise genomför Contoso följande process, som innehåller rekommendationer från Microsoft:

1. Aktiverad peer-cachelagring för Configuration Manager.
2. Anpassade Windows-paket som skapats utifrån avbildningarna från Volume Licensing Service Center.
3. Används Konfigurationshanteraren för att distribuera Windows paket till distributionspunkter i deras nätverk och distribuerade byggen till de tre mellanlagringsgrupperna för validering och distribution.
4. Genomförde bedömning av framgång för datorer och enheter i de tre ringarna för mellanlagring av verifiering och distribution med hjälp av enhetshälsotillstånd och lösningar för uppdateringsefterlevnad för Windows Analytics.
5. Utifrån informationen i Windows bestämde Contoso vilken version av Windows 10 Enterprise distribuerade till den breda distributionsgruppen.
6. Körde distributionssekvenser för Konfigurationshanteraren för att distribuera det Windows paket till den breda distributionsgruppen.
7. Övervakade datorer och enheter i den omfattande distributionsgruppen med lösningar för enhetshälsa och uppdatering av efterlevnad för att lösa problem.

Det här är Contosos på plats-uppgradering och pågående uppdateringars distributionsarkitektur.

![Contosos distributrionsinfrastruktur för Windows 10 Enterprise](../media/contoso-win10/contoso-win10-fig1.png)

Infrastrukturen består av:

- Configuration Manager, som:
  - Hämtar avbildningar av Windows 10 Enterprise-paket från Microsoft Volume Licensing Center i Microsoft-nätverket.
  - Är den centrala administrationsplatsen för distributionspaket.
- Regionala distributionsplatser som vanligtvis finns i Contosos regionala navkontor.
- Windows Datorer och enheter på olika platser som tar emot och installerar distributionspaketen för den på plats-uppgraderingen eller pågående uppdateringar baserat på gruppmedlemskap.

## <a name="next-step"></a>Nästa steg

Lär dig hur Contoso utnyttjar sin infrastruktur i Configuration Manager för [att distribuera och hålla Microsoft 365-appar för företag](contoso-o365pp.md) i organisationen. 

## <a name="see-also"></a>Se även

[Windows 10 Enterprise](/windows/deployment/)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Testlabbguider](m365-enterprise-test-lab-guides.md)