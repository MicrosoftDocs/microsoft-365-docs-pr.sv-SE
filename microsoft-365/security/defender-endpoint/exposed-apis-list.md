---
title: Microsoft Defender för Endpoint API:er som stöds
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
ms.openlocfilehash: f7a620ad56496b1a26e193a18fa93f4d217431df
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684153"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="1c94f-104">Microsoft Defender för Endpoint API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="1c94f-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c94f-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1c94f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1c94f-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1c94f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c94f-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1c94f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="1c94f-108">Slutpunkts-URI och versionshantering</span><span class="sxs-lookup"><span data-stu-id="1c94f-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="1c94f-109">Slutpunkts-URI</span><span class="sxs-lookup"><span data-stu-id="1c94f-109">Endpoint URI</span></span>

> <span data-ttu-id="1c94f-110">Tjänstens bas-URI är: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1c94f-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="1c94f-111">De frågor som baseras på OData har prefixet "/api".</span><span class="sxs-lookup"><span data-stu-id="1c94f-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="1c94f-112">Om du till exempel vill få aviseringar kan du skicka [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="1c94f-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="1c94f-113">Versionshantering</span><span class="sxs-lookup"><span data-stu-id="1c94f-113">Versioning</span></span>

> <span data-ttu-id="1c94f-114">API:t har stöd för versionshantering.</span><span class="sxs-lookup"><span data-stu-id="1c94f-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="1c94f-115">Den aktuella versionen är **V1.0.**</span><span class="sxs-lookup"><span data-stu-id="1c94f-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="1c94f-116">Om du vill använda en särskild version använder du följande format: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="1c94f-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="1c94f-117">Till exempel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="1c94f-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="1c94f-118">Om du inte anger någon version (t.ex. `https://api.securitycenter.microsoft.com/api/alerts` ) kommer du till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="1c94f-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="1c94f-119">Läs mer om de enskilda enheter som stöds, där du kan köra API-anrop till, och information som HTTP-begärans värden, begärans rubriker och förväntade svar.</span><span class="sxs-lookup"><span data-stu-id="1c94f-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1c94f-120">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="1c94f-120">In this section</span></span>

<span data-ttu-id="1c94f-121">Ämne</span><span class="sxs-lookup"><span data-stu-id="1c94f-121">Topic</span></span> | <span data-ttu-id="1c94f-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1c94f-122">Description</span></span>
:---|:---
[<span data-ttu-id="1c94f-123">Avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1c94f-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="1c94f-124">Köra frågor från API.</span><span class="sxs-lookup"><span data-stu-id="1c94f-124">Run queries from API.</span></span>
[<span data-ttu-id="1c94f-125">Metod och egenskaper för varningar</span><span class="sxs-lookup"><span data-stu-id="1c94f-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="1c94f-126">Kör API-anrop \- som få aviseringar, skapa en avisering, uppdatera avisering och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="1c94f-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="1c94f-127">Exportera utvärderingsmetoder och egenskaper per enhet</span><span class="sxs-lookup"><span data-stu-id="1c94f-127">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md) | <span data-ttu-id="1c94f-128">Kör API-anrop som \- export secure configuration assessment, export software inventory assessment och export software vulnerabilities assessment.</span><span class="sxs-lookup"><span data-stu-id="1c94f-128">Run API calls such as \- export secure configuration assessment, export software inventory assessment,  and export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="1c94f-129">Metoder och egenskaper för automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="1c94f-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="1c94f-130">Kör API-anrop, \- till exempel hämta undersökningssamling.</span><span class="sxs-lookup"><span data-stu-id="1c94f-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="1c94f-131">Hämta domänrelaterade varningar</span><span class="sxs-lookup"><span data-stu-id="1c94f-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="1c94f-132">Kör API-anrop \- som att hämta domänrelaterade enheter, domänstatistik och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="1c94f-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="1c94f-133">Filmetoder och -egenskaper</span><span class="sxs-lookup"><span data-stu-id="1c94f-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="1c94f-134">Kör API-anrop \- som att få filinformation, filrelaterade aviseringar, filrelaterade enheter och filstatistik.</span><span class="sxs-lookup"><span data-stu-id="1c94f-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="1c94f-135">Indikatormetoder och -egenskaper</span><span class="sxs-lookup"><span data-stu-id="1c94f-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="1c94f-136">Kör API-anrop, \- t.ex. hämta indikatorer, skapa indikator och ta bort indikatorer.</span><span class="sxs-lookup"><span data-stu-id="1c94f-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="1c94f-137">Hämta IP-relaterade varningar</span><span class="sxs-lookup"><span data-stu-id="1c94f-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="1c94f-138">Kör API-anrop som \- få IP-relaterade aviseringar och få IP-statistik.</span><span class="sxs-lookup"><span data-stu-id="1c94f-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="1c94f-139">Maskinmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="1c94f-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="1c94f-140">Kör API-anrop \- som att hämta enheter, hämta enheter efter ID, information om inloggade användare, redigera taggar med mera.</span><span class="sxs-lookup"><span data-stu-id="1c94f-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="1c94f-141">Metoder och egenskaper för maskinåtgärd</span><span class="sxs-lookup"><span data-stu-id="1c94f-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="1c94f-142">Kör API-anrop som \- isolation, kör antivirussökning och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="1c94f-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="1c94f-143">Metoder och egenskaper för rekommendation</span><span class="sxs-lookup"><span data-stu-id="1c94f-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="1c94f-144">Kör API-anrop som \- få rekommendation från ID.</span><span class="sxs-lookup"><span data-stu-id="1c94f-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="1c94f-145">Metoder och egenskaper för åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="1c94f-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="1c94f-146">Kör API-anrop som få alla åtgärder, få åtgärder på exponerade enheter och \- få en åtgärdsaktivitet per id.</span><span class="sxs-lookup"><span data-stu-id="1c94f-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="1c94f-147">Poängmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="1c94f-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="1c94f-148">Kör API-anrop, \- till exempel för att få exponeringsresultat eller för att få ett säkert enhetsresultat.</span><span class="sxs-lookup"><span data-stu-id="1c94f-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="1c94f-149">Programvarumetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="1c94f-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="1c94f-150">Kör API-anrop, \- till exempel säkerhetsproblem efter programvara.</span><span class="sxs-lookup"><span data-stu-id="1c94f-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="1c94f-151">Användarmetoder</span><span class="sxs-lookup"><span data-stu-id="1c94f-151">User methods</span></span>](user.md) | <span data-ttu-id="1c94f-152">Kör \- API-anrop, till exempel få användarrelaterade aviseringar och användarrelaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="1c94f-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="1c94f-153">Metoder och egenskaper för sårbarhet</span><span class="sxs-lookup"><span data-stu-id="1c94f-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="1c94f-154">Kör API-anrop som \- listenheter efter säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="1c94f-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c94f-155">Se även</span><span class="sxs-lookup"><span data-stu-id="1c94f-155">See also</span></span>

- [<span data-ttu-id="1c94f-156">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="1c94f-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="1c94f-157">Information om Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="1c94f-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
