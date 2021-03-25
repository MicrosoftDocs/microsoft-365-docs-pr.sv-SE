---
title: Microsoft Defender-API:er som stöds för slutpunkts-API:er
ms.reviewer: ''
description: Läs mer om specifika Microsoft Defender för slutpunktsenheter där du kan skapa API-anrop till.
keywords: apis, apis som stöds, aktör, aviseringar, enhet, användare, domän, ip, fil, avancerade frågor, avancerad sökning
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198334"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="e63da-104">Microsoft Defender-API:er som stöds för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="e63da-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e63da-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e63da-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e63da-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e63da-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e63da-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e63da-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="e63da-108">Slutpunkts-URI och versionshantering</span><span class="sxs-lookup"><span data-stu-id="e63da-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="e63da-109">Slutpunkt-URI:</span><span class="sxs-lookup"><span data-stu-id="e63da-109">Endpoint URI:</span></span>

> <span data-ttu-id="e63da-110">Tjänstens bas-URI är: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e63da-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="e63da-111">De frågor som baseras på OData har prefixet "/api".</span><span class="sxs-lookup"><span data-stu-id="e63da-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="e63da-112">Om du till exempel vill få aviseringar kan du skicka https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="e63da-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="e63da-113">Versionshantering:</span><span class="sxs-lookup"><span data-stu-id="e63da-113">Versioning:</span></span>

> <span data-ttu-id="e63da-114">API:t har stöd för versionshantering.</span><span class="sxs-lookup"><span data-stu-id="e63da-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="e63da-115">Den aktuella versionen är **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="e63da-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="e63da-116">Om du vill använda en särskild version använder du följande format: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="e63da-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="e63da-117">Till exempel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="e63da-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="e63da-118">Om du inte anger någon version (t.ex. https://api.securitycenter.microsoft.com/api/alerts ) kommer du till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="e63da-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="e63da-119">Läs mer om de enskilda enheter som stöds, där du kan köra API-anrop till, och information som HTTP-begärans värden, begärans rubriker och förväntade svar.</span><span class="sxs-lookup"><span data-stu-id="e63da-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e63da-120">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="e63da-120">In this section</span></span>

<span data-ttu-id="e63da-121">Ämne</span><span class="sxs-lookup"><span data-stu-id="e63da-121">Topic</span></span> | <span data-ttu-id="e63da-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e63da-122">Description</span></span>
:---|:---
<span data-ttu-id="e63da-123">Advanced Hunting</span><span class="sxs-lookup"><span data-stu-id="e63da-123">Advanced Hunting</span></span> | <span data-ttu-id="e63da-124">Köra frågor från API.</span><span class="sxs-lookup"><span data-stu-id="e63da-124">Run queries from API.</span></span>
<span data-ttu-id="e63da-125">Varningar</span><span class="sxs-lookup"><span data-stu-id="e63da-125">Alerts</span></span> | <span data-ttu-id="e63da-126">Kör API-anrop som få aviseringar, skapa en avisering, uppdatera avisering och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="e63da-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="e63da-127">Domäner</span><span class="sxs-lookup"><span data-stu-id="e63da-127">Domains</span></span> | <span data-ttu-id="e63da-128">Kör API-anrop som att hämta domänrelaterade enheter, domänstatistik och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="e63da-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="e63da-129">Filer</span><span class="sxs-lookup"><span data-stu-id="e63da-129">Files</span></span> | <span data-ttu-id="e63da-130">Kör API-anrop som att få filinformation, filrelaterade aviseringar, filrelaterade enheter och filstatistik.</span><span class="sxs-lookup"><span data-stu-id="e63da-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="e63da-131">IP-adresser</span><span class="sxs-lookup"><span data-stu-id="e63da-131">IPs</span></span> | <span data-ttu-id="e63da-132">Kör API-anrop som få IP-relaterade aviseringar och få IP-statistik.</span><span class="sxs-lookup"><span data-stu-id="e63da-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="e63da-133">Datorer</span><span class="sxs-lookup"><span data-stu-id="e63da-133">Machines</span></span> | <span data-ttu-id="e63da-134">Kör API-anrop som att hämta enheter, hämta enheter efter ID, information om inloggade användare, redigera taggar med mera.</span><span class="sxs-lookup"><span data-stu-id="e63da-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="e63da-135">Datoråtgärder</span><span class="sxs-lookup"><span data-stu-id="e63da-135">Machine Actions</span></span> | <span data-ttu-id="e63da-136">Kör API-anrop som isolation, kör antivirussökning och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="e63da-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="e63da-137">Indikatorer</span><span class="sxs-lookup"><span data-stu-id="e63da-137">Indicators</span></span> | <span data-ttu-id="e63da-138">Kör API-anrop som att skapa indikator, hämta indikatorer och ta bort indikatorer.</span><span class="sxs-lookup"><span data-stu-id="e63da-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="e63da-139">Användare</span><span class="sxs-lookup"><span data-stu-id="e63da-139">Users</span></span> | <span data-ttu-id="e63da-140">Kör API-anrop, till exempel få användarrelaterade aviseringar och användarrelaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="e63da-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="e63da-141">Poäng</span><span class="sxs-lookup"><span data-stu-id="e63da-141">Score</span></span> | <span data-ttu-id="e63da-142">Kör API-anrop, till exempel för att få exponeringsresultat eller för att få ett säkert enhetsresultat.</span><span class="sxs-lookup"><span data-stu-id="e63da-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="e63da-143">Programvara</span><span class="sxs-lookup"><span data-stu-id="e63da-143">Software</span></span> | <span data-ttu-id="e63da-144">Kör API-anrop, till exempel säkerhetsproblem efter programvara.</span><span class="sxs-lookup"><span data-stu-id="e63da-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="e63da-145">Sårbarhet</span><span class="sxs-lookup"><span data-stu-id="e63da-145">Vulnerability</span></span> | <span data-ttu-id="e63da-146">Kör API-anrop som listenheter efter säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="e63da-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="e63da-147">Rekommendation</span><span class="sxs-lookup"><span data-stu-id="e63da-147">Recommendation</span></span> | <span data-ttu-id="e63da-148">Kör API-anrop som Få rekommendation via ID.</span><span class="sxs-lookup"><span data-stu-id="e63da-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="e63da-149">Se även</span><span class="sxs-lookup"><span data-stu-id="e63da-149">See also</span></span>
- [<span data-ttu-id="e63da-150">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="e63da-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
