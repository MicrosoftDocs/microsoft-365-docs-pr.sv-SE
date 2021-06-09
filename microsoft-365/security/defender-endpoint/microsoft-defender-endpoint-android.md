---
title: Microsoft Defender för Endpoint för Android
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender för slutpunkt på Android
keywords: microsoft, defender, Microsoft Defender för slutpunkt, android, installation, distribuera, avinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 499ac9a6ee81bacb79cd83993d510f87e11c62c6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844724"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender för Endpoint för Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Defender för slutpunkt på Android.

> [!CAUTION]
> Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Defender för Slutpunkt på Android kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Så här installerar du Microsoft Defender för slutpunkt på Android

### <a name="prerequisites"></a>Förutsättningar

-   **För slutanvändare**

    -   Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet. Se [Licenskrav för Microsoft Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune-företagsportal-appen kan laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och finns på Android-enheten.

        -   Dessutom kan enheter registreras via appen [Intune-företagsportal](/mem/intune/user-help/enroll-device-android-company-portal) för att tillämpa Intune-enhetsefterlevnadsprinciper. Det kräver att användaren tilldelas en Microsoft Intune licens.

    -   Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **För administratörer**

    -   Åtkomst till Microsoft Defender Säkerhetscenter portalen.

        > [!NOTE]
        > Microsoft Intune är den enda MDM-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt på Android. För närvarande stöds endast registrerade enheter för tvingande Defender för Slutpunkt på Android-relaterade efterlevnadsprinciper för enheter i Intune. 

    -   Access [Microsoft Endpoint Manager administrationscenter](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.
        
### <a name="network-requirements"></a>Nätverkskrav

- För att Microsoft Defender för slutpunkt på Android ska fungera när du är ansluten till ett nätverk måste brandväggen/proxyn konfigureras för att aktivera åtkomst till URL:er för [Microsoft Defender för slutpunktstjänsten.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Systemkrav

-   Android-enheter med Android 6.0 och högre.
-   Intune-företagsportal laddas ned från [Google Play och](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) installeras. Enhetsregistrering krävs för att Intune-efterlevnadsprinciper för enheter ska tillämpas.

### <a name="installation-instructions"></a>Installationsanvisningar

Microsoft Defender för slutpunkt på Android har stöd för installation i båda lägen för registrerade enheter – äldre enhetsadministratörs- och Android Enterprise-lägen.
**För närvarande stöds personligt ägda enheter med arbetsprofil och företagsägd registrering av fullständigt hanterade användarenheter i Android Enterprise. Stöd för andra företagsläge i Android meddelas när du är klar.**

Distribution av Microsoft Defender för slutpunkt på Android sker via Microsoft Intune (MDM).
Mer information finns i Distribuera [Microsoft Defender för slutpunkt på Android med Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender för slutpunkt på Android är tillgängligt på [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) nu.** <br> Du kan ansluta till Google Play från Intune för att distribuera Microsoft Defender för slutpunktsappen, över lägen för enhetsadministratör och Android Enterprise-registrering. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Konfigurera Microsoft Defender för slutpunkt på Android

Anvisningar om hur du konfigurerar Microsoft Defender för slutpunkt på Android-funktioner finns i [Konfigurera Microsoft Defender för slutpunkt på Android-funktioner.](android-configure.md)



## <a name="related-topics"></a>Relaterade ämnen
- [Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune](android-intune.md)
- [Konfigurera Microsoft Defender för Endpoint för Android-funktioner](android-configure.md)

