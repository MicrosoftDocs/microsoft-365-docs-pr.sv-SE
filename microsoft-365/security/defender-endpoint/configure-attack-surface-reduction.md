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
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="74895-104">Konfigurera funktioner för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="74895-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="74895-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74895-105">**Applies to:**</span></span>

- [<span data-ttu-id="74895-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74895-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74895-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74895-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="74895-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="74895-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="74895-109">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="74895-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="74895-110">Defender för Slutpunkt innehåller flera funktioner för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="74895-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="74895-111">Mer information finns i [Översikt över minskningsfunktioner för attackytor.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="74895-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="74895-112">Konfigurera minskning av attackytan i din miljö genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="74895-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="74895-113">[Aktivera maskinvarubaserad avgränsning för Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span><span class="sxs-lookup"><span data-stu-id="74895-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="74895-114">Aktivera programkontroll.</span><span class="sxs-lookup"><span data-stu-id="74895-114">Enable application control.</span></span>

   1. <span data-ttu-id="74895-115">Granska basprinciper i Windows.</span><span class="sxs-lookup"><span data-stu-id="74895-115">Review base policies in Windows.</span></span> <span data-ttu-id="74895-116">Se [Exempel på basprinciper.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="74895-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="74895-117">Se Windows Defender [för designguiden för Programkontroll.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="74895-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="74895-118">Mer information [finns i Windows Defender programkontrollprinciper (WDAC).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="74895-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="74895-119">[Aktivera reglerad mappåtkomst.](enable-controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="74895-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="74895-120">[Aktivera nätverksskydd](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="74895-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="74895-121">[Aktivera sårbarhetsskydd.](enable-exploit-protection.md)</span><span class="sxs-lookup"><span data-stu-id="74895-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="74895-122">[Konfigurera regler för att minska attackytan](enable-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="74895-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="74895-123">Konfigurera nätverkets brandvägg.</span><span class="sxs-lookup"><span data-stu-id="74895-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="74895-124">Få en översikt över [Windows Defender med avancerad säkerhet.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="74895-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="74895-125">Använd guiden [Windows Defender för att](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) bestämma hur du vill utforma brandväggsprinciperna.</span><span class="sxs-lookup"><span data-stu-id="74895-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="74895-126">Använd Windows Defender [för brandväggsdistribution](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) för att konfigurera din organisations brandvägg med avancerad säkerhet.</span><span class="sxs-lookup"><span data-stu-id="74895-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="74895-127">När du konfigurerar funktioner för att minska attackytan kan du i de flesta fall välja mellan flera metoder:</span><span class="sxs-lookup"><span data-stu-id="74895-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="74895-128">Microsoft Endpoint Manager (som nu innehåller Microsoft Intune och Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="74895-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="74895-129">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="74895-129">Group Policy</span></span>
> - <span data-ttu-id="74895-130">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="74895-130">PowerShell cmdlets</span></span>
