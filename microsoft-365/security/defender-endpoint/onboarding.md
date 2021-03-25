---
title: Introduktion till Microsoft Defender ATP-tjänsten
description: Lär dig hur du onboardar slutpunkter till Microsoft Defender ATP-tjänsten
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186935"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Onboard to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Läs mer om de olika faserna i distributionen av Microsoft Defender för Endpoint och hur du konfigurerar funktionerna i lösningen. 

Distribution av Defender för Endpoint är en process i tre steg:

| [![distributionsfas – förbereda](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fas 1: Förbereda](prepare-deployment.md) | [![distributionsfas – konfiguration](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fas 2: Konfigurera](production-deployment.md) | ![distributionsfas – onboard](images/phase-diagrams/onboard.png)<br>Fas 3: Introduktion |
| ----- | ----- | ----- |
| | |*Du är här!*|

Du befinner dig för närvarande i introduktionsfasen.

Det här är de steg du måste vidta för att distribuera Defender för Slutpunkt:

- Steg 1: Introducera slutpunkter till tjänsten 
- Steg 2: Konfigurera funktioner 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Steg 1: Hantera slutpunkter som använder något av de hanteringsverktyg som stöds
I [avsnittet Planera](deployment-strategy.md) distribution beskrivs de allmänna åtgärder du behöver vidta för att distribuera Defender för Slutpunkt.  


Titta på den här videon för en snabb överblick över registreringsprocessen och lär dig mer om tillgängliga verktyg och metoder.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



När du har identifierat arkitekturen måste du bestämma vilken distributionsmetod du ska använda. Distributionsverktyget du väljer påverkar hur du onboardar slutpunkter till tjänsten. 

### <a name="onboarding-tool-options"></a>Alternativ för introduktionsverktyg

I följande tabell visas de tillgängliga verktygen baserat på slutpunkten som du behöver registrera.

| Slutpunkt     | Verktygsalternativ                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokalt skript (upp till 10 enheter)](configure-endpoints-script.md) <br>  [Grupprincip](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-skript](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokala skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokalt skript](linux-install-manually.md) <br> [En- och en-](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Appbaserade](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Steg 2: Konfigurera funktioner
Efter att slutpunkterna introduceras konfigurerar du de olika funktionerna, till exempel identifiering och svar av slutpunkter, nästa generations skydd och minskning av attackytan. 


## <a name="example-deployments"></a>Exempeldistributioner
I den här distributionsguiden vägleder vi dig genom att använda två distributionsverktyg för att introducera slutpunkter och konfigurera funktioner.

Verktygen i exempeldistributionerna är:
- [Introduktion med Konfigurationshanteraren för Microsoft Endpoint](onboarding-endpoint-configuration-manager.md)
- [Introduktion med Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Med hjälp av de omnämnda distributionsverktygen ovan vägleds du när du konfigurerar följande Defender för Slutpunkt-funktioner:
- Konfiguration av slutpunktsidentifiering och -svar
- Konfiguration av nästa generations skydd
- Konfiguration för att minska attackytan

## <a name="related-topics"></a>Relaterade ämnen
- [Introduktion med Konfigurationshanteraren för Microsoft Endpoint](onboarding-endpoint-configuration-manager.md)
- [Introduktion med Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
