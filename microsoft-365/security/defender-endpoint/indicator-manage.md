---
title: Hantera indikatorer
ms.reviewer: ''
description: Hantera indikatorer för en filhash, IP-adress, URL:er eller domäner som definierar identifiering, skydd och undantag för enheter.
keywords: importera, indikator, lista, ioc, csv, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
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
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185951"
---
# <a name="manage-indicators"></a><span data-ttu-id="5e2b8-104">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="5e2b8-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5e2b8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="5e2b8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5e2b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5e2b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e2b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5e2b8-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5e2b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5e2b8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="5e2b8-110">Välj Ta fram Inställningar  >  **i navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="5e2b8-111">Välj fliken för den entitetstyp som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="5e2b8-112">Uppdatera information om indikatorn och klicka  **på Spara** eller klicka på knappen Ta bort om du vill ta bort entiteten från listan.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="5e2b8-113">Importera en lista med IoCs</span><span class="sxs-lookup"><span data-stu-id="5e2b8-113">Import a list of IoCs</span></span>

<span data-ttu-id="5e2b8-114">Du kan också välja att ladda upp en CSV-fil som definierar attribut för indikatorer, den åtgärd som ska vidtas och annan information.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="5e2b8-115">Ladda ned CSV-exemplet för att ta fram de kolumnattribut som stöds.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="5e2b8-116">Välj Ta fram Inställningar  >  **i navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="5e2b8-117">Välj fliken för den enhetstyp som du vill importera indikatorer för.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="5e2b8-118">Välj **Importera**  >  **välj fil**.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="5e2b8-119">Välj **Importera.**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-119">Select **Import**.</span></span> <span data-ttu-id="5e2b8-120">Gör så här för alla filer du vill importera.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="5e2b8-121">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-121">Select **Done**.</span></span>

<span data-ttu-id="5e2b8-122">I följande tabell visas de parametrar som stöds.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="5e2b8-123">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e2b8-123">Parameter</span></span> | <span data-ttu-id="5e2b8-124">Typ</span><span class="sxs-lookup"><span data-stu-id="5e2b8-124">Type</span></span>    |   <span data-ttu-id="5e2b8-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5e2b8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="5e2b8-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="5e2b8-126">indicatorType</span></span> | <span data-ttu-id="5e2b8-127">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="5e2b8-127">Enum</span></span> | <span data-ttu-id="5e2b8-128">Typ av indikator.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-128">Type of the indicator.</span></span> <span data-ttu-id="5e2b8-129">Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url".</span><span class="sxs-lookup"><span data-stu-id="5e2b8-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="5e2b8-130">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-130">**Required**</span></span>
<span data-ttu-id="5e2b8-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="5e2b8-131">indicatorValue</span></span> | <span data-ttu-id="5e2b8-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-132">String</span></span> | <span data-ttu-id="5e2b8-133">Identiteten för [indikatorenheten.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="5e2b8-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="5e2b8-134">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-134">**Required**</span></span>
<span data-ttu-id="5e2b8-135">åtgärd</span><span class="sxs-lookup"><span data-stu-id="5e2b8-135">action</span></span> | <span data-ttu-id="5e2b8-136">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="5e2b8-136">Enum</span></span> | <span data-ttu-id="5e2b8-137">Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="5e2b8-138">Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet".</span><span class="sxs-lookup"><span data-stu-id="5e2b8-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="5e2b8-139">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-139">**Required**</span></span>
<span data-ttu-id="5e2b8-140">rubrik</span><span class="sxs-lookup"><span data-stu-id="5e2b8-140">title</span></span> | <span data-ttu-id="5e2b8-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-141">String</span></span> | <span data-ttu-id="5e2b8-142">Indikatoraviseringens rubrik.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-142">Indicator alert title.</span></span> <span data-ttu-id="5e2b8-143">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-143">**Required**</span></span>
<span data-ttu-id="5e2b8-144">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5e2b8-144">description</span></span> | <span data-ttu-id="5e2b8-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-145">String</span></span> |  <span data-ttu-id="5e2b8-146">Beskrivning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-146">Description of the indicator.</span></span> <span data-ttu-id="5e2b8-147">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-147">**Required**</span></span>
<span data-ttu-id="5e2b8-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="5e2b8-148">expirationTime</span></span> | <span data-ttu-id="5e2b8-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5e2b8-149">DateTimeOffset</span></span> | <span data-ttu-id="5e2b8-150">Förfallodatum för indikatorn i följande format YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="5e2b8-151">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-151">**Optional**</span></span>
<span data-ttu-id="5e2b8-152">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="5e2b8-152">severity</span></span> | <span data-ttu-id="5e2b8-153">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="5e2b8-153">Enum</span></span> | <span data-ttu-id="5e2b8-154">Indikatorns allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-154">The severity of the indicator.</span></span> <span data-ttu-id="5e2b8-155">Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="5e2b8-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="5e2b8-156">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-156">**Optional**</span></span>
<span data-ttu-id="5e2b8-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="5e2b8-157">recommendedActions</span></span> | <span data-ttu-id="5e2b8-158">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-158">String</span></span> | <span data-ttu-id="5e2b8-159">Rekommenderade åtgärder för TI-indikatoraviseringar.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="5e2b8-160">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-160">**Optional**</span></span>
<span data-ttu-id="5e2b8-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="5e2b8-161">rbacGroupNames</span></span> | <span data-ttu-id="5e2b8-162">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-162">String</span></span> | <span data-ttu-id="5e2b8-163">Kommaavgränsade listor med namn på RBAC-grupper indikatorn skulle tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="5e2b8-164">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-164">**Optional**</span></span>
<span data-ttu-id="5e2b8-165">kategori</span><span class="sxs-lookup"><span data-stu-id="5e2b8-165">category</span></span> | <span data-ttu-id="5e2b8-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-166">String</span></span> | <span data-ttu-id="5e2b8-167">Kategorin för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-167">Category of the alert.</span></span> <span data-ttu-id="5e2b8-168">Några exempel: Åtkomst för körning och autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="5e2b8-169">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="5e2b8-169">**Optional**</span></span>
<span data-ttu-id="5e2b8-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="5e2b8-170">mitretechniques</span></span>| <span data-ttu-id="5e2b8-171">Sträng</span><span class="sxs-lookup"><span data-stu-id="5e2b8-171">String</span></span> | <span data-ttu-id="5e2b8-172">MITRE-tekniker, kod/id (kommaavgränsade).</span><span class="sxs-lookup"><span data-stu-id="5e2b8-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="5e2b8-173">Mer information finns i [Enterprise taktiker](https://attack.mitre.org/tactics/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="5e2b8-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="5e2b8-174">**Valfritt** Vi rekommenderar att du lägger till ett värde i kategori när du använder en MITRE-teknik.</span><span class="sxs-lookup"><span data-stu-id="5e2b8-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="5e2b8-175">Mer information finns i [Microsoft Defender för slutpunktsvarningskategorier](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)är nu i linje med MITRE ATT&CK! .</span><span class="sxs-lookup"><span data-stu-id="5e2b8-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="5e2b8-176">Se även</span><span class="sxs-lookup"><span data-stu-id="5e2b8-176">See also</span></span>
- [<span data-ttu-id="5e2b8-177">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="5e2b8-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="5e2b8-178">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="5e2b8-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="5e2b8-179">Skapa indikatorer för IP:er och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="5e2b8-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="5e2b8-180">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="5e2b8-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
