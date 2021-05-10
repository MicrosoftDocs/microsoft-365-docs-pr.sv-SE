---
title: Aktivera att definitionen inaktiveras för Microsoft Defender Antivirus
description: Aktivera att definitionen inaktiveras för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, definition som finns i retirement
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296496"
---
# <a name="turn-on-definition-retirement"></a>Aktivera att definitionen inaktiveras

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan konfigurera att en definition ska sluta användas med grupprinciper. Definition som inte längre behövs kontrollerar om en dator har de säkerhetsuppdateringar som krävs för att skydda den mot ett visst säkerhetshål. Om systemet inte är sårbart för sårbarheten som identifieras av en definition kommer den definitionen att "dras tillbaka". Om all säkerhetsinformation för ett visst protokoll dras tillbaka analyseras inte det protokollet längre. Om du aktiverar den här funktionen kan du förbättra prestandan. Nätverksskydd påverkar inte nätverksprestandan på datorer som är uppdaterade med de senaste säkerhetsuppdateringarna.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Använda grupprincip för att ta ut en definition

1. Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Gå till **Administrativa mallar för**  >  **datorkonfiguration** Windows  >  **komponenter**  >  **Microsoft Defender Antivirus** System  >  **för nätverksinspektion.** 

3. Välj **Aktivera att definitionen inaktiveras**. Den här principen är aktiverad som standard. Om denna **anges som Ej konfigurerad** kommer den att vara aktiverad. 

4. Om du vill redigera principen väljer du **länken Redigera principinställning.**

5. Välj **Aktiverad** och välj sedan **OK.**

6. Distribuera det uppdaterade grupprincipobjektet. Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Använder du grupprincipobjekt lokalt? Se hur de översätter i molnet. [Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)