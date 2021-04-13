---
title: Konfigurera funktioner för Microsoft Defender Antivirus
description: Du kan konfigurera antivirusfunktionerna i Microsoft Defender med Intune, Microsoft Endpoint Configuration Manager, Grupprincip och PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, defender, konfigurera, konfiguration, konfigurationshanteraren, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, hantering av mobila enheter, GP, grupprincip, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690817"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="b2a80-104">Konfigurera funktioner för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b2a80-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b2a80-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b2a80-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2a80-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b2a80-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b2a80-107">Du kan konfigurera Microsoft Defender Antivirus med ett antal verktyg, till exempel:</span><span class="sxs-lookup"><span data-stu-id="b2a80-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="b2a80-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b2a80-108">Microsoft Intune</span></span>
- <span data-ttu-id="b2a80-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b2a80-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="b2a80-110">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="b2a80-110">Group Policy</span></span>
- <span data-ttu-id="b2a80-111">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="b2a80-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="b2a80-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="b2a80-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="b2a80-113">Du kan konfigurera följande breda kategorier av funktioner:</span><span class="sxs-lookup"><span data-stu-id="b2a80-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="b2a80-114">Moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="b2a80-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="b2a80-115">Ständigt realtidsskydd, inklusive beteende, heuristiskt och maskininlärningsbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="b2a80-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="b2a80-116">Hur slutanvändare interagerar med klienten i enskilda slutpunkter</span><span class="sxs-lookup"><span data-stu-id="b2a80-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="b2a80-117">I följande artiklar beskrivs hur du utför viktiga uppgifter när du konfigurerar Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2a80-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b2a80-118">Varje artikel innehåller instruktioner för det tillämpliga konfigurationsverktyget (eller verktygen).</span><span class="sxs-lookup"><span data-stu-id="b2a80-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="b2a80-119">Artikel</span><span class="sxs-lookup"><span data-stu-id="b2a80-119">Article</span></span>  |<span data-ttu-id="b2a80-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b2a80-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="b2a80-121">Använd Microsofts molnskydd med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b2a80-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="b2a80-122">Använd moln levererat skydd för avancerad, snabb och robust antivirusidentifiering.</span><span class="sxs-lookup"><span data-stu-id="b2a80-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="b2a80-123">Konfigurera behavioruellt, heuristiskt och realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="b2a80-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="b2a80-124">Aktivera funktionsbaserat, heuristiskt och realtidsskydd för antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2a80-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="b2a80-125">Konfigurera interaktion med slutanvändare med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b2a80-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="b2a80-126">Konfigurera hur slutanvändarna i organisationen interagerar med Microsoft Defender Antivirus, vilka meddelanden de ser och om de kan åsidosätta inställningar.</span><span class="sxs-lookup"><span data-stu-id="b2a80-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="b2a80-127">Du kan också läsa avsnittet [Referensavsnitt för hanterings- och konfigurationsverktyg,](configuration-management-reference-microsoft-defender-antivirus.md) där det finns en översikt över de olika verktygen samt länkar till ytterligare hjälp.</span><span class="sxs-lookup"><span data-stu-id="b2a80-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>