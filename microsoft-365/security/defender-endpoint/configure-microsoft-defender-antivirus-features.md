---
title: Konfigurera funktionerna i Microsoft Defender Antivirus
description: Du kan Microsoft Defender Antivirus funktioner med Intune, Microsoft Endpoint Configuration Manager, Grupprincip och PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, defender, konfigurera, konfiguration, konfiguration, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, hantering av mobila enheter, GP, grupprincip, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789033"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="a9f8d-104">Konfigurera funktionerna i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a9f8d-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a9f8d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a9f8d-105">**Applies to:**</span></span>

- [<span data-ttu-id="a9f8d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a9f8d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a9f8d-107">Du kan Microsoft Defender Antivirus med ett antal verktyg, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="a9f8d-108">Microsoft Endpoint Manager (som omfattar Microsoft Intune och Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="a9f8d-109">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="a9f8d-109">Group Policy</span></span>
- <span data-ttu-id="a9f8d-110">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="a9f8d-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="a9f8d-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="a9f8d-112">Du kan konfigurera följande breda kategorier av funktioner:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="a9f8d-113">Moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-113">Cloud-delivered protection.</span></span> <span data-ttu-id="a9f8d-114">Se [Moln levererat skydd och Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="a9f8d-115">Ständigt realtidsskydd, inklusive beteende, heuristiskt och maskininlärningsbaserat skydd.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="a9f8d-116">Se [Konfigurera behavioral, heuristisk och realtidsskydd.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="a9f8d-117">Hur slutanvändare interagerar med klienten i enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="a9f8d-118">Se följande resurser:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="a9f8d-119">Hindra användare från att se eller interagera Microsoft Defender Antivirus användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="a9f8d-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="a9f8d-120">Förhindra eller tillåta användare att lokalt ändra Microsoft Defender Antivirus principinställningar</span><span class="sxs-lookup"><span data-stu-id="a9f8d-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="a9f8d-121">Läs [Referensavsnitt om hanterings- och konfigurationsverktyg.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>