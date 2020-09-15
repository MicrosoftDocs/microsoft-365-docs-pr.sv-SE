---
title: 'API: er för skydd mot Microsoft Threat'
description: 'API: er för skydd mot Microsoft Threat'
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650564"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="33cba-104">API: er för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="33cba-104">Supported Microsoft Threat Protection APIs</span></span> 
<span data-ttu-id="33cba-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="33cba-105">**Applies to:**</span></span>
- <span data-ttu-id="33cba-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="33cba-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="33cba-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="33cba-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="33cba-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="33cba-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="33cba-109">Slut punkts-URI:</span><span class="sxs-lookup"><span data-stu-id="33cba-109">End Point URIs:</span></span>

- <span data-ttu-id="33cba-110">Tjänste leverantörens URI är: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33cba-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="33cba-111">För bättre prestanda kan du använda Server närmare din Geo-plats:</span><span class="sxs-lookup"><span data-stu-id="33cba-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="33cba-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33cba-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="33cba-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33cba-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="33cba-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33cba-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="33cba-115">Resursen för att hämta token ska vara: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="33cba-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="33cba-116">Alla API: er under ```/api``` Path är OData API.</span><span class="sxs-lookup"><span data-stu-id="33cba-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="33cba-117">namn@example.com. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="33cba-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="33cba-118">Lista över tillgängliga API: er</span><span class="sxs-lookup"><span data-stu-id="33cba-118">List of available APIs:</span></span>

<span data-ttu-id="33cba-119">Ämnes</span><span class="sxs-lookup"><span data-stu-id="33cba-119">Topic</span></span> | <span data-ttu-id="33cba-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33cba-120">Description</span></span>
:---|:---
[<span data-ttu-id="33cba-121">Avancerat jakt-API</span><span class="sxs-lookup"><span data-stu-id="33cba-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="33cba-122">Kör avancerade frågor från API.</span><span class="sxs-lookup"><span data-stu-id="33cba-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="33cba-123">API för incidenter</span><span class="sxs-lookup"><span data-stu-id="33cba-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="33cba-124">Kör incident närliggande API-samtal, till exempel: list incidenter, uppdaterings tillbud och mer.</span><span class="sxs-lookup"><span data-stu-id="33cba-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
