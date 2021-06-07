---
title: Använda känslighetsetiketter som villkor i DLP-principer
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: lära dig om tjänsterna och objekttyperna som du kan använda känslighetsetiketter som villkor i DLP-principer
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779849"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="1c446-103">Använda känslighetsetiketter som villkor i DLP-principer</span><span class="sxs-lookup"><span data-stu-id="1c446-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="1c446-104">Du kan använda [känslighetsetiketter](sensitivity-labels.md) som ett villkor i DLP-principerna för dessa platser:</span><span class="sxs-lookup"><span data-stu-id="1c446-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="1c446-105">E-postmeddelanden från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1c446-105">Exchange Online email messages</span></span>
- <span data-ttu-id="1c446-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c446-106">SharePoint Online</span></span>
- <span data-ttu-id="1c446-107">OneDrive för företag-webbplatser</span><span class="sxs-lookup"><span data-stu-id="1c446-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="1c446-108">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="1c446-108">Windows 10 devices</span></span>

<span data-ttu-id="1c446-109">Känslighetsetiketter visas som ett alternativ i listan **Innehåll innehåller**.</span><span class="sxs-lookup"><span data-stu-id="1c446-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1c446-110">![känslighetsetikett som ett villkor](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="1c446-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c446-111">**Känslighetsetiketter** som ett villkor är inte tillgängligt om du har markerat **Teams chatt- och kanalmeddelanden** som en plats för att tillämpa DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="1c446-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="1c446-112">Objekt, scenarier och principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="1c446-113">Du kan använda känslighetsetiketter som villkor för de här objekten och i dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="1c446-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="1c446-114">Objekt som stöds:</span><span class="sxs-lookup"><span data-stu-id="1c446-114">Supported items</span></span>

|<span data-ttu-id="1c446-115">Tjänst</span><span class="sxs-lookup"><span data-stu-id="1c446-115">Service</span></span>  |<span data-ttu-id="1c446-116">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="1c446-116">Item type</span></span>  |<span data-ttu-id="1c446-117">Tillgängligt för principtips</span><span class="sxs-lookup"><span data-stu-id="1c446-117">Available to policy tip</span></span>  |<span data-ttu-id="1c446-118">Verkställbar</span><span class="sxs-lookup"><span data-stu-id="1c446-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="1c446-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="1c446-119">Exchange</span></span>    |<span data-ttu-id="1c446-120">e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="1c446-120">email message</span></span>         |<span data-ttu-id="1c446-121">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-121">yes</span></span>         |<span data-ttu-id="1c446-122">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-122">yes</span></span>         |
|<span data-ttu-id="1c446-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="1c446-123">Exchange</span></span>    |<span data-ttu-id="1c446-124">e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="1c446-124">email attachment</span></span>         |<span data-ttu-id="1c446-125">nej</span><span class="sxs-lookup"><span data-stu-id="1c446-125">no</span></span>         |<span data-ttu-id="1c446-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="1c446-126">yes \*</span></span>         |
|<span data-ttu-id="1c446-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c446-127">SharePoint Online</span></span>     |<span data-ttu-id="1c446-128">object i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c446-128">items in SharePoint Online</span></span>         |<span data-ttu-id="1c446-129">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-129">yes</span></span>         |<span data-ttu-id="1c446-130">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-130">yes</span></span>         |
|<span data-ttu-id="1c446-131">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="1c446-131">OneDrive for Business</span></span>     |<span data-ttu-id="1c446-132">objekt</span><span class="sxs-lookup"><span data-stu-id="1c446-132">items</span></span>         |<span data-ttu-id="1c446-133">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-133">yes</span></span>         |<span data-ttu-id="1c446-134">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-134">yes</span></span>         |
|<span data-ttu-id="1c446-135">Teams</span><span class="sxs-lookup"><span data-stu-id="1c446-135">Teams</span></span>     |<span data-ttu-id="1c446-136">Teams och kanalmeddelanden</span><span class="sxs-lookup"><span data-stu-id="1c446-136">Teams and channel messages</span></span>         |<span data-ttu-id="1c446-137">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="1c446-137">not applicable</span></span>         |<span data-ttu-id="1c446-138">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="1c446-138">not applicable</span></span>         |
|<span data-ttu-id="1c446-139">Teams</span><span class="sxs-lookup"><span data-stu-id="1c446-139">Teams</span></span>     |<span data-ttu-id="1c446-140">bifogade filer</span><span class="sxs-lookup"><span data-stu-id="1c446-140">attachments</span></span>         |<span data-ttu-id="1c446-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="1c446-141">yes \*\*</span></span>         |<span data-ttu-id="1c446-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="1c446-142">yes \*\*</span></span>         |
|<span data-ttu-id="1c446-143">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="1c446-143">Windows 10 devices</span></span>     |<span data-ttu-id="1c446-144">objekt</span><span class="sxs-lookup"><span data-stu-id="1c446-144">items</span></span>         |<span data-ttu-id="1c446-145">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-145">yes</span></span>         |<span data-ttu-id="1c446-146">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-146">yes</span></span>         |
|<span data-ttu-id="1c446-147">MCAS (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="1c446-147">MCAS (preview)</span></span> |<span data-ttu-id="1c446-148">objekt</span><span class="sxs-lookup"><span data-stu-id="1c446-148">items</span></span>         |<span data-ttu-id="1c446-149">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-149">yes</span></span>         |<span data-ttu-id="1c446-150">ja</span><span class="sxs-lookup"><span data-stu-id="1c446-150">yes</span></span>         |

<span data-ttu-id="1c446-151">\* DLP-identifiering av e-postbilagor med känslighetsetiketter stöds endast för Office-filtyper.</span><span class="sxs-lookup"><span data-stu-id="1c446-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="1c446-152">\*\* Bifogade filer som skickas i Teams över 1:1 chatt eller kanaler laddas automatiskt upp till OneDrive för företag och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c446-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="1c446-153">Så om SharePoint Online eller OneDrive för företag ingår som platser i DLP-principen inkluderas etiketterade bifogade filer som skickas i Teams automatiskt inom ramen för detta villkor.</span><span class="sxs-lookup"><span data-stu-id="1c446-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="1c446-154">Teams som en plats behöver inte väljas i DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="1c446-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="1c446-155">DLP:ers möjlighet att identifiera känslighetsetiketter i SharePoint och OneDrive för företag är begränsad.</span><span class="sxs-lookup"><span data-stu-id="1c446-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="1c446-156">Mer information finns i [Aktivera känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="1c446-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="1c446-157">Scenarier som stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-157">Supported scenarios</span></span>

- <span data-ttu-id="1c446-158">DLP-administratören kan se en lista över alla känslighetsetiketter i klientorganisationen när de väljer att inkludera en eller flera känslighetsetiketter som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="1c446-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="1c446-159">Användningen av känslighetsetiketter som ett villkor stöds i alla arbetsbelastningar som anges i supportmatrisen ovan.</span><span class="sxs-lookup"><span data-stu-id="1c446-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="1c446-160">DLP-principtips kommer att fortsätta att visas över arbetsbelastningar (förutom Outlook Win32) för DLP-principer som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="1c446-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="1c446-161">Känslighetsetiketter visas också som en del av e-postmeddelandet för incidentrapporten om en DLP-princip med känslighetsetiketter matchas som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="1c446-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="1c446-162">Information om känslighetsetiketter visas också i granskningsloggen för DLP-regeln för en matchning av DLP-princip som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="1c446-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="1c446-163">Principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-163">Support policy tips</span></span>


|<span data-ttu-id="1c446-164">Arbetsbelastning</span><span class="sxs-lookup"><span data-stu-id="1c446-164">Workload</span></span>  |<span data-ttu-id="1c446-165">Principtips som stöds/inte stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="1c446-166">OWA</span><span class="sxs-lookup"><span data-stu-id="1c446-166">OWA</span></span> |    <span data-ttu-id="1c446-167">stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-167">supported</span></span>     |
|<span data-ttu-id="1c446-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="1c446-168">Outlook Win 32</span></span>    |  <span data-ttu-id="1c446-169">stöds inte</span><span class="sxs-lookup"><span data-stu-id="1c446-169">not supported</span></span>       |
|<span data-ttu-id="1c446-170">SharePoint</span><span class="sxs-lookup"><span data-stu-id="1c446-170">SharePoint</span></span>   |   <span data-ttu-id="1c446-171">stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-171">supported</span></span>      |
|<span data-ttu-id="1c446-172">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="1c446-172">OneDrive for Business</span></span>    |    <span data-ttu-id="1c446-173">stöds</span><span class="sxs-lookup"><span data-stu-id="1c446-173">supported</span></span>     |
|<span data-ttu-id="1c446-174">slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="1c446-174">endpoint devices</span></span>   |  <span data-ttu-id="1c446-175">stöds inte</span><span class="sxs-lookup"><span data-stu-id="1c446-175">not supported</span></span>       |
