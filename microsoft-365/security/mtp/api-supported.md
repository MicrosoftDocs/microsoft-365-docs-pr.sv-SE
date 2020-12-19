---
title: 'Microsoft 365 Defender API: er som stöds'
description: 'Microsoft 365 Defender API: er som stöds'
keywords: 'MTP, API: er'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719328"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="d3f38-104">Microsoft 365 Defender API: er som stöds</span><span class="sxs-lookup"><span data-stu-id="d3f38-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d3f38-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d3f38-105">**Applies to:**</span></span>
- <span data-ttu-id="d3f38-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3f38-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3f38-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="d3f38-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d3f38-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="d3f38-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="d3f38-109">Lista över tillgängliga API: er</span><span class="sxs-lookup"><span data-stu-id="d3f38-109">List of available APIs</span></span>

<span data-ttu-id="d3f38-110">Artiklar</span><span class="sxs-lookup"><span data-stu-id="d3f38-110">Article</span></span> | <span data-ttu-id="d3f38-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d3f38-111">Description</span></span>
-|-
[<span data-ttu-id="d3f38-112">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="d3f38-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="d3f38-113">Kör avancerade jakt frågor.</span><span class="sxs-lookup"><span data-stu-id="d3f38-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="d3f38-114">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="d3f38-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="d3f38-115">Lista och uppdatera händelser samt andra praktiska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="d3f38-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="d3f38-116">Slut punkts-URI</span><span class="sxs-lookup"><span data-stu-id="d3f38-116">Endpoint URIs</span></span>

<span data-ttu-id="d3f38-117">Bas-URI för båda huvud gränssnitten är: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="d3f38-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="d3f38-118">För bättre prestanda bör du använda en server närmast din plats:</span><span class="sxs-lookup"><span data-stu-id="d3f38-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="d3f38-119">USA: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d3f38-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="d3f38-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d3f38-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="d3f38-121">Storbritannien: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d3f38-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="d3f38-122">Token kan erhållas genom åtkomst https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="d3f38-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="d3f38-123">Alla API: er längs `/api` sökvägen använder protokollet [OData](https://docs.microsoft.com/odata/overview) , till exempel https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="d3f38-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d3f38-124">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d3f38-124">Related articles</span></span>

- [<span data-ttu-id="d3f38-125">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="d3f38-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d3f38-126">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="d3f38-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="d3f38-127">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="d3f38-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d3f38-128">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="d3f38-128">Understand error codes</span></span>](api-error-codes.md)
