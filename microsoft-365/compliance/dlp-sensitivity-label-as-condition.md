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
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651098"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="82dec-103">Använda känslighetsetiketter som villkor i DLP-principer</span><span class="sxs-lookup"><span data-stu-id="82dec-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="82dec-104">Du kan använda [känslighetsetiketter](sensitivity-labels.md) som ett villkor i DLP-principerna för dessa platser:</span><span class="sxs-lookup"><span data-stu-id="82dec-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="82dec-105">E-postmeddelanden från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="82dec-105">Exchange Online email messages</span></span>
- <span data-ttu-id="82dec-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="82dec-106">SharePoint Online</span></span>
- <span data-ttu-id="82dec-107">OneDrive för företag-webbplatser</span><span class="sxs-lookup"><span data-stu-id="82dec-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="82dec-108">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="82dec-108">Windows 10 devices</span></span>

<span data-ttu-id="82dec-109">Känslighetsetiketter visas som ett alternativ i listan **Innehåll innehåller**.</span><span class="sxs-lookup"><span data-stu-id="82dec-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="82dec-110">![känslighetsetikett som ett villkor](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="82dec-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82dec-111">**Känslighetsetiketter** som ett villkor är inte tillgängligt om du har markerat **Teams chatt- och kanalmeddelanden** som en plats för att tillämpa DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="82dec-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="82dec-112">Objekt, scenarier och principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="82dec-113">Du kan använda känslighetsetiketter som villkor för de här objekten och i dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="82dec-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="82dec-114">Objekt som stöds:</span><span class="sxs-lookup"><span data-stu-id="82dec-114">Supported items</span></span>

