---
title: Hantera Windows Defender i ditt företag
description: Lär dig hur du använder grupprinciper, konfigurationshanteraren, PowerShell, WMI, Intune och kommandoraden för att hantera Microsoft Defender AV
keywords: grupprincip, gpo, config manager, sccm, sshell, powershell, wmi, intune, defender, antivirus, antimalware, säkerhet, skydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764873"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Hantera Microsoft Defender Antivirus i ditt företag

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan hantera och konfigurera Microsoft Defender Antivirus med följande verktyg:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ingår nu i Microsoft Endpoint Manager)
- [Konfigurationshanteraren för Microsoft Endpoint](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ingår nu i Microsoft Endpoint Manager)
- [Grupprincip](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell-cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Kommandoradsverktyget Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (kallas även verktyget *mpcmdrun.exe* Protection)

Följande artiklar innehåller ytterligare information, länkar och resurser för att använda dessa verktyg för att hantera och konfigurera Microsoft Defender Antivirus.

| Artikel | Beskrivning |
|:---|:---|
|[Hantera Microsoft Defender Antivirus med Microsoft Intune och Konfigurationshanteraren för Microsoft Endpoint](use-intune-config-manager-microsoft-defender-antivirus.md)|Information om hur du använder Intune och Konfigurationshanteraren för att distribuera, hantera, rapportera och konfigurera Microsoft Defender Antivirus |
|[Hantera Microsoft Defender Antivirus med grupprincipinställningar](use-group-policy-microsoft-defender-antivirus.md)|Lista över alla grupprincipinställningar i ADMX-mallar |
|[Hantera Microsoft Defender Antivirus med PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instruktioner för hur du använder PowerShell-cmdlets för att hantera Microsoft Defender Antivirus samt länkar till dokumentation för alla cmdlets och tillåtna parametrar |
|[Hantera Microsoft Defender Antivirus med Windows Management Instrumentation (WMI)](use-wmi-microsoft-defender-antivirus.md)| Instruktioner för hur du använder WMI för att hantera Microsoft Defender Antivirus samt länkar till dokumentation för WMIv2-API:er (inklusive alla klasser, metoder och egenskaper) |
|[Hantera Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget](command-line-arguments-microsoft-defender-antivirus.md)|Instruktioner om hur du använder det dedikerade kommandoradsverktyget för att hantera och använda Microsoft Defender Antivirus |