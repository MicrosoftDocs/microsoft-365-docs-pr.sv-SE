---
title: Microsoft Defender ATP på Android
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender ATP för Android
keywords: microsoft, defender, atp, android, installation, distribuera, avinstallation, intune
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
ms.openlocfilehash: 8311cb703bc5232e1421d19892fec9cdbc94b052
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698202"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender för slutpunkt på Android

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

    -   Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet. Se [Licenskrav för Microsoft Defender för Slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Appen Intune Company Portal kan laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och är tillgänglig på Android-enheten.

        -   Dessutom kan enheter registreras via [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) appen Intune-företagsportal för att framtvinga Intune-enhetsefterlevnadsprinciper. Det kräver att användaren tilldelas en Microsoft Intune-licens.

    -   Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **För administratörer**

    -   Åtkomst till Microsoft Defender Säkerhetscenter-portalen.

        > [!NOTE]
        > Microsoft Intune är den enda MDM-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt på Android. För närvarande stöds endast registrerade enheter för tvingande Defender för Endpoint för Android-relaterade efterlevnadsprinciper för enheter i Intune. 

    -   Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera appen till registrerade användargrupper i organisationen.

### <a name="system-requirements"></a>Systemkrav

-   Android-enheter med Android 6.0 och högre.
-   Appen Intune Company Portal laddas ned från [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) och installeras. Enhetsregistrering krävs för att Intune-efterlevnadsprinciper för enheter ska tillämpas.

### <a name="installation-instructions"></a>Installationsanvisningar

Microsoft Defender för slutpunkt på Android har stöd för installation i båda lägen för registrerade enheter – äldre enhetsadministratörs- och Android Enterprise-lägen.
**För närvarande stöds personligt ägda enheter med arbetsprofil och företagsägd registrering av fullständigt hanterade användarenheter i Android Enterprise. Stöd för andra företagsläge i Android meddelas när du är klar.**

Distribution av Microsoft Defender för slutpunkt på Android sker via Microsoft Intune (MDM).
Mer information finns i Distribuera [Microsoft Defender för slutpunkt på Android med Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Microsoft Defender för slutpunkt på Android är tillgängligt på [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) nu.** <br> Du kan ansluta till Google Play från Intune för att distribuera Microsoft Defender för slutpunktsappen, över lägen för enhetsadministratör och Android Enterprise-registrering. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Konfigurera Microsoft Defender för slutpunkt på Android

Anvisningar om hur du konfigurerar Microsoft Defender för slutpunkt på Android-funktioner finns i [Konfigurera Microsoft Defender för slutpunkt på Android-funktioner.](android-configure.md)



## <a name="related-topics"></a>Relaterade ämnen
- [Distribuera Microsoft Defender för slutpunkt på Android med Microsoft Intune](android-intune.md)
- [Konfigurera Microsoft Defender för slutpunkt på Android-funktioner](android-configure.md)

