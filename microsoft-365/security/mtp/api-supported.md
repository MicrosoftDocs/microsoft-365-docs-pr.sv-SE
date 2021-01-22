---
title: 'Microsoft 365 Defender API: er som stöds'
description: 'Microsoft 365 Defender API: er som stöds'
keywords: MTP, API:er, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926204"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="1ace8-104">Microsoft 365 Defender API: er som stöds</span><span class="sxs-lookup"><span data-stu-id="1ace8-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1ace8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1ace8-105">**Applies to:**</span></span>
- <span data-ttu-id="1ace8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ace8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ace8-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="1ace8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1ace8-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="1ace8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="1ace8-109">Lista över tillgängliga API:er</span><span class="sxs-lookup"><span data-stu-id="1ace8-109">List of available APIs</span></span>

<span data-ttu-id="1ace8-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="1ace8-110">Article</span></span> | <span data-ttu-id="1ace8-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1ace8-111">Description</span></span>
-|-
[<span data-ttu-id="1ace8-112">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="1ace8-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="1ace8-113">Köra Avancerade frågor om sökfrågor.</span><span class="sxs-lookup"><span data-stu-id="1ace8-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="1ace8-114">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="1ace8-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="1ace8-115">Lista och uppdatera incidenter, tillsammans med andra praktiska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="1ace8-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="1ace8-116">Slutpunkts-URI:er</span><span class="sxs-lookup"><span data-stu-id="1ace8-116">Endpoint URIs</span></span>

<span data-ttu-id="1ace8-117">Bas-URI för båda de viktigaste API:erna är: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="1ace8-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="1ace8-118">Använd en server närmare din geolokalisering för bättre prestanda:</span><span class="sxs-lookup"><span data-stu-id="1ace8-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="1ace8-119">USA: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1ace8-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="1ace8-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1ace8-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="1ace8-121">Storbritannien: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1ace8-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="1ace8-122">Token kan köpas genom https://api.security.microsoft.com åtkomst.</span><span class="sxs-lookup"><span data-stu-id="1ace8-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="1ace8-123">Alla API:er längs vägen använder till exempel `/api` [OData-protokollet.](https://docs.microsoft.com/odata/overview) https://api.security.microsoft.com/api/incidents</span><span class="sxs-lookup"><span data-stu-id="1ace8-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1ace8-124">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="1ace8-124">Related articles</span></span>

- [<span data-ttu-id="1ace8-125">Översikt över API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ace8-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1ace8-126">Få åtkomst till API:er för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ace8-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="1ace8-127">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="1ace8-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1ace8-128">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="1ace8-128">Understand error codes</span></span>](api-error-codes.md)
