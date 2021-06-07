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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772143"
---
# <a name="user-resource-type"></a><span data-ttu-id="b4993-104">Användarresurstyp</span><span class="sxs-lookup"><span data-stu-id="b4993-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4993-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b4993-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4993-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4993-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b4993-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4993-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4993-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b4993-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b4993-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b4993-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="b4993-110">Metod</span><span class="sxs-lookup"><span data-stu-id="b4993-110">Method</span></span>|<span data-ttu-id="b4993-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="b4993-111">Return Type</span></span> |<span data-ttu-id="b4993-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b4993-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b4993-113">Lista användarrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="b4993-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="b4993-114">[aviseringssamling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b4993-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="b4993-115">Lista alla aviseringar som är associerade med en [användare.](user.md)</span><span class="sxs-lookup"><span data-stu-id="b4993-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="b4993-116">Lista användarrelaterade enheter</span><span class="sxs-lookup"><span data-stu-id="b4993-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="b4993-117">[maskinsamling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="b4993-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="b4993-118">Lista alla enheter som var inloggade av en [användare.](user.md)</span><span class="sxs-lookup"><span data-stu-id="b4993-118">List all the devices that were logged on by a [user](user.md).</span></span>
