---
title: Konfigurera funktioner för minskning av attackytan
description: Använd Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets och grupprincip för att konfigurera minskning av attackytan.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984454"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Konfigurera funktioner för minskning av attackytan

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).

Defender för Slutpunkt innehåller flera funktioner för att minska attackytan. Mer information finns i [Översikt över minskningsfunktioner för attackytor.](overview-attack-surface-reduction.md) Konfigurera minskning av attackytan i din miljö genom att följa de här stegen:

1. [Aktivera maskinvarubaserad avgränsning för Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. Aktivera programkontroll.

   1. Granska basprinciper i Windows. Se [Exempel på basprinciper.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)
   2. Se Windows Defender [för designguiden för Programkontroll.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. Mer information [finns i Windows Defender programkontrollprinciper (WDAC).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [Aktivera reglerad mappåtkomst.](enable-controlled-folders.md)

4. [Aktivera nätverksskydd](enable-network-protection.md).

5. [Aktivera sårbarhetsskydd.](enable-exploit-protection.md)

6. [Konfigurera regler för att minska attackytan](enable-attack-surface-reduction.md).

7. Konfigurera nätverkets brandvägg.

   1. Få en översikt över [Windows Defender med avancerad säkerhet.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Använd guiden [Windows Defender för att](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) bestämma hur du vill utforma brandväggsprinciperna.
   3. Använd Windows Defender [för brandväggsdistribution](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) för att konfigurera din organisations brandvägg med avancerad säkerhet.

> [!TIP]
> När du konfigurerar funktioner för att minska attackytan kan du i de flesta fall välja mellan flera metoder:

> - Microsoft Endpoint Manager (som nu innehåller Microsoft Intune och Microsoft Endpoint Configuration Manager)
> - Grupprincip
> - PowerShell-cmdlets
