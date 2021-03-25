---
title: Indikatorresurstyp
description: Ange entitetsinformation och definiera förfallotiden för indikatorn med Hjälp av Microsoft Defender för Slutpunkt.
keywords: apis, apis som stöds, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187315"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="963c0-104">Indikatorresurstyp</span><span class="sxs-lookup"><span data-stu-id="963c0-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="963c0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="963c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="963c0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="963c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="963c0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="963c0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="963c0-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="963c0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="963c0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="963c0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="963c0-110">Se motsvarande [indikatorsida](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) i portalen.</span><span class="sxs-lookup"><span data-stu-id="963c0-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="963c0-111">Metod</span><span class="sxs-lookup"><span data-stu-id="963c0-111">Method</span></span>|<span data-ttu-id="963c0-112">Returtyp</span><span class="sxs-lookup"><span data-stu-id="963c0-112">Return Type</span></span> |<span data-ttu-id="963c0-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="963c0-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="963c0-114">Listindikatorer</span><span class="sxs-lookup"><span data-stu-id="963c0-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="963c0-115">[Indikator](ti-indicator.md) Samling</span><span class="sxs-lookup"><span data-stu-id="963c0-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="963c0-116">Enheter [med listindikator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="963c0-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="963c0-117">Indikator för skicka</span><span class="sxs-lookup"><span data-stu-id="963c0-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="963c0-118">Indikator</span><span class="sxs-lookup"><span data-stu-id="963c0-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="963c0-119">Skicka eller uppdatera [indikator entitet.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="963c0-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="963c0-120">Importera indikatorer</span><span class="sxs-lookup"><span data-stu-id="963c0-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="963c0-121">[Indikator](ti-indicator.md) Samling</span><span class="sxs-lookup"><span data-stu-id="963c0-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="963c0-122">Skicka eller uppdatera [indikatorer.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="963c0-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="963c0-123">Ta bort-indikator</span><span class="sxs-lookup"><span data-stu-id="963c0-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="963c0-124">Inget innehåll</span><span class="sxs-lookup"><span data-stu-id="963c0-124">No Content</span></span> | <span data-ttu-id="963c0-125">Tar bort [indikator entitet.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="963c0-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="963c0-126">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="963c0-126">Properties</span></span>
<span data-ttu-id="963c0-127">Egenskap</span><span class="sxs-lookup"><span data-stu-id="963c0-127">Property</span></span> |  <span data-ttu-id="963c0-128">Skriv</span><span class="sxs-lookup"><span data-stu-id="963c0-128">Type</span></span>    |   <span data-ttu-id="963c0-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="963c0-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="963c0-130">id</span><span class="sxs-lookup"><span data-stu-id="963c0-130">id</span></span> | <span data-ttu-id="963c0-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-131">String</span></span> | <span data-ttu-id="963c0-132">Identiteten för [indikatorenheten.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="963c0-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="963c0-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="963c0-133">indicatorValue</span></span> | <span data-ttu-id="963c0-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-134">String</span></span> | <span data-ttu-id="963c0-135">Värdet på [indikatorn](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="963c0-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="963c0-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="963c0-136">indicatorType</span></span> | <span data-ttu-id="963c0-137">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="963c0-137">Enum</span></span> | <span data-ttu-id="963c0-138">Typ av indikator.</span><span class="sxs-lookup"><span data-stu-id="963c0-138">Type of the indicator.</span></span> <span data-ttu-id="963c0-139">Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url".</span><span class="sxs-lookup"><span data-stu-id="963c0-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="963c0-140">program</span><span class="sxs-lookup"><span data-stu-id="963c0-140">application</span></span> | <span data-ttu-id="963c0-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-141">String</span></span> | <span data-ttu-id="963c0-142">Programmet som är kopplat till indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="963c0-143">åtgärd</span><span class="sxs-lookup"><span data-stu-id="963c0-143">action</span></span> | <span data-ttu-id="963c0-144">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="963c0-144">Enum</span></span> | <span data-ttu-id="963c0-145">Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen.</span><span class="sxs-lookup"><span data-stu-id="963c0-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="963c0-146">Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet".</span><span class="sxs-lookup"><span data-stu-id="963c0-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="963c0-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="963c0-147">sourceType</span></span> | <span data-ttu-id="963c0-148">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="963c0-148">Enum</span></span> | <span data-ttu-id="963c0-149">"Användare" om indikatorn skapades av en användare (t.ex. från portalen), "AadApp" om den skickades med automatiserad ansökan via API:t.</span><span class="sxs-lookup"><span data-stu-id="963c0-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="963c0-150">källa</span><span class="sxs-lookup"><span data-stu-id="963c0-150">source</span></span> | <span data-ttu-id="963c0-151">sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-151">string</span></span> | <span data-ttu-id="963c0-152">Namnet på den användare/det program som skickade indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="963c0-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="963c0-153">createdBy</span></span> | <span data-ttu-id="963c0-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-154">String</span></span> | <span data-ttu-id="963c0-155">Unik identitet för användaren/programmet som skickade indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="963c0-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="963c0-156">lastUpdatedBy</span></span> | <span data-ttu-id="963c0-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-157">String</span></span> | <span data-ttu-id="963c0-158">Identiteten för den användare/det program som senast uppdaterade indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="963c0-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="963c0-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="963c0-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="963c0-160">DateTimeOffset</span></span> | <span data-ttu-id="963c0-161">Datum och tid då indikatorn skapades.</span><span class="sxs-lookup"><span data-stu-id="963c0-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="963c0-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="963c0-162">expirationTime</span></span> | <span data-ttu-id="963c0-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="963c0-163">DateTimeOffset</span></span> | <span data-ttu-id="963c0-164">Indikatorns utgångstid.</span><span class="sxs-lookup"><span data-stu-id="963c0-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="963c0-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="963c0-165">lastUpdateTime</span></span> | <span data-ttu-id="963c0-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="963c0-166">DateTimeOffset</span></span> | <span data-ttu-id="963c0-167">Den senaste gången indikatorn uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="963c0-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="963c0-168">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="963c0-168">severity</span></span> | <span data-ttu-id="963c0-169">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="963c0-169">Enum</span></span> | <span data-ttu-id="963c0-170">Indikatorns allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="963c0-170">The severity of the indicator.</span></span> <span data-ttu-id="963c0-171">Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="963c0-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="963c0-172">rubrik</span><span class="sxs-lookup"><span data-stu-id="963c0-172">title</span></span> | <span data-ttu-id="963c0-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-173">String</span></span> | <span data-ttu-id="963c0-174">Indikatorrubrik.</span><span class="sxs-lookup"><span data-stu-id="963c0-174">Indicator title.</span></span>
<span data-ttu-id="963c0-175">beskrivning</span><span class="sxs-lookup"><span data-stu-id="963c0-175">description</span></span> | <span data-ttu-id="963c0-176">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-176">String</span></span> | <span data-ttu-id="963c0-177">Beskrivning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-177">Description of the indicator.</span></span>
<span data-ttu-id="963c0-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="963c0-178">recommendedActions</span></span> | <span data-ttu-id="963c0-179">Sträng</span><span class="sxs-lookup"><span data-stu-id="963c0-179">String</span></span> | <span data-ttu-id="963c0-180">Rekommenderade åtgärder för indikatorn.</span><span class="sxs-lookup"><span data-stu-id="963c0-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="963c0-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="963c0-181">rbacGroupNames</span></span> | <span data-ttu-id="963c0-182">Lista med strängar</span><span class="sxs-lookup"><span data-stu-id="963c0-182">List of strings</span></span> | <span data-ttu-id="963c0-183">Gruppnamn på RBAC-enheter där indikatorn exponeras och är aktiv.</span><span class="sxs-lookup"><span data-stu-id="963c0-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="963c0-184">Tom lista om den exponeras för alla enheter.</span><span class="sxs-lookup"><span data-stu-id="963c0-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="963c0-185">Json-representation</span><span class="sxs-lookup"><span data-stu-id="963c0-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```