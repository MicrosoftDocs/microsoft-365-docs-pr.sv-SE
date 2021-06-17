---
title: Microsoft 365 Defender API:er som stöds
description: Microsoft 365 Defender API:er som stöds
keywords: Microsoft 365 Defender API:er, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985090"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="3a559-104">Microsoft 365 Defender API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="3a559-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3a559-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3a559-105">**Applies to:**</span></span>
- <span data-ttu-id="3a559-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a559-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a559-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="3a559-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3a559-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="3a559-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="3a559-109">Lista över tillgängliga API:er</span><span class="sxs-lookup"><span data-stu-id="3a559-109">List of available APIs</span></span>

<span data-ttu-id="3a559-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="3a559-110">Article</span></span> | <span data-ttu-id="3a559-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3a559-111">Description</span></span>
-|-
[<span data-ttu-id="3a559-112">Avancerad jakt-API</span><span class="sxs-lookup"><span data-stu-id="3a559-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="3a559-113">Kör avancerade frågor för sökning.</span><span class="sxs-lookup"><span data-stu-id="3a559-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="3a559-114">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="3a559-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="3a559-115">Lista och uppdatera incidenter, tillsammans med andra praktiska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="3a559-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="3a559-116">[Direktuppspelnings-API](streaming-api.md) (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="3a559-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="3a559-117">Leverera händelser och aviseringar i realtid när de inträffar i en enda dataström.</span><span class="sxs-lookup"><span data-stu-id="3a559-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="3a559-118">Slutpunkts-URI:er</span><span class="sxs-lookup"><span data-stu-id="3a559-118">Endpoint URIs</span></span>

<span data-ttu-id="3a559-119">Bas-URI för båda de viktigaste API:erna är: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="3a559-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="3a559-120">Du kan använda en server närmare din geolokalisering för bättre prestanda:</span><span class="sxs-lookup"><span data-stu-id="3a559-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="3a559-121">USA: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a559-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="3a559-122">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a559-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="3a559-123">Storbritannien: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a559-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="3a559-124">Token kan köpas genom https://api.security.microsoft.com åtkomst.</span><span class="sxs-lookup"><span data-stu-id="3a559-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="3a559-125">Alla API:er längs sökvägen använder till exempel `/api` [OData-protokollet.](/odata/overview) https://api.security.microsoft.com/api/incidents</span><span class="sxs-lookup"><span data-stu-id="3a559-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3a559-126">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="3a559-126">Related articles</span></span>

- [<span data-ttu-id="3a559-127">Microsoft 365 Defender API:er – översikt</span><span class="sxs-lookup"><span data-stu-id="3a559-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="3a559-128">Få åtkomst Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="3a559-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3a559-129">API för direktuppspelning</span><span class="sxs-lookup"><span data-stu-id="3a559-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="3a559-130">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="3a559-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3a559-131">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="3a559-131">Understand error codes</span></span>](api-error-codes.md)
