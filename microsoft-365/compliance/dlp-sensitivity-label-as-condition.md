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
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162748"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="d3c0e-103">Använda känslighetsetiketter som villkor i DLP-principer</span><span class="sxs-lookup"><span data-stu-id="d3c0e-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="d3c0e-104">Du kan använda [känslighetsetiketter](sensitivity-labels.md) som ett villkor i DLP-principerna för dessa platser:</span><span class="sxs-lookup"><span data-stu-id="d3c0e-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="d3c0e-105">E-postmeddelanden från Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3c0e-105">Exchange Online email messages</span></span>
- <span data-ttu-id="d3c0e-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3c0e-106">SharePoint Online</span></span>
- <span data-ttu-id="d3c0e-107">OneDrive för företag-webbplatser</span><span class="sxs-lookup"><span data-stu-id="d3c0e-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="d3c0e-108">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d3c0e-108">Windows 10 devices</span></span>

<span data-ttu-id="d3c0e-109">Känslighetsetiketter visas som ett alternativ i listan **Innehåll innehåller**.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3c0e-110">![känslighetsetikett som ett villkor](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="d3c0e-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3c0e-111">**Känslighetsetiketter** som ett villkor är inte tillgängligt om du har markerat **Teams chatt- och kanalmeddelanden** som en plats för att tillämpa DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="d3c0e-112">Objekt, scenarier och principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="d3c0e-113">Du kan använda känslighetsetiketter som villkor för de här objekten och i dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="d3c0e-114">Objekt som stöds:</span><span class="sxs-lookup"><span data-stu-id="d3c0e-114">Supported items</span></span>

