---
title: 'API: er som stöds av Microsoft Hotskydd'
description: 'API: er som stöds av Microsoft Hotskydd'
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203701"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="52ba0-104">API: er som stöds av Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="52ba0-104">Supported Microsoft Threat Protection APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="52ba0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="52ba0-105">**Applies to:**</span></span>
- <span data-ttu-id="52ba0-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="52ba0-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="52ba0-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="52ba0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="52ba0-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="52ba0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="52ba0-109">Slut punkts-URI:</span><span class="sxs-lookup"><span data-stu-id="52ba0-109">End Point URIs:</span></span>

- <span data-ttu-id="52ba0-110">Tjänste leverantörens URI är: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52ba0-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="52ba0-111">För bättre prestanda kan du använda Server närmare din Geo-plats:</span><span class="sxs-lookup"><span data-stu-id="52ba0-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="52ba0-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52ba0-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="52ba0-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52ba0-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="52ba0-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52ba0-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="52ba0-115">Resursen för att hämta token ska vara: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="52ba0-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="52ba0-116">Alla API: er under ```/api``` Path är OData API.</span><span class="sxs-lookup"><span data-stu-id="52ba0-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="52ba0-117">namn@example.com. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="52ba0-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="52ba0-118">Lista över tillgängliga API: er</span><span class="sxs-lookup"><span data-stu-id="52ba0-118">List of available APIs:</span></span>

<span data-ttu-id="52ba0-119">Ämnes</span><span class="sxs-lookup"><span data-stu-id="52ba0-119">Topic</span></span> | <span data-ttu-id="52ba0-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="52ba0-120">Description</span></span>
:---|:---
[<span data-ttu-id="52ba0-121">Advanced jakt-API</span><span class="sxs-lookup"><span data-stu-id="52ba0-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="52ba0-122">Kör avancerade frågor från API.</span><span class="sxs-lookup"><span data-stu-id="52ba0-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="52ba0-123">API:er för tillbud</span><span class="sxs-lookup"><span data-stu-id="52ba0-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="52ba0-124">Kör incident närliggande API-samtal, till exempel: list incidenter, uppdaterings tillbud och mer.</span><span class="sxs-lookup"><span data-stu-id="52ba0-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
