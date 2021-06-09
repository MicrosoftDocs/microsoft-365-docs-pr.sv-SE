---
title: Övervaka och rapportera Microsoft Defender Antivirus skydd
description: Använd Konfigurationshanteraren eller säkerhetsinformation och händelsehanteringsverktyg (SIEM) för att använda rapporter och övervaka Microsoft Defender AV med PowerShell och WMI.
keywords: siem, bildskärm, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269594"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Rapport om Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ingår i Windows 10, Windows Server 2019 och Windows Server 2016. Microsoft Defender Antivirus är ditt nästa generations skydd i Microsoft Defender för Endpoint. Nästa generations skydd skyddar dina enheter mot programvaruhot som virus, skadlig programvara och spionprogram i e-post, appar, molnet och webben.

Med Microsoft Defender Antivirus finns det flera alternativ för att granska status och aviseringar för skydd. Du kan använda Microsoft Endpoint Manager att övervaka [Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) eller skapa [e-postaviseringar.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Eller så kan du övervaka skyddet med [hjälp av Microsoft Intune](/intune/introduction-intune).  

Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite har ett tillägg för uppdateringsefterlevnad som rapporterar Microsoft Defender Antivirus viktiga problem, bland annat skyddsuppdateringar och inställningar för realtidsskydd.

Om du har en säkerhetsinformations- och händelsehanteringsserver (SIEM) från tredje part kan du också använda [Windows Defender-klienthändelser.](/windows/win32/events/windows-events) 

Windows säkerhetshändelser omfattar flera säkerhetshändelsekällor, inklusive SAM-händelser (förbättrade för[Windows 10,](/windows/whats-new/whats-new-windows-10-version-1507-and-1511) [](/windows/device-security/auditing/security-auditing-overview) se även avsnittet Säkerhetsgranskning) [och Windows Defender händelser.](troubleshoot-microsoft-defender-antivirus.md) 

Dessa händelser kan aggregeras centralt med hjälp av Windows [händelseinsamlare.](/windows/win32/wec/windows-event-collector) Ofta har SIEM-servrar kopplingar för Windows-händelser, så att du korrelerar alla säkerhetshändelser i DIN SIEM-server. 

Du kan också [övervaka skadlig programvara med hjälp av Malware Assessment-lösningen i logganalys.](/azure/log-analytics/log-analytics-malware)

Information om hur du övervakar eller fastställer status för PowerShell, WMI eller Microsoft Azure finns i (tabellen med [distributions-,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)hanterings- och rapporteringsalternativ).

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus på Windows Server 2016 och 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)