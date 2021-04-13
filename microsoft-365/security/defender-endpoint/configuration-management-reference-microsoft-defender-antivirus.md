---
title: Hantera Windows Defender i ditt företag
description: Lär dig hur du använder grupprinciper, konfigurationshanteraren, PowerShell, WMI, Intune och kommandoraden för att hantera Microsoft Defender AV
keywords: grupprincip, gpo, config manager, sccm, sshell, powershell, wmi, intune, defender, antivirus, antimalware, säkerhet, skydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad3e8d2fb61eb5a2a350d061f926dd7bff8ae109
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691076"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="68c8b-104">Hantera Microsoft Defender Antivirus i ditt företag</span><span class="sxs-lookup"><span data-stu-id="68c8b-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="68c8b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="68c8b-105">**Applies to:**</span></span>

- [<span data-ttu-id="68c8b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="68c8b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="68c8b-107">Du kan hantera och konfigurera Microsoft Defender Antivirus med följande verktyg:</span><span class="sxs-lookup"><span data-stu-id="68c8b-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="68c8b-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ingår nu i Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="68c8b-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="68c8b-109">[Konfigurationshanteraren för Microsoft Endpoint](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ingår nu i Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="68c8b-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="68c8b-110">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="68c8b-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="68c8b-111">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="68c8b-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="68c8b-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="68c8b-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="68c8b-113">[Kommandoradsverktyget Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (kallas även verktyget *mpcmdrun.exe* Protection)</span><span class="sxs-lookup"><span data-stu-id="68c8b-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="68c8b-114">Följande artiklar innehåller ytterligare information, länkar och resurser för att använda dessa verktyg för att hantera och konfigurera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="68c8b-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="68c8b-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="68c8b-115">Article</span></span> | <span data-ttu-id="68c8b-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="68c8b-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="68c8b-117">Hantera Microsoft Defender Antivirus med Microsoft Intune och Konfigurationshanteraren för Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="68c8b-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="68c8b-118">Information om hur du använder Intune och Konfigurationshanteraren för att distribuera, hantera, rapportera och konfigurera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="68c8b-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="68c8b-119">Hantera Microsoft Defender Antivirus med grupprincipinställningar</span><span class="sxs-lookup"><span data-stu-id="68c8b-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="68c8b-120">Lista över alla grupprincipinställningar i ADMX-mallar</span><span class="sxs-lookup"><span data-stu-id="68c8b-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="68c8b-121">Hantera Microsoft Defender Antivirus med PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="68c8b-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="68c8b-122">Instruktioner för hur du använder PowerShell-cmdlets för att hantera Microsoft Defender Antivirus samt länkar till dokumentation för alla cmdlets och tillåtna parametrar</span><span class="sxs-lookup"><span data-stu-id="68c8b-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="68c8b-123">Hantera Microsoft Defender Antivirus med Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="68c8b-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="68c8b-124">Instruktioner för hur du använder WMI för att hantera Microsoft Defender Antivirus samt länkar till dokumentation för WMIv2-API:er (inklusive alla klasser, metoder och egenskaper)</span><span class="sxs-lookup"><span data-stu-id="68c8b-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="68c8b-125">Hantera Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="68c8b-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="68c8b-126">Instruktioner om hur du använder det dedikerade kommandoradsverktyget för att hantera och använda Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="68c8b-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |