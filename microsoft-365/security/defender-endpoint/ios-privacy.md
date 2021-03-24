---
title: Information om sekretess – Microsoft Defender för Slutpunkt för iOS
ms.reviewer: ''
description: Beskriver sekretessinformation för Microsoft Defender för Endpoint för iOS
keywords: microsoft, defender, atp, ios, princip, översikt
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52694322c7f084df777a8e97fe5b84cc3cb4e6d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072306"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>Information om sekretess – Microsoft Defender för Slutpunkt för iOS

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender för Endpoint för iOS använder en VPN för att tillhandahålla webskyddsfunktionen. Det här är inte en vanlig VPN och är en lokal eller självslingande VPN som inte tar trafik utanför enheten. **Microsoft eller din organisation ser inte din webbaktivitet.**

Defender för Slutpunkt för iOS samlar in information från dina konfigurerade iOS-enheter och lagrar den i samma klientorganisation där du har Defender för Slutpunkt. Informationen samlas in för att hålla Defender för Endpoint för iOS säker, uppdaterad och fungerar som förväntat, och för att stödja tjänsten.

Mer information om datalagring finns i [Microsoft Defender för Slutpunktens datalagring och sekretess.](data-storage-privacy.md)

## <a name="required-data"></a>Data som krävs 

Obligatoriska data består av data som krävs för att Defender för Endpoint för iOS ska fungera som förväntat. Dessa data är viktiga för att tjänsten ska kunna användas och kan innehålla data relaterade till slutanvändare, organisation, enhet och appar. 

Här är en lista över de typer av data som samlas in: 

### <a name="web-page-or-network-information"></a>Webbsida eller nätverksinformation 

- Domännamnet på webbplatsen endast när en skadlig anslutning eller webbsida identifieras. 

### <a name="device-and-account-information"></a>Enhet och kontoinformation 

- Enhetsinformation som datum & tid, iOS-version, CPU-information och enhetsidentifierare, där Enhetsidentifierare är något av följande: 

    - Wi-Fi mac-adapteradress 

    - Slumpmässigt genererad globalt unik identifierare (GUID) 

- Information om klientorganisation, enhet och användare 

    - Enhets-ID (AD) för Azure Active Directory och Azure Användar-ID – Identifierar enheten, respektive användaren vid Azure Active Directory. 

    - Azure-klientorganisations-ID – GUID som identifierar organisationen i Azure Active Directory. 

    - Microsoft Defender för slutpunktens organisations-ID – Unikt ID som associeras med företaget som enheten tillhör. Gör att Microsoft kan identifiera om det finns problem som påverkar en uppsättning utvalda företag och antalet företag som påverkas. 

    - User Principal Name – Användarens e-post-ID. 

### <a name="product-and-service-usage-data"></a>Användningsdata för produkter och tjänster 

Följande information samlas endast in för appen Microsoft Defender för slutpunkt som är installerad på enheten. 

- Information om programpaket, inklusive namn, version och appuppgraderingsstatus. 

- Åtgärder som utförts i appen. 

- Kraschrapportloggar som genererats av iOS. 

- Minnesanvändningsdata. 

## <a name="optional-data"></a>Valfria data 

Valfria data omfattar diagnostikdata och feedbackdata från klienten. Valfria diagnostikdata är ytterligare data som ligger till grund för produktförbättringar och ger förbättrad information som hjälper oss att upptäcka, diagnostisera och åtgärda problem. Dessa data är endast avsedda för diagnostiska syften och krävs inte för själva tjänsten. 

Valfria diagnostikdata omfattar: 

- App-, CPU- och nätverksanvändning för Defender för Slutpunkt. 

- Funktioner som konfigurerats av administratören för Defender för Endpoint. 

Feedbackdata samlas in via feedback som ges av användaren i appen. 

- Användarens e-postadress, om han eller hon väljer att ange den.

- Feedbacktyp (leende, bägare, idé) och eventuella feedbackkommentarer som skickats in av användaren. 

Mer information finns i [Mer om sekretess](https://aka.ms/mdatpiosprivacystatement).