|<span data-ttu-id="82dec-115">Tjänst</span><span class="sxs-lookup"><span data-stu-id="82dec-115">Service</span></span>  |<span data-ttu-id="82dec-116">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="82dec-116">Item type</span></span>  |<span data-ttu-id="82dec-117">Tillgängligt för principtips</span><span class="sxs-lookup"><span data-stu-id="82dec-117">Available to policy tip</span></span>  |<span data-ttu-id="82dec-118">Verkställbar</span><span class="sxs-lookup"><span data-stu-id="82dec-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="82dec-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="82dec-119">Exchange</span></span>    |<span data-ttu-id="82dec-120">e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="82dec-120">email message</span></span>         |<span data-ttu-id="82dec-121">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-121">yes</span></span>         |<span data-ttu-id="82dec-122">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-122">yes</span></span>         |
|<span data-ttu-id="82dec-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="82dec-123">Exchange</span></span>    |<span data-ttu-id="82dec-124">e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="82dec-124">email attachment</span></span>         |<span data-ttu-id="82dec-125">nej</span><span class="sxs-lookup"><span data-stu-id="82dec-125">no</span></span>         |<span data-ttu-id="82dec-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="82dec-126">yes \*</span></span>         |
|<span data-ttu-id="82dec-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="82dec-127">SharePoint Online</span></span>     |<span data-ttu-id="82dec-128">object i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="82dec-128">items in SharePoint Online</span></span>         |<span data-ttu-id="82dec-129">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-129">yes</span></span>         |<span data-ttu-id="82dec-130">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-130">yes</span></span>         |
|<span data-ttu-id="82dec-131">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="82dec-131">OneDrive for Business</span></span>     |<span data-ttu-id="82dec-132">objekt</span><span class="sxs-lookup"><span data-stu-id="82dec-132">items</span></span>         |<span data-ttu-id="82dec-133">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-133">yes</span></span>         |<span data-ttu-id="82dec-134">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-134">yes</span></span>         |
|<span data-ttu-id="82dec-135">Teams</span><span class="sxs-lookup"><span data-stu-id="82dec-135">Teams</span></span>     |<span data-ttu-id="82dec-136">Teams och kanalmeddelanden</span><span class="sxs-lookup"><span data-stu-id="82dec-136">Teams and channel messages</span></span>         |<span data-ttu-id="82dec-137">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="82dec-137">not applicable</span></span>         |<span data-ttu-id="82dec-138">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="82dec-138">not applicable</span></span>         |
|<span data-ttu-id="82dec-139">Teams</span><span class="sxs-lookup"><span data-stu-id="82dec-139">Teams</span></span>     |<span data-ttu-id="82dec-140">bifogade filer</span><span class="sxs-lookup"><span data-stu-id="82dec-140">attachments</span></span>         |<span data-ttu-id="82dec-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="82dec-141">yes \*\*</span></span>         |<span data-ttu-id="82dec-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="82dec-142">yes \*\*</span></span>         |
|<span data-ttu-id="82dec-143">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="82dec-143">Windows 10 devices</span></span>     |<span data-ttu-id="82dec-144">objekt</span><span class="sxs-lookup"><span data-stu-id="82dec-144">items</span></span>         |<span data-ttu-id="82dec-145">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-145">yes</span></span>         |<span data-ttu-id="82dec-146">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-146">yes</span></span>         |
|<span data-ttu-id="82dec-147">MCAS (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="82dec-147">MCAS (preview)</span></span> |<span data-ttu-id="82dec-148">objekt</span><span class="sxs-lookup"><span data-stu-id="82dec-148">items</span></span>         |<span data-ttu-id="82dec-149">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-149">yes</span></span>         |<span data-ttu-id="82dec-150">ja</span><span class="sxs-lookup"><span data-stu-id="82dec-150">yes</span></span>         |

<span data-ttu-id="82dec-151">\* DLP-identifiering av e-postbilagor med känslighetsetiketter stöds endast för Office-filtyper.</span><span class="sxs-lookup"><span data-stu-id="82dec-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="82dec-152">\*\* Bifogade filer som skickas i Teams över 1:1 chatt eller kanaler laddas automatiskt upp till OneDrive för företag och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="82dec-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="82dec-153">Så om SharePoint Online eller OneDrive för företag ingår som platser i DLP-principen inkluderas etiketterade bifogade filer som skickas i Teams automatiskt inom ramen för detta villkor.</span><span class="sxs-lookup"><span data-stu-id="82dec-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="82dec-154">Teams som en plats behöver inte väljas i DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="82dec-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="82dec-155">Scenarier som stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-155">Supported scenarios</span></span>

- <span data-ttu-id="82dec-156">DLP-administratören kan se en lista över alla känslighetsetiketter i klientorganisationen när de väljer att inkludera en eller flera känslighetsetiketter som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="82dec-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="82dec-157">Användningen av känslighetsetiketter som ett villkor stöds i alla arbetsbelastningar som anges i supportmatrisen ovan.</span><span class="sxs-lookup"><span data-stu-id="82dec-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="82dec-158">DLP-principtips kommer att fortsätta att visas över arbetsbelastningar (förutom Outlook Win32) för DLP-principer som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="82dec-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="82dec-159">Känslighetsetiketter visas också som en del av e-postmeddelandet för incidentrapporten om en DLP-princip med känslighetsetiketter matchas som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="82dec-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="82dec-160">Information om känslighetsetiketter visas också i granskningsloggen för DLP-regeln för en matchning av DLP-princip som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="82dec-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="82dec-161">Principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-161">Support policy tips</span></span>


|<span data-ttu-id="82dec-162">Arbetsbelastning</span><span class="sxs-lookup"><span data-stu-id="82dec-162">Workload</span></span>  |<span data-ttu-id="82dec-163">Principtips som stöds/inte stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="82dec-164">OWA</span><span class="sxs-lookup"><span data-stu-id="82dec-164">OWA</span></span> |    <span data-ttu-id="82dec-165">stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-165">supported</span></span>     |
|<span data-ttu-id="82dec-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="82dec-166">Outlook Win 32</span></span>    |  <span data-ttu-id="82dec-167">stöds inte</span><span class="sxs-lookup"><span data-stu-id="82dec-167">not supported</span></span>       |
|<span data-ttu-id="82dec-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="82dec-168">SharePoint</span></span>   |   <span data-ttu-id="82dec-169">stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-169">supported</span></span>      |
|<span data-ttu-id="82dec-170">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="82dec-170">OneDrive for Business</span></span>    |    <span data-ttu-id="82dec-171">stöds</span><span class="sxs-lookup"><span data-stu-id="82dec-171">supported</span></span>     |
|<span data-ttu-id="82dec-172">slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="82dec-172">endpoint devices</span></span>   |  <span data-ttu-id="82dec-173">stöds inte</span><span class="sxs-lookup"><span data-stu-id="82dec-173">not supported</span></span>       |
