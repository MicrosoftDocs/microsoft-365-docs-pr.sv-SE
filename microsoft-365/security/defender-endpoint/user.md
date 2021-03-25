---
title: Användarresurstyp
description: Hämta de senaste Microsoft Defender för slutpunktsaviseringar som är relaterade till användare.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197963"
---
# <a name="user-resource-type"></a><span data-ttu-id="3ee35-104">Användarresurstyp</span><span class="sxs-lookup"><span data-stu-id="3ee35-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ee35-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3ee35-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ee35-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ee35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3ee35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ee35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ee35-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3ee35-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ee35-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3ee35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="3ee35-110">Metod</span><span class="sxs-lookup"><span data-stu-id="3ee35-110">Method</span></span>|<span data-ttu-id="3ee35-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="3ee35-111">Return Type</span></span> |<span data-ttu-id="3ee35-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3ee35-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="3ee35-113">Lista användarrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="3ee35-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="3ee35-114">[aviseringssamling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3ee35-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="3ee35-115">Lista alla aviseringar som är associerade med en [användare.](user.md)</span><span class="sxs-lookup"><span data-stu-id="3ee35-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="3ee35-116">Lista användarrelaterade enheter</span><span class="sxs-lookup"><span data-stu-id="3ee35-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="3ee35-117">[maskinsamling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="3ee35-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="3ee35-118">Lista alla enheter som var inloggade av en [användare.](user.md)</span><span class="sxs-lookup"><span data-stu-id="3ee35-118">List all the devices that were logged on by a [user](user.md).</span></span>
