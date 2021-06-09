---
title: Registreringsverktyg och -metoder för Windows 10-enheter
description: Introducera Windows 10 enheter så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensor
keywords: Hantera Windows 10 enheter, grupprincip, slutpunktskonfigurationshanteraren, hantering av mobila enheter, lokalt skript, gp, sccm, mdm, intune
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892835"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Registreringsverktyg och -metoder för Windows 10-enheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 Insider-riskhantering](/microsoft-365/compliance/insider-risk-management)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Enheter i organisationen måste vara konfigurerade så att Defender för slutpunktstjänsten kan hämta sensordata från dem. Det finns olika metoder och distributionsverktyg som du kan använda för att konfigurera enheter i din organisation.

Följande distributionsverktyg och -metoder stöds:

- Grupprincip
- Microsoft Endpoint Configuration Manager
- Hantering av mobila enheter (inklusive Microsoft Intune)
- Lokalt skript

## <a name="in-this-section"></a>I det här avsnittet
Ämne | Beskrivning
:---|:---
[Introducera Windows 10 enheter med grupprincip](configure-endpoints-gp.md) | Använd Grupprincip för att distribuera konfigurationspaketet på enheter.
[Introducera Windows enheter med hjälp av Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Du kan använda antingen Microsoft Endpoint Manager (current branch) version 1606 eller Microsoft Endpoint Manager (current branch) version 1602 eller tidigare för att distribuera konfigurationspaket på enheter.
[Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](configure-endpoints-mdm.md) | Använd verktyg för hantering av mobila enheter eller Microsoft Intune till att distribuera konfigurationspaketet på enheten.
[Registrera Windows 10-enheter med ett lokalt skript](configure-endpoints-script.md) | Lär dig hur du använder det lokala skriptet för att distribuera konfigurationspaketet på slutpunkter.
[Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](configure-endpoints-vdi.md) | Lär dig hur du använder konfigurationspaketet för att konfigurera VDI-enheter.


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
