---
title: 'Microsoft 365 Defender API: er'
description: 'Microsoft 365 Defender API: er'
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844966"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="c153e-104">Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="c153e-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c153e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c153e-105">**Applies to:**</span></span>
- <span data-ttu-id="c153e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c153e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c153e-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="c153e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c153e-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="c153e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="c153e-109">Slut punkts-URI:</span><span class="sxs-lookup"><span data-stu-id="c153e-109">End Point URIs:</span></span>

- <span data-ttu-id="c153e-110">Tjänste leverantörens URI är: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c153e-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="c153e-111">För bättre prestanda kan du använda Server närmare din Geo-plats:</span><span class="sxs-lookup"><span data-stu-id="c153e-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="c153e-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c153e-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="c153e-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c153e-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="c153e-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c153e-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="c153e-115">Resursen för att hämta token ska vara: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c153e-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="c153e-116">Alla API: er under ```/api``` Path är OData API.</span><span class="sxs-lookup"><span data-stu-id="c153e-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="c153e-117">namn@example.com. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="c153e-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="c153e-118">Lista över tillgängliga API: er</span><span class="sxs-lookup"><span data-stu-id="c153e-118">List of available APIs:</span></span>

<span data-ttu-id="c153e-119">Ämnes</span><span class="sxs-lookup"><span data-stu-id="c153e-119">Topic</span></span> | <span data-ttu-id="c153e-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c153e-120">Description</span></span>
:---|:---
[<span data-ttu-id="c153e-121">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="c153e-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="c153e-122">Kör avancerade frågor från API.</span><span class="sxs-lookup"><span data-stu-id="c153e-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="c153e-123">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="c153e-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="c153e-124">Kör incident närliggande API-samtal, till exempel: list incidenter, uppdaterings tillbud och mer.</span><span class="sxs-lookup"><span data-stu-id="c153e-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
