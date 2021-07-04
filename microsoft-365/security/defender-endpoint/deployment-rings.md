---
title: Distribuera Microsoft Defender för slutpunkt i ringar
description: Lär dig hur du distribuerar Microsoft Defender för slutpunkt i ringar
keywords: distribuera, ringar, utvärdera, pilottesta, insider snabbt, insider – långsamt, konfiguration, onboard, phase, deployment, deploying, adoption, configuring
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fffbbb519f9c31b5343e665958bcb47436a2d50
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289349"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Distribuera Microsoft Defender för slutpunkt i ringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Distribution av Microsoft Defender för Endpoint kan göras med en ringbaserad distributionsmetod. 

Distributionsringarna kan användas i följande scenarier:
- [Nya distributioner](#new-deployments)
- [Befintliga distributioner](#existing-deployments)

## <a name="new-deployments"></a>Nya distributioner

![Bild på distributionsringar](images/deployment-rings.png)


En ringbaserad metod är en metod för att identifiera en uppsättning slutpunkter för att registrera och verifiera att vissa villkor uppfylls innan du fortsätter att distribuera tjänsten till en större uppsättning enheter. Du kan definiera utgångsvillkor för varje ring och säkerställa att de är nöjda innan du går vidare till nästa ring.

Genom att införa en ringbaserad distribution minskar du eventuella problem som kan uppstå när tjänsten distribueras. Genom att pilottesta ett visst antal enheter först kan du identifiera potentiella problem och minimera potentiella risker som kan uppstå. 

Tabell 1 innehåller ett exempel på de distributionsringar som du kan använda.

**Tabell 1**

|Distributionsringen|Beskrivning
|---|---|
Utvärdera | Ring 1: Identifiera 50 system för pilottestning
Pilot | Ring 2: Identifiera de nästa 50–100 slutpunkterna i produktionsmiljön
Fullständig distribution | Ring 3: Distribuera tjänsten till resten av miljön stegvis.

### <a name="exit-criteria"></a>Avsluta villkor

Ett exempel på utgångsvillkor för dessa ringar kan vara:

- Enheter visas i enhetsinventeringslistan
- Aviseringar visas i instrumentpanelen
- [Köra ett identifieringstest](run-detection-test.md)
- [Köra en simulerad attack på en enhet](attack-simulations.md)

### <a name="evaluate"></a>Utvärdera

Identifiera ett litet antal testdatorer i din miljö som kan komma igång med tjänsten. Helst bör dessa datorer ha färre än 50 slutpunkter.

### <a name="pilot"></a>Pilot

Microsoft Defender för Endpoint har stöd för ett antal olika slutpunkter som du kan introducera till tjänsten. I den här ringen identifierar du flera enheter som kan introduceras och utifrån de utgångsvillkor som du anger, bestämmer dig för att gå vidare till nästa distributionsring.

I följande tabell visas de slutpunkter som stöds och motsvarande verktyg som du kan använda för att registrera enheter i tjänsten. 

| Slutpunkt     | Distributionsverktyget                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokalt skript (upp till 10 enheter)](configure-endpoints-script.md) <br> Obs! Om du vill distribuera fler än 10 enheter i en produktionsmiljö använder du grupprincipmetoden i stället eller andra verktyg som stöds nedan.<br>  [Grupprincip](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-skript](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokalt skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF-Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokalt skript](linux-install-manually.md) <br> [En- och en-](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Appbaserade](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               |

### <a name="full-deployment"></a>Fullständig distribution

I det här läget kan du använda planera [distributionsmaterial](deployment-strategy.md) för att planera distributionen. 

Använd följande material för att välja lämplig Microsoft Defender för Slutpunktsarkitektur som bäst passar din organisation.

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Thumb-bild för Microsoft Defender för distributionsstrategi för slutpunkt](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Med hjälp av arkitekturmaterialet kan du planera din distribution för följande arkitekturer: <ul><li> Molnbaserad </li><li> Samhantering </li><li> Lokal</li><li>Utvärdering och lokal registrering</li></ul>

## <a name="existing-deployments"></a>Befintliga distributioner

### <a name="windows-endpoints"></a>Windows slutpunkter

För Windows-servrar och/eller Windows-servrar väljer du flera datorer för att testa i förväg (före korrigeringen tisdag) med hjälp av programmet FÖR **säkerhetsuppdateringsverifiering (SÅD).**

Mer information finns i:

- [Vad är verifieringsprogrammet för säkerhetsuppdateringar?](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Valideringsprogram för program för programuppdatering och Microsoft Malware Protection Center upp - TwC Interaktiv tidslinje del 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>Slutpunkter som Windows inte är slutpunkter

Med macOS och Linux kan du köra ett par system i Beta-kanalen.

> [!NOTE]
> Under idealiska som helst minst en säkerhetsadministratör och en utvecklare så att du kan hitta kompatibilitets-, prestanda- och tillförlitlighetsproblem innan versionen tar den till aktuell kanal.

Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet. Enheter i betaversion är de första som får uppdateringar och nya funktioner, följt senare av Förhandsversion och slutligen av Aktuell.

![Bild på insiderringar](images/insider-rings.png)

Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget för användning med antingen betaversion eller förhandsversion.

> [!WARNING]
> Om du byter kanal efter den första installationen måste produkten installeras om. Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.
