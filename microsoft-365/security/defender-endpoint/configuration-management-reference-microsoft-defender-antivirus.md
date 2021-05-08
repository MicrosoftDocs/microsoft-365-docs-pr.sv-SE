---
title: Hantera Windows Defender i företaget
description: Lär dig hur du använder grupprinciper, konfigurationshanteraren, PowerShell, WMI, Intune och kommandoraden för att hantera Microsoft Defender AV
keywords: grupprincip, gpo, config manager, sccm, sshell, powershell, wmi, intune, defender, antivirus, antimalware, säkerhet, skydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274982"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Hantera Microsoft Defender Antivirus i företaget

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan hantera och Microsoft Defender Antivirus med följande verktyg:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ingår nu i Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ingår nu i Microsoft Endpoint Manager)
- [Grupprincip](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell-cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Kommandoradsverktyget Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (kallas även verktyget *mpcmdrun.exe* Protection)

Följande artiklar innehåller ytterligare information, länkar och resurser för att använda dessa verktyg för att hantera och Microsoft Defender Antivirus.

| Artikel | Beskrivning |
|:---|:---|
|[Hantera Microsoft Defender Antivirus med Microsoft Intune och Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Information om hur du använder Intune och Configuration Manager för att distribuera, hantera, rapportera och Microsoft Defender Antivirus |
|[Hantera Microsoft Defender Antivirus med grupprincipinställningar](use-group-policy-microsoft-defender-antivirus.md)|Lista över alla grupprincipinställningar i ADMX-mallar |
|[Hantera Microsoft Defender Antivirus med PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instruktioner för hur du använder PowerShell-cmdlets för Microsoft Defender Antivirus, samt länkar till dokumentation för alla cmdlets och tillåtna parametrar |
|[Hantera Microsoft Defender Antivirus med Windows Management Instrumentation (WMI)](use-wmi-microsoft-defender-antivirus.md)| Instruktioner för hur du använder WMI för Microsoft Defender Antivirus och länkar till dokumentation för WMIv2-API:er (inklusive alla klasser, metoder och egenskaper) |
|[Hantera Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget](command-line-arguments-microsoft-defender-antivirus.md)|Instruktioner om hur du använder det dedikerade kommandoradsverktyget för att hantera och använda Microsoft Defender Antivirus |