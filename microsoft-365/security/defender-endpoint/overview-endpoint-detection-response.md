---
title: Översikt över funktioner för identifiering av slutpunkt och svar
ms.reviewer: ''
description: Läs mer om funktionerna för identifiering och svar av slutpunkter i Microsoft Defender för Endpoint
keywords: microsoft defender för slutpunkt, identifiering och svar av slutpunkter, svar, identifiering, identifiering, cybersäkerhet, skydd
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
ms.openlocfilehash: 138a6afde9e8c601fd41811928580644b85bf2e2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861725"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="083b0-104">Översikt över identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="083b0-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="083b0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="083b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="083b0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="083b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="083b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="083b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="083b0-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="083b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="083b0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="083b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="083b0-110">Defender för slutpunktsidentifierings- och svarsfunktioner tillhandahåller avancerade attackidentifieringar som är nära i realtid och kan användas.</span><span class="sxs-lookup"><span data-stu-id="083b0-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="083b0-111">Säkerhetsanalytiker kan effektivt prioritera varningar, få synlighet över helheten av ett intrång och vidta åtgärder för att åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="083b0-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="083b0-112">När ett hot identifieras skapas aviseringar i systemet för att en analytiker ska undersöka det.</span><span class="sxs-lookup"><span data-stu-id="083b0-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="083b0-113">Varningar med samma attacktekniker eller förser samma attack med samma attacker aggregeras i en enhet som kallas för _en incident_.</span><span class="sxs-lookup"><span data-stu-id="083b0-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="083b0-114">Att samla aviseringar på det här sättet gör det enkelt för analytiker att gemensamt undersöka och reagera på hot.</span><span class="sxs-lookup"><span data-stu-id="083b0-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="083b0-115">Med inspiration från "anta intrång" är Defender för Endpoint kontinuerligt samlad beteenderelaterad cyber telemetri.</span><span class="sxs-lookup"><span data-stu-id="083b0-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="083b0-116">Det omfattar processinformation, nätverksaktiviteter, djupoptisk in i kernel och minneshanteraren, användarinloggningsaktiviteter, ändringar i registret och filsystem m.m.</span><span class="sxs-lookup"><span data-stu-id="083b0-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="083b0-117">Informationen lagras i sex månader så att en analytiker kan färdas tillbaka i tiden till början av en attack.</span><span class="sxs-lookup"><span data-stu-id="083b0-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="083b0-118">Analytikern kan sedan pivotera i olika vyer och närmar sig en undersökning genom flera vektorer.</span><span class="sxs-lookup"><span data-stu-id="083b0-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="083b0-119">Med svarsfunktionerna kan du snabbt åtgärda hot genom att agera på de berörda enheterna.</span><span class="sxs-lookup"><span data-stu-id="083b0-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="083b0-120">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="083b0-120">Related topics</span></span>
- [<span data-ttu-id="083b0-121">Instrumentpanel för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="083b0-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="083b0-122">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="083b0-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="083b0-123">Varningskö</span><span class="sxs-lookup"><span data-stu-id="083b0-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="083b0-124">Enhetslista</span><span class="sxs-lookup"><span data-stu-id="083b0-124">Devices list</span></span>](machines-view-overview.md)

