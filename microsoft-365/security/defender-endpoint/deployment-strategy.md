---
title: Planera distribution av Microsoft Defender för Slutpunkt
description: Välj den bästa distributionsstrategin för Microsoft Defender för slutpunkten för din miljö
keywords: distribuera, planera, distributionsstrategi, inbyggd molntjänst, hantering, lokal, utvärdering, onboarding, lokal, grupprincip, gp, slutpunktsansvarig, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163581"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Planera distribution av Microsoft Defender för Slutpunkt 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


Planera distributionen av Microsoft Defender för slutpunkt så att du kan maximera säkerhetsfunktionerna i paketet och bättre skydda ditt företag mot cyberhot.


Den här lösningen innehåller vägledning om hur du identifierar din miljöarkitektur, väljer den typ av distributionsverktyg som bäst passar dina behov och vägledning om hur du konfigurerar funktioner.


![Bild av distributionsflöde](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>Steg 1: Identifiera arkitektur
Vi förstår att alla företagsmiljöer är unika, så vi har tillhandahållit flera alternativ för att ge dig flexibiliteten att välja hur tjänsten ska distribueras.

Beroende på din miljö passar vissa verktyg bättre för vissa arkitekturer. 

Använd följande material för att välja lämplig Defender för Endpoint-arkitektur som bäst passar din organisation.

| Objekt | Beskrivning |
|:-----|:-----|
|[![Thumb-bild för Defender för slutpunktsdistributionsstrategi](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Med hjälp av arkitekturmaterialet kan du planera din distribution för följande arkitekturer: <ul><li> Molnbaserad </li><li> Samhantering </li><li> Lokal</li><li>Utvärdering och lokal registrering</li>



## <a name="step-2-select-deployment-method"></a>Steg 2: Välj distributionsmetod
Defender för Endpoint har stöd för ett antal olika slutpunkter som du kan introducera till tjänsten. 

I följande tabell visas de slutpunkter som stöds och motsvarande distributionsverktyg som du kan använda så att du kan planera distributionen på rätt sätt.

| Slutpunkt     | Distributionsverktyget                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokalt skript (upp till 10 enheter)](configure-endpoints-script.md) <br>  [Grupprincip](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-skript](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokalt skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokalt skript](linux-install-manually.md) <br> [En- och en-](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Appbaserade](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>Steg 3: Konfigurera funktioner
Efter slutpunkter för onboarding konfigurerar du säkerhetsfunktionerna i Defender för Endpoint så att du kan maximera det robusta säkerhetsskydd som finns tillgängligt i programsviten. Funktionerna omfattar:

- Identifiering och svar av slutpunkter
- Nästa generations skydd
- Minskning av attackytan


  
## <a name="related-topics"></a>Relaterade ämnen
- [Distributionsfaser](deployment-phases.md)
