---
title: Översikt över identifiering och åtgärd på slutpunkt funktioner
ms.reviewer: ''
description: Läs mer identifiering och åtgärd på slutpunkt Microsoft Defender för Endpoint
keywords: Microsoft Defender för Endpoint, identifiering och åtgärd på slutpunkt, svar, identifiering, cybersäkerhet, skydd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933523"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="3403c-104">Översikt över identifiering och åtgärd på slutpunkt</span><span class="sxs-lookup"><span data-stu-id="3403c-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3403c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3403c-105">**Applies to:**</span></span>
- [<span data-ttu-id="3403c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3403c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3403c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3403c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3403c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3403c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3403c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3403c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3403c-110">Defender för identifiering och åtgärd på slutpunkt tillhandahåller avancerade attackidentifieringar som är nästan i realtid och kan vidtas.</span><span class="sxs-lookup"><span data-stu-id="3403c-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="3403c-111">Säkerhetsanalytiker kan effektivt prioritera varningar, få synlighet över helheten av ett intrång och vidta åtgärder för att åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="3403c-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="3403c-112">När ett hot identifieras skapas aviseringar i systemet för att en analytiker ska undersöka det.</span><span class="sxs-lookup"><span data-stu-id="3403c-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="3403c-113">Varningar med samma attacktekniker eller förser samma attack med samma attacker aggregeras i en enhet som kallas för _en incident_.</span><span class="sxs-lookup"><span data-stu-id="3403c-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="3403c-114">Att samla aviseringar på det här sättet gör det enkelt för analytiker att gemensamt undersöka och reagera på hot.</span><span class="sxs-lookup"><span data-stu-id="3403c-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="3403c-115">Med inspiration från "anta intrång" är Defender för Endpoint kontinuerligt samlad beteenderelaterad cyber telemetri.</span><span class="sxs-lookup"><span data-stu-id="3403c-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="3403c-116">Det omfattar processinformation, nätverksaktiviteter, djupoptisk in i kernel och minneshanteraren, användarinloggningsaktiviteter, ändringar i registret och filsystem m.m.</span><span class="sxs-lookup"><span data-stu-id="3403c-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="3403c-117">Informationen lagras i sex månader så att en analytiker kan färdas tillbaka i tiden till början av en attack.</span><span class="sxs-lookup"><span data-stu-id="3403c-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="3403c-118">Analytikern kan sedan pivotera i olika vyer och närmar sig en undersökning genom flera vektorer.</span><span class="sxs-lookup"><span data-stu-id="3403c-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="3403c-119">Med svarsfunktionerna kan du snabbt åtgärda hot genom att agera på de berörda enheterna.</span><span class="sxs-lookup"><span data-stu-id="3403c-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3403c-120">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3403c-120">Related topics</span></span>
- [<span data-ttu-id="3403c-121">Instrumentpanel för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="3403c-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="3403c-122">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="3403c-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="3403c-123">Varningskö</span><span class="sxs-lookup"><span data-stu-id="3403c-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="3403c-124">Enhetslista</span><span class="sxs-lookup"><span data-stu-id="3403c-124">Devices list</span></span>](machines-view-overview.md)

