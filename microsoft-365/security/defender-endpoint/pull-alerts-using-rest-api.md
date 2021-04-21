---
title: Hämta Microsoft Defender för slutpunktsidentifiering med REST API
description: Lär dig hur du anropar en Microsoft Defender för Endpoint API-slutpunkt för att hämta identifieringar i JSON-format med HJÄLP av SIEM REST API.
keywords: identifieringar, dra identifieringar, rest api, begäran, svar
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 06028f64a3340aeeef52269bc8a1e739d18e6db7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903124"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="c4104-104">Hämta Microsoft Defender för slutpunktsidentifiering med HJÄLP av SIEM REST API</span><span class="sxs-lookup"><span data-stu-id="c4104-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c4104-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c4104-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4104-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c4104-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4104-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4104-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c4104-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c4104-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4104-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c4104-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="c4104-110">[Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.</span><span class="sxs-lookup"><span data-stu-id="c4104-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="c4104-111">[Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="c4104-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="c4104-112">-Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="c4104-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="c4104-113">Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c4104-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="c4104-114">Microsoft Defender för Endpoint har stöd för OAuth 2.0-protokollet för att hämta identifieringar från API:et.</span><span class="sxs-lookup"><span data-stu-id="c4104-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="c4104-115">OAuth 2.0-protokollet har i allmänhet stöd för fyra typer av flöden:</span><span class="sxs-lookup"><span data-stu-id="c4104-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="c4104-116">Flöde för auktoriseringsauktorisering</span><span class="sxs-lookup"><span data-stu-id="c4104-116">Authorization grant flow</span></span>
- <span data-ttu-id="c4104-117">Implicit flöde</span><span class="sxs-lookup"><span data-stu-id="c4104-117">Implicit flow</span></span>
- <span data-ttu-id="c4104-118">Flöde för klientautentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="c4104-118">Client credentials flow</span></span>
- <span data-ttu-id="c4104-119">Flöde för resursägare</span><span class="sxs-lookup"><span data-stu-id="c4104-119">Resource owner flow</span></span>

<span data-ttu-id="c4104-120">Mer information om OAuth-specifikationer finns på [OAuth-webbplatsen.](http://www.oauth.net)</span><span class="sxs-lookup"><span data-stu-id="c4104-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="c4104-121">Microsoft Defender för  Endpoint har  stöd för flöde för auktoriseringsauktorisering och autentiseringsuppgifter för klient för att få åtkomst till identifieringar med Azure Active Directory (AAD) som auktoriseringsserver.</span><span class="sxs-lookup"><span data-stu-id="c4104-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="c4104-122">Flödet för auktoriseringsauktoriseringsautentisering använder användarautentiseringsuppgifter för att få en auktoriseringskod som sedan används för att hämta en åtkomsttoken. </span><span class="sxs-lookup"><span data-stu-id="c4104-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="c4104-123">Flödet _för autentiseringsuppgifter för klient använder_ klientautentiseringsuppgifter för att autentisera mot Microsoft Defender för slutpunktsslutpunkts-URL.</span><span class="sxs-lookup"><span data-stu-id="c4104-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="c4104-124">Det här flödet passar för scenarier när en OAuth-klient skapar begäranden till ett API som inte kräver användarautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c4104-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="c4104-125">Använd följande metod i Microsoft Defender för Endpoint API för att hämta identifieringar i JSON-format.</span><span class="sxs-lookup"><span data-stu-id="c4104-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="c4104-126">I Microsoft Defender Säkerhetscenter slås liknande aviseringsidentifiering ihop till en enda avisering.</span><span class="sxs-lookup"><span data-stu-id="c4104-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="c4104-127">Detta API hämtar aviseringsidentifiering i sin rådata utifrån de frågeparametrar du anger, så att du kan använda din egen gruppering och filtrering.</span><span class="sxs-lookup"><span data-stu-id="c4104-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="c4104-128">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c4104-128">Before you begin</span></span>
- <span data-ttu-id="c4104-129">Innan du anropar Microsoft Defender för slutpunktsslutpunkten för att hämta identifieringar måste du aktivera SIEM-integrationsprogrammet i Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="c4104-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c4104-130">Mer information finns i Aktivera [SIEM-integrering i Microsoft Defender för slutpunkt.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="c4104-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="c4104-131">Notera följande värden i din Azure-programregistrering.</span><span class="sxs-lookup"><span data-stu-id="c4104-131">Take note of the following values in your Azure application registration.</span></span> <span data-ttu-id="c4104-132">Du behöver dessa värden för att konfigurera OAuth-flödet i tjänsten eller daemon-appen:</span><span class="sxs-lookup"><span data-stu-id="c4104-132">You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="c4104-133">Program-ID (unikt för ditt program)</span><span class="sxs-lookup"><span data-stu-id="c4104-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="c4104-134">Appnyckel eller hemlig (unik för ditt program)</span><span class="sxs-lookup"><span data-stu-id="c4104-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="c4104-135">OAuth 2.0-tokenslutpunkt för appen</span><span class="sxs-lookup"><span data-stu-id="c4104-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="c4104-136">Hitta det här värdet genom **att klicka på** Visa slutpunkter längst ned på Azure Management Portal på appsidan.</span><span class="sxs-lookup"><span data-stu-id="c4104-136">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page.</span></span> <span data-ttu-id="c4104-137">Slutpunkten ser ut så `https://login.microsoftonline.com/{tenantId}/oauth2/token` här.</span><span class="sxs-lookup"><span data-stu-id="c4104-137">The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="c4104-138">Hämta en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="c4104-138">Get an access token</span></span>
<span data-ttu-id="c4104-139">Innan du skapar samtal till slutpunkten måste du få en åtkomsttoken.</span><span class="sxs-lookup"><span data-stu-id="c4104-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="c4104-140">Du använder åtkomsttoken för att komma åt den skyddade resursen, vilket identifieringar visas i Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="c4104-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="c4104-141">För att få en åtkomsttoken måste du göra en POST-begäran till den token som utfärdar slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="c4104-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="c4104-142">Här är ett exempel på en förfrågan:</span><span class="sxs-lookup"><span data-stu-id="c4104-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="c4104-143">Svaret innehåller information om åtkomsttoken och utgångsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="c4104-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="c4104-144">Nu kan du använda värdet i fältet *access_token* i en begäran till Defender för slutpunkts-API.</span><span class="sxs-lookup"><span data-stu-id="c4104-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="c4104-145">Begäran</span><span class="sxs-lookup"><span data-stu-id="c4104-145">Request</span></span>
<span data-ttu-id="c4104-146">Med en åtkomsttoken kan appen göra autentiserade begäranden till Microsoft Defender för Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="c4104-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="c4104-147">Appen måste lägga till åtkomsttoken i rubriken Auktorisering för varje begäran.</span><span class="sxs-lookup"><span data-stu-id="c4104-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="c4104-148">Syntax för begäran</span><span class="sxs-lookup"><span data-stu-id="c4104-148">Request syntax</span></span>
<span data-ttu-id="c4104-149">Metod</span><span class="sxs-lookup"><span data-stu-id="c4104-149">Method</span></span> | <span data-ttu-id="c4104-150">Begär URI</span><span class="sxs-lookup"><span data-stu-id="c4104-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="c4104-151">SKAFFA</span><span class="sxs-lookup"><span data-stu-id="c4104-151">GET</span></span>| <span data-ttu-id="c4104-152">Använd URI:en som gäller för din region.</span><span class="sxs-lookup"><span data-stu-id="c4104-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="c4104-153">**För EU:**`https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="c4104-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="c4104-154">**För USA:**`https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="c4104-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="c4104-155">**För Storbritannien:**`https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="c4104-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="c4104-156">Sidhuvud för begäran</span><span class="sxs-lookup"><span data-stu-id="c4104-156">Request header</span></span>
<span data-ttu-id="c4104-157">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="c4104-157">Header</span></span> | <span data-ttu-id="c4104-158">Skriv</span><span class="sxs-lookup"><span data-stu-id="c4104-158">Type</span></span> | <span data-ttu-id="c4104-159">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4104-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="c4104-160">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="c4104-160">Authorization</span></span> | <span data-ttu-id="c4104-161">sträng</span><span class="sxs-lookup"><span data-stu-id="c4104-161">string</span></span> | <span data-ttu-id="c4104-162">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="c4104-162">Required.</span></span> <span data-ttu-id="c4104-163">Azure AD-åtkomsttoken i formuläret **Bearer-token.** &lt;  &gt;</span><span class="sxs-lookup"><span data-stu-id="c4104-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="c4104-164">Begär parametrar</span><span class="sxs-lookup"><span data-stu-id="c4104-164">Request parameters</span></span>

<span data-ttu-id="c4104-165">Använd valfria frågeparametrar för att ange och styra mängden data som returneras i ett svar.</span><span class="sxs-lookup"><span data-stu-id="c4104-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="c4104-166">Om du anropar den här metoden utan parametrar innehåller svaret alla aviseringar i organisationen under de senaste 2 timmarna.</span><span class="sxs-lookup"><span data-stu-id="c4104-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="c4104-167">Namn</span><span class="sxs-lookup"><span data-stu-id="c4104-167">Name</span></span> | <span data-ttu-id="c4104-168">Värde</span><span class="sxs-lookup"><span data-stu-id="c4104-168">Value</span></span>| <span data-ttu-id="c4104-169">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4104-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="c4104-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="c4104-170">sinceTimeUtc</span></span> | <span data-ttu-id="c4104-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="c4104-171">DateTime</span></span> | <span data-ttu-id="c4104-172">Definierar att aviseringar med lägre tidsbunden tid hämtas från, baserat på fält:</span><span class="sxs-lookup"><span data-stu-id="c4104-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="c4104-173">Tidsperioden blir: fråntimeUtc-tid till aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="c4104-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="c4104-174">**Obs!** När det inte har angetts hämtas alla aviseringar som genererats de senaste två timmarna.</span><span class="sxs-lookup"><span data-stu-id="c4104-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="c4104-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="c4104-175">untilTimeUtc</span></span> | <span data-ttu-id="c4104-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="c4104-176">DateTime</span></span> | <span data-ttu-id="c4104-177">Definierar den övre tidsbundna aviseringarna hämtas.</span><span class="sxs-lookup"><span data-stu-id="c4104-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="c4104-178">Tidsperioden blir då och `sinceTimeUtc` `untilTimeUtc` då.</span><span class="sxs-lookup"><span data-stu-id="c4104-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="c4104-179">**Obs!** När det inte anges används den aktuella tiden som standardvärde.</span><span class="sxs-lookup"><span data-stu-id="c4104-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="c4104-180">sedan</span><span class="sxs-lookup"><span data-stu-id="c4104-180">ago</span></span> | <span data-ttu-id="c4104-181">sträng</span><span class="sxs-lookup"><span data-stu-id="c4104-181">string</span></span> | <span data-ttu-id="c4104-182">Hämtar aviseringar i följande tidsperiod: från `(current_time - ago)` tid till `current_time` tid.</span><span class="sxs-lookup"><span data-stu-id="c4104-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="c4104-183">Värdet ska anges i enlighet med **iso 8601-varaktighetsformatet**</span><span class="sxs-lookup"><span data-stu-id="c4104-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="c4104-184">Exempel: `ago=PT10M` hämtar aviseringar som tagits emot de senaste 10 minuterna.</span><span class="sxs-lookup"><span data-stu-id="c4104-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="c4104-185">gräns</span><span class="sxs-lookup"><span data-stu-id="c4104-185">limit</span></span> | <span data-ttu-id="c4104-186">int</span><span class="sxs-lookup"><span data-stu-id="c4104-186">int</span></span> | <span data-ttu-id="c4104-187">Definierar antalet aviseringar som ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="c4104-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="c4104-188">De senaste aviseringarna hämtas baserat på det definierade antalet.</span><span class="sxs-lookup"><span data-stu-id="c4104-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="c4104-189">**Obs!** När det inte anges hämtas alla aviseringar som finns tillgängliga inom tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="c4104-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="c4104-190">maskingrupper</span><span class="sxs-lookup"><span data-stu-id="c4104-190">machinegroups</span></span> | <span data-ttu-id="c4104-191">sträng</span><span class="sxs-lookup"><span data-stu-id="c4104-191">string</span></span> | <span data-ttu-id="c4104-192">Anger vilka enhetsgrupper som aviseringar ska hämta aviseringar från.</span><span class="sxs-lookup"><span data-stu-id="c4104-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="c4104-193">**Obs!** När det inte anges hämtas aviseringar från alla enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c4104-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="c4104-194">Exempel:</span><span class="sxs-lookup"><span data-stu-id="c4104-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="c4104-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="c4104-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="c4104-196">sträng</span><span class="sxs-lookup"><span data-stu-id="c4104-196">string</span></span> | <span data-ttu-id="c4104-197">En enstaka enhetstagg från registret.</span><span class="sxs-lookup"><span data-stu-id="c4104-197">Single device tag from the registry.</span></span>
<span data-ttu-id="c4104-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="c4104-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="c4104-199">sträng</span><span class="sxs-lookup"><span data-stu-id="c4104-199">string</span></span> | <span data-ttu-id="c4104-200">Enhetstaggar som har skapats i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="c4104-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="c4104-201">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="c4104-201">Request example</span></span>
<span data-ttu-id="c4104-202">I följande exempel visas hur du hämtar alla identifieringar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c4104-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="c4104-203">I följande exempel visas en begäran om att få de senaste 20 identifieringarna sedan 2016-09-12 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="c4104-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="c4104-204">Svar</span><span class="sxs-lookup"><span data-stu-id="c4104-204">Response</span></span>
<span data-ttu-id="c4104-205">Returvärdet är en matris med aviseringsobjekt i JSON-format.</span><span class="sxs-lookup"><span data-stu-id="c4104-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="c4104-206">Här är ett exempel på ett returvärde:</span><span class="sxs-lookup"><span data-stu-id="c4104-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="c4104-207">Kodexempel</span><span class="sxs-lookup"><span data-stu-id="c4104-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="c4104-208">Hämta åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="c4104-208">Get access token</span></span>
<span data-ttu-id="c4104-209">Följande kodexempel visar hur du hämtar en åtkomsttoken för att anropa Microsoft Defender för Endpoint SIEM API.</span><span class="sxs-lookup"><span data-stu-id="c4104-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="c4104-210">Använd token för att ansluta till identifieringsslutpunkten</span><span class="sxs-lookup"><span data-stu-id="c4104-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="c4104-211">Följande kodexempel visar hur du använder en åtkomsttoken för att anropa Defender för slutpunkt SIEM API för att få aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c4104-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="c4104-212">Felkoder</span><span class="sxs-lookup"><span data-stu-id="c4104-212">Error codes</span></span>
<span data-ttu-id="c4104-213">Microsoft Defender för slutpunkt REST API returnerar följande felkoder som orsakas av en ogiltig begäran.</span><span class="sxs-lookup"><span data-stu-id="c4104-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="c4104-214">HTTP-felkod</span><span class="sxs-lookup"><span data-stu-id="c4104-214">HTTP error code</span></span> | <span data-ttu-id="c4104-215">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4104-215">Description</span></span>
:---|:---
<span data-ttu-id="c4104-216">401</span><span class="sxs-lookup"><span data-stu-id="c4104-216">401</span></span> | <span data-ttu-id="c4104-217">Felaktig begäran eller ogiltig token.</span><span class="sxs-lookup"><span data-stu-id="c4104-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="c4104-218">403</span><span class="sxs-lookup"><span data-stu-id="c4104-218">403</span></span> | <span data-ttu-id="c4104-219">Obehörigt undantag – någon av domänerna hanteras inte av innehavaradministratören eller innehavartillståndet tas bort.</span><span class="sxs-lookup"><span data-stu-id="c4104-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="c4104-220">500</span><span class="sxs-lookup"><span data-stu-id="c4104-220">500</span></span> | <span data-ttu-id="c4104-221">Fel i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c4104-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4104-222">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c4104-222">Related topics</span></span>
- [<span data-ttu-id="c4104-223">Aktivera SIEM-integrering i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c4104-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="c4104-224">Konfigurera ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="c4104-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="c4104-225">Dra identifieringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="c4104-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="c4104-226">Fälten Microsoft Defender för identifiering av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c4104-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="c4104-227">Felsöka problem med SIEM-verktygsintegrering</span><span class="sxs-lookup"><span data-stu-id="c4104-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