|<span data-ttu-id="d3c0e-115">Tjänst</span><span class="sxs-lookup"><span data-stu-id="d3c0e-115">Service</span></span>  |<span data-ttu-id="d3c0e-116">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="d3c0e-116">Item type</span></span>  |<span data-ttu-id="d3c0e-117">Tillgängligt för principtips</span><span class="sxs-lookup"><span data-stu-id="d3c0e-117">Available to policy tip</span></span>  |<span data-ttu-id="d3c0e-118">Verkställbar</span><span class="sxs-lookup"><span data-stu-id="d3c0e-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d3c0e-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="d3c0e-119">Exchange</span></span>    |<span data-ttu-id="d3c0e-120">e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="d3c0e-120">email message</span></span>         |<span data-ttu-id="d3c0e-121">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-121">yes</span></span>         |<span data-ttu-id="d3c0e-122">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-122">yes</span></span>         |
|<span data-ttu-id="d3c0e-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="d3c0e-123">Exchange</span></span>    |<span data-ttu-id="d3c0e-124">e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="d3c0e-124">email attachment</span></span>         |<span data-ttu-id="d3c0e-125">nej \*</span><span class="sxs-lookup"><span data-stu-id="d3c0e-125">no \*</span></span>         |<span data-ttu-id="d3c0e-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="d3c0e-126">yes \*</span></span>         |
|<span data-ttu-id="d3c0e-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3c0e-127">SharePoint Online</span></span>     |<span data-ttu-id="d3c0e-128">object i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3c0e-128">items in SharePoint Online</span></span>         |<span data-ttu-id="d3c0e-129">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-129">yes</span></span>         |<span data-ttu-id="d3c0e-130">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-130">yes</span></span>         |
|<span data-ttu-id="d3c0e-131">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="d3c0e-131">OneDrive for Business</span></span>     |<span data-ttu-id="d3c0e-132">objekt</span><span class="sxs-lookup"><span data-stu-id="d3c0e-132">items</span></span>         |<span data-ttu-id="d3c0e-133">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-133">yes</span></span>         |<span data-ttu-id="d3c0e-134">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-134">yes</span></span>         |
|<span data-ttu-id="d3c0e-135">Teams</span><span class="sxs-lookup"><span data-stu-id="d3c0e-135">Teams</span></span>     |<span data-ttu-id="d3c0e-136">Teams och kanalmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d3c0e-136">Teams and channel messages</span></span>         |<span data-ttu-id="d3c0e-137">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="d3c0e-137">not applicable</span></span>         |<span data-ttu-id="d3c0e-138">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="d3c0e-138">not applicable</span></span>         |
|<span data-ttu-id="d3c0e-139">Teams</span><span class="sxs-lookup"><span data-stu-id="d3c0e-139">Teams</span></span>     |<span data-ttu-id="d3c0e-140">bifogade filer</span><span class="sxs-lookup"><span data-stu-id="d3c0e-140">attachments</span></span>         |<span data-ttu-id="d3c0e-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="d3c0e-141">yes \*\*</span></span>         |<span data-ttu-id="d3c0e-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="d3c0e-142">yes \*\*</span></span>         |
|<span data-ttu-id="d3c0e-143">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d3c0e-143">Windows 10 devices</span></span>     |<span data-ttu-id="d3c0e-144">objekt</span><span class="sxs-lookup"><span data-stu-id="d3c0e-144">items</span></span>         |<span data-ttu-id="d3c0e-145">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-145">yes</span></span>         |<span data-ttu-id="d3c0e-146">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-146">yes</span></span>         |
|<span data-ttu-id="d3c0e-147">MCAS (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d3c0e-147">MCAS (preview)</span></span> |<span data-ttu-id="d3c0e-148">objekt</span><span class="sxs-lookup"><span data-stu-id="d3c0e-148">items</span></span>         |<span data-ttu-id="d3c0e-149">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-149">yes</span></span>         |<span data-ttu-id="d3c0e-150">ja</span><span class="sxs-lookup"><span data-stu-id="d3c0e-150">yes</span></span>         |

<span data-ttu-id="d3c0e-151">\* DLP-identifiering och tillämpning av känslighetsetiketter för e-postmeddelanden och bilagor stöds under överföringen.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="d3c0e-152">Det är inte DLP-principtips för känslighetsetiketter för e-postbilagor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="d3c0e-153">\*\* Bifogade filer som skickas i Teams över 1:1 chatt eller kanaler laddas automatiskt upp till OneDrive för företag och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="d3c0e-154">Så om SharePoint Online eller OneDrive för företag ingår som platser i DLP-principen inkluderas etiketterade bifogade filer som skickas i Teams automatiskt inom ramen för detta villkor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="d3c0e-155">Teams som en plats behöver inte väljas i DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="d3c0e-156">Scenarier som stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-156">Supported scenarios</span></span>

- <span data-ttu-id="d3c0e-157">DLP-administratören kan se en lista över alla känslighetsetiketter i klientorganisationen när de väljer att inkludera en eller flera känslighetsetiketter som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="d3c0e-158">Användningen av känslighetsetiketter som ett villkor stöds i alla arbetsbelastningar som anges i supportmatrisen ovan.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="d3c0e-159">DLP-principtips kommer att fortsätta att visas över arbetsbelastningar (förutom Outlook Win32) för DLP-principer som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="d3c0e-160">Känslighetsetiketter visas också som en del av e-postmeddelandet för incidentrapporten om en DLP-princip med känslighetsetiketter matchas som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="d3c0e-161">Information om känslighetsetiketter visas också i granskningsloggen för DLP-regeln för en matchning av DLP-princip som innehåller känslighetsetiketten som ett villkor.</span><span class="sxs-lookup"><span data-stu-id="d3c0e-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="d3c0e-162">Principtips som stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-162">Support policy tips</span></span>


|<span data-ttu-id="d3c0e-163">Arbetsbelastning</span><span class="sxs-lookup"><span data-stu-id="d3c0e-163">Workload</span></span>  |<span data-ttu-id="d3c0e-164">Principtips som stöds/inte stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="d3c0e-165">OWA</span><span class="sxs-lookup"><span data-stu-id="d3c0e-165">OWA</span></span> |    <span data-ttu-id="d3c0e-166">stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-166">supported</span></span>     |
|<span data-ttu-id="d3c0e-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="d3c0e-167">Outlook Win 32</span></span>    |  <span data-ttu-id="d3c0e-168">stöds inte</span><span class="sxs-lookup"><span data-stu-id="d3c0e-168">not supported</span></span>       |
|<span data-ttu-id="d3c0e-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d3c0e-169">SharePoint</span></span>   |   <span data-ttu-id="d3c0e-170">stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-170">supported</span></span>      |
|<span data-ttu-id="d3c0e-171">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="d3c0e-171">OneDrive for Business</span></span>    |    <span data-ttu-id="d3c0e-172">stöds</span><span class="sxs-lookup"><span data-stu-id="d3c0e-172">supported</span></span>     |
|<span data-ttu-id="d3c0e-173">slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="d3c0e-173">endpoint devices</span></span>   |  <span data-ttu-id="d3c0e-174">stöds inte</span><span class="sxs-lookup"><span data-stu-id="d3c0e-174">not supported</span></span>       |
