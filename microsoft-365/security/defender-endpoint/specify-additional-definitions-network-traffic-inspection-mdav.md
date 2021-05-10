---
title: Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik för Microsoft Defender Antivirus
description: Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, kontroll av nätverkstrafik
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300261"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik med grupprincip.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Använda grupprincip till att ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik

1. Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Gå till **Windows Komponenter**  >  **Microsoft Defender Antivirus**  >  **System för nätverksinspektion.** 

3. Välj **Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik**. Som standard har den här principen inställningen **Ej konfigurerad.** 

4. Om du vill redigera principen väljer du **länken Redigera principinställning.**

5. Välj **Aktiverad** och välj sedan **Visa...** i **avsnittet Alternativ.**

6. Lägg till poster i listan och välj sedan **OK.** 

   Varje post måste anges som ett namnvärdepar, där namnet är en strängrepresentation av en definitionsuppsättning med GUID. Som exempel definieras definitionsuppsättningen GUID för att aktivera testsäkerhetsinformation som: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . Värdet används inte, så vi rekommenderar att du ställer in det på `0` . 

7. Välj **OK** och distribuera sedan det uppdaterade grupprincipobjektet. Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Använder du grupprincipobjekt lokalt? Se hur de översätter i molnet. [Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)