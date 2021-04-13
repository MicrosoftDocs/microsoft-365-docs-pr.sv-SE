---
title: Microsoft Defender ATP för Android – information om sekretess
description: Sekretesskontroller, hur du konfigurerar principinställningar som påverkar sekretess och information om diagnostikdata som samlas in i Microsoft Defender ATP för Android.
keywords: microsoft, defender, atp, android, sekretess, diagnostik
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
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687967"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender för slutpunkt på Android – information om sekretess

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Defender för slutpunkt för Android samlar in information från dina konfigurerade Android-enheter och lagrar den i samma klientorganisation där du har Defender för Slutpunkt.

Information samlas in för att hålla Defender för Endpoint för Android säkert och uppdaterat så att det fungerar som förväntat och för att stödja tjänsten.

## <a name="required-data"></a>Data som krävs 

Data som krävs består av data som krävs för att Defender för Slutpunkt för Android ska fungera som förväntat. Dessa data är viktiga för att tjänsten ska kunna användas och kan innehålla data relaterade till slutanvändare, organisation, enhet och appar. Här är en lista över de typer av data som samlas in:

### <a name="app-information"></a>Appinformation

Information om Android-programpaket (APKs) på enheten, inklusive

-  Installera källa
-  Lagringsplats (sökväg) för APK
-  Tid för installation, storlek på APK och behörigheter

### <a name="web-page--network-information"></a>Webbsida/nätverksinformation

- Fullständig URL (på webbläsare som stöds), vid klickning
- Anslutningsinformation
- Protokolltyp (till exempel HTTP, HTTPS osv.)


### <a name="device-and-account-information"></a>Enhet och kontoinformation

- Enhetsinformation som datum & tid, Android-version, OEM-modell, CPU-information och enhetsidentifierare
- Enhetsidentifierare är något av följande:
    - Wi-Fi mac-adapteradress
    - [Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (som genereras av Android vid första starten av enheten)
    - Slumpmässigt genererad globalt unik identifierare (GUID)

- Information om klientorganisation, enhet och användare
    -   Enhets-ID för Azure Active Directory (AD) och Azure Användar-ID: Identifierar enheten, respektive användaren vid Azure Active Directory.

    -   Azure-klientorganisations-ID – GUID som identifierar organisationen i Azure Active Directory

    -   Organisations-ID för Microsoft Defender ATP – Unikt ID associerat med företaget som enheten tillhör. Gör att Microsoft kan identifiera huruvida problem påverkar en uppsättning utvalda företag och hur många företag som påverkas 

    -   User Principal Name – Användarens e-post-ID

### <a name="product-and-service-usage-data"></a>Användningsdata för produkter och tjänster
-   Information om programpaket, inklusive namn, version och appuppgraderingsstatus

-   Åtgärder som utförs i appen

-   Information om identifiering av hot, till exempel namn på hot, kategori osv.

-   Kraschrapportloggar som genererats av Android

## <a name="optional-data"></a>Valfria data

Valfria data omfattar diagnostikdata och feedbackdata. Valfria diagnostikdata är ytterligare data som ligger till grund för produktförbättringar och ger förbättrad information som hjälper oss att upptäcka, diagnostisera och åtgärda problem. Valfria diagnostikdata omfattar:

-   App-, CPU- och nätverksanvändning

-   Status för enheten ur appperspektiv, inklusive genomsökningsstatus, tidsinställningar för skanning, beviljad appbehörighet och uppgraderingsstatus

-   Funktioner som konfigurerats av administratören

-   Grundläggande information om webbläsare på enheten

**Feedbackdata** samlas in via feedback som ges av användaren i appen

-   Användarens e-postadress, om han eller hon väljer att ange den

-   Feedbacktyp (leende, bägare, idé) och eventuella feedbackkommentarer som skickats in av användaren
