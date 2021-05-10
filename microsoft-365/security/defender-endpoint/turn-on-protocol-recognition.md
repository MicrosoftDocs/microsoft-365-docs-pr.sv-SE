---
title: Aktivera protokolligenkänning för Microsoft Defender Antivirus
description: Aktivera protokolligenkänning för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, protokolligenkänning
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296495"
---
# <a name="turn-on-protocol-recognition"></a>Aktivera protokolligenkänning 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Med den här principinställningen kan du konfigurera protokolligenkänning för nätverksskydd mot sårbarheter av kända säkerhetsproblem. Om du aktiverar eller inte konfigurerar den här inställningen aktiveras protokolligenkänning. Om du inaktiverar den här inställningen inaktiveras protokolligenkänningen.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Använda grupprinciper för att konfigurera protokolligenkänning

1. Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Gå till **Administrativa mallar för**  >  **datorkonfiguration** Windows  >  **komponenter**  >  **Microsoft Defender Antivirus** System  >  **för nätverksinspektion.** 

3. Välj **protokolligenkänning**. Den här principen är aktiverad som standard. Om denna **anges som Ej konfigurerad** kommer den att vara aktiverad. 

4. Om du vill redigera principen väljer du **länken Redigera principinställning.**

5. Välj **Aktiverad** och välj sedan **OK.**

6. Distribuera det uppdaterade grupprincipobjektet. Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Använder du grupprincipobjekt lokalt? Se hur de översätter i molnet. [Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)