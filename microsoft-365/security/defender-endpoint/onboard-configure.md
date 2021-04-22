---
title: Introducera enheter till Microsoft Defender för slutpunktstjänsten
description: Introducera Windows 10-enheter, servrar, icke-Windows-enheter och lär dig hur du kör ett identifieringstest.
keywords: onboarding, Microsoft Defender för slutpunkts onboarding, sccm, grupprincip, mdm, lokalt skript, identifieringstest
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933559"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Introducera enheter till Microsoft Defender för slutpunktstjänsten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Du måste gå till introduktionsavsnittet i Defender för Endpoint-portalen för att registrera någon av de enheter som stöds. Beroende på enhet vägleds du med lämpliga steg och lämpliga alternativ för hantering och distributionsverktyg för enheten. 

I allmänhet kan du registrera enheter i tjänsten:

- Kontrollera att enheten uppfyller [minimikraven](minimum-requirements.md)
- Beroende på enhet följer du konfigurationsstegen i introduktionsavsnittet för Defender för slutpunktsportalen
- Använd rätt hanteringsverktyg och distributionsmetod för dina enheter
- Kör ett identifieringstest för att verifiera att enheterna är korrekt onboarded och rapporterar till tjänsten

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Alternativ för introduktionsverktyg
I följande tabell visas de tillgängliga verktygen baserat på slutpunkten som du behöver registrera.

| Slutpunkt     | Verktygsalternativ                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokalt skript (upp till 10 enheter)](configure-endpoints-script.md) <br>  [Grupprincip](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-skript](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokala skript](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokalt skript](linux-install-manually.md) <br> [En- och en-](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Appbaserade](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>I det här avsnittet
Ämne | Beskrivning
:---|:---
[Registrera tidigare versioner av Windows](onboard-downlevel.md)| Introducera Windows 7- och Windows 8.1-enheter i Defender för Slutpunkt. 
[Registrera Windows 10-enheter](configure-endpoints.md) | Du måste registrera enheter för att rapporten ska kunna rapportera till Defender för slutpunktstjänsten. Läs mer om verktyg och metoder som du kan använda för att konfigurera enheter i företaget.
[Onboard servers](configure-server-endpoints.md) |  Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SACK) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.
[Registrera icke-Windows-enheter](configure-endpoints-non-windows.md) | Defender för Endpoint ger en centraliserad säkerhetsoperationer för Windows och för icke-Windows-plattformar. Du kan se aviseringar från olika operativsystem som stöds (OS) i Microsoft Defender Säkerhetscenter och bättre skydda organisationens nätverk. Den här upplevelsen utnyttjar sensordata från tredje part. 
[Kör ett identifieringstest på en nyligen registrerad enhet](run-detection-test.md) | Kör ett skript på en nyligen onboarded-enhet för att verifiera att den rapporterar korrekt till Defender för slutpunkt-tjänsten.
[Konfigurera proxy- och Internetinställningar](configure-proxy-internet.md)| Aktivera kommunikation med Defender för slutpunktsmolntjänsten genom att konfigurera proxy- och Internetanslutningsinställningarna.
[Felsöka registreringsproblem](troubleshoot-onboarding.md) | Läs mer om hur du löser problem som kan uppstå under registrering.

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
