---
title: Konfigurera funktionerna i Microsoft Defender Antivirus
description: Du kan Microsoft Defender Antivirus funktioner med Intune, Microsoft Endpoint Configuration Manager, Grupprincip och PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, defender, konfigurera, konfiguration, konfiguration, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, hantering av mobila enheter, GP, grupprincip, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925401"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="c22d4-104">Konfigurera funktionerna i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c22d4-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="c22d4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c22d4-105">**Applies to:**</span></span>

- [<span data-ttu-id="c22d4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c22d4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c22d4-107">Du kan Microsoft Defender Antivirus med ett antal verktyg, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c22d4-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="c22d4-108">Microsoft Endpoint Manager (som omfattar Microsoft Intune och Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="c22d4-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="c22d4-109">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="c22d4-109">Group Policy</span></span>
- <span data-ttu-id="c22d4-110">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="c22d4-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="c22d4-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="c22d4-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="c22d4-112">Du kan konfigurera följande breda kategorier av funktioner:</span><span class="sxs-lookup"><span data-stu-id="c22d4-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="c22d4-113">Moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="c22d4-113">Cloud-delivered protection.</span></span> <span data-ttu-id="c22d4-114">Se [Moln levererat skydd och Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c22d4-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="c22d4-115">Ständigt realtidsskydd, inklusive beteende, heuristiskt och maskininlärningsbaserat skydd.</span><span class="sxs-lookup"><span data-stu-id="c22d4-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="c22d4-116">Se [Konfigurera behavioral, heuristisk och realtidsskydd.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c22d4-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="c22d4-117">Hur slutanvändare interagerar med klienten i enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="c22d4-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="c22d4-118">Se följande resurser:</span><span class="sxs-lookup"><span data-stu-id="c22d4-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="c22d4-119">Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="c22d4-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="c22d4-120">Förhindra eller tillåta användare att lokalt ändra Microsoft Defender Antivirus principinställningar</span><span class="sxs-lookup"><span data-stu-id="c22d4-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="c22d4-121">Läs [Referensavsnitt om hanterings- och konfigurationsverktyg.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c22d4-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
