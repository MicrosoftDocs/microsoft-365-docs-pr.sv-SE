---
title: Konfigurera Microsoft Defender Antivirus med Microsoft Endpoint Manager
description: Använd Microsoft Endpoint Manager och Microsoft Intune för att konfigurera Microsoft Defender AV och Endpoint Protection
keywords: s den, intune, slutpunktsskydd, konfiguration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683757"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="4bd0d-104">Använda Microsoft Endpoint Manager för att konfigurera och hantera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="4bd0d-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4bd0d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4bd0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="4bd0d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4bd0d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4bd0d-107">Du kan använda [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) för att konfigurera Microsoft Defender Antivirus genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="4bd0d-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Konfigurationshanteraren](/mem/configmgr/core/understand/introduction) är nu en del av Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="4bd0d-109">Konfigurera Microsoft Defender Antivirus skanningar i Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4bd0d-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="4bd0d-110">Gå till Microsoft Endpoint Manager ( ) [https://endpoint.microsoft.com](https://endpoint.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="4bd0d-111">Gå till **Slutpunktssäkerhet**.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="4bd0d-112">Välj **Antivirus** under **Hantera.**</span><span class="sxs-lookup"><span data-stu-id="4bd0d-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="4bd0d-113">Välj Microsoft Defender Antivirus princip.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="4bd0d-114">Under **Hantera** väljer du **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="4bd0d-115">Välj **Redigera** bredvid **Konfigurationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="4bd0d-116">Expandera avsnittet **Skanna** och granska eller redigera inställningarna för skanning.</span><span class="sxs-lookup"><span data-stu-id="4bd0d-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="4bd0d-117">Välj **Granska + spara**</span><span class="sxs-lookup"><span data-stu-id="4bd0d-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="4bd0d-118">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="4bd0d-118">Need help?</span></span> <span data-ttu-id="4bd0d-119">Se [Hantera slutpunktssäkerhet i Microsoft Intune](/mem/intune/protect/endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="4bd0d-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="4bd0d-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4bd0d-120">Related articles</span></span>

- [<span data-ttu-id="4bd0d-121">Referensartiklar för hantering och konfigurationsverktyg</span><span class="sxs-lookup"><span data-stu-id="4bd0d-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4bd0d-122">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="4bd0d-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)