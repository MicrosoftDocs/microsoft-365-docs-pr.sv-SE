---
title: Övervaka och rapportera om Antivirusskyddet i Microsoft Defender
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
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="632cc-104">Rapport om Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="632cc-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="632cc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="632cc-105">**Applies to:**</span></span>

- [<span data-ttu-id="632cc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="632cc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="632cc-107">Microsoft Defender Antivirus är inbyggt i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="632cc-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="632cc-108">Microsoft Defender Antivirus är ditt nästa generations skydd i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="632cc-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="632cc-109">Nästa generations skydd skyddar dina enheter mot programvaruhot som virus, skadlig programvara och spionprogram i e-post, appar, molnet och webben.</span><span class="sxs-lookup"><span data-stu-id="632cc-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="632cc-110">Med Microsoft Defender Antivirus har du flera alternativ för att granska skyddsstatus och aviseringar.</span><span class="sxs-lookup"><span data-stu-id="632cc-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="632cc-111">Du kan använda Microsoft Endpoint Manager för att [övervaka Microsoft Defender Antivirus eller](/configmgr/protect/deploy-use/monitor-endpoint-protection) skapa [e-postaviseringar.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="632cc-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="632cc-112">Eller så kan du övervaka skyddet med [Microsoft Intune.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="632cc-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="632cc-113">Microsoft Operations Management Suite har ett [tillägg](/windows/deployment/update/update-compliance-get-started) för uppdateringsefterlevnad som rapporterar om viktiga problem med Microsoft Defender Antivirus, inklusive skyddsuppdateringar och inställningar för realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="632cc-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="632cc-114">Om du har en säkerhetsinformations- och händelsehanteringsserver (SIEM) från tredje part kan du också använda [Windows Defender-klienthändelser.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="632cc-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="632cc-115">Windows-händelser omfattar flera säkerhetshändelsekällor, inklusive HÄNDELSER i Säkerhetskontohanteraren (SAM) [](/windows/device-security/auditing/security-auditing-overview) ( förbättrade för[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), se även ämnet [Säkerhetsgranskning) och Windows Defender-händelser.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="632cc-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="632cc-116">Dessa händelser kan aggregeras centralt med hjälp av [händelseinsamlaren i Windows.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="632cc-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="632cc-117">Ofta har SIEM-servrar kopplingar för Windows-händelser, så att du korrelerar alla säkerhetshändelser i DIN SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="632cc-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="632cc-118">Du kan också [övervaka skadlig programvara med hjälp av Malware Assessment-lösningen i logganalys.](/azure/log-analytics/log-analytics-malware)</span><span class="sxs-lookup"><span data-stu-id="632cc-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="632cc-119">Information om hur du övervakar eller fastställer status för PowerShell, WMI eller Microsoft Azure finns i (Tabellen med distribution- och [hanteringsalternativ och rapporteringsalternativ).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)</span><span class="sxs-lookup"><span data-stu-id="632cc-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="632cc-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="632cc-120">Related articles</span></span>

- [<span data-ttu-id="632cc-121">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="632cc-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="632cc-122">Microsoft Defender Antivirus på Windows Server 2016 och 2019</span><span class="sxs-lookup"><span data-stu-id="632cc-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="632cc-123">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="632cc-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)