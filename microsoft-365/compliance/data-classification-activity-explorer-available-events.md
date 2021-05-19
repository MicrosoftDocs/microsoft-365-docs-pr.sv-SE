---
title: Etikettering av åtgärder som rapporterats i Utforskaren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: en lista med etiketter för aktiviteter som är tillgängliga i aktivitetsutforskaren.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532260"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="142d9-103">Märka aktiviteter som är tillgängliga i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="142d9-104">Känslighetsetikett används</span><span class="sxs-lookup"><span data-stu-id="142d9-104">Sensitivity label applied</span></span>

<span data-ttu-id="142d9-105">Den här händelsen genereras varje gång ett dokument utan etikett sätts i etiketter eller ett e-postmeddelande skickas med en känslighetsetikett.</span><span class="sxs-lookup"><span data-stu-id="142d9-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="142d9-106">Den fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="142d9-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="142d9-107">Den fångas när den förekommer i Azure Information Protection-tillägg.</span><span class="sxs-lookup"><span data-stu-id="142d9-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="142d9-108">Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.</span><span class="sxs-lookup"><span data-stu-id="142d9-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="142d9-109">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-109">Source</span></span>  |<span data-ttu-id="142d9-110">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-110">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-111">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="142d9-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="142d9-113">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-113">yes</span></span> |
|<span data-ttu-id="142d9-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-114">Outlook</span></span>| <span data-ttu-id="142d9-115">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-115">yes</span></span> |<span data-ttu-id="142d9-116">från Win 32</span><span class="sxs-lookup"><span data-stu-id="142d9-116">from Win 32</span></span> |
|<span data-ttu-id="142d9-117">SharePoint online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="142d9-118">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-118">yes</span></span> | |
|<span data-ttu-id="142d9-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-119">Exchange</span></span>        |<span data-ttu-id="142d9-120">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-120">yes</span></span>         | |
|<span data-ttu-id="142d9-121">Enhetlig klient och enhetlig AIP-skanner i Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="142d9-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="142d9-122">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-122">yes</span></span> |<span data-ttu-id="142d9-123">Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="142d9-124">Microsoft information protection (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="142d9-125">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-125">yes</span></span>|<span data-ttu-id="142d9-126">Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="142d9-127">RMS (Rights Management Service)</span><span class="sxs-lookup"><span data-stu-id="142d9-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="142d9-128">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-128">not applicable</span></span>         | |
|<span data-ttu-id="142d9-129">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-129">Power BI desktop and web</span></span>        | <span data-ttu-id="142d9-130">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-130">no</span></span>| <span data-ttu-id="142d9-131">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="142d9-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="142d9-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="142d9-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="142d9-133">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="142d9-134">Känslighetsetikett har ändrats</span><span class="sxs-lookup"><span data-stu-id="142d9-134">Sensitivity label changed</span></span>

<span data-ttu-id="142d9-135">Den här händelsen genereras varje gång en känslighetsetikett uppdateras i dokumentet eller e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="142d9-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="142d9-136">För källorna AIP Unified Client, Unified Scanner och  MIP SDK har AIP-uppgraderingsetiketten och nedgraderingsetikettsmapparna till aktivitetsutforskaren *ändrats* </span><span class="sxs-lookup"><span data-stu-id="142d9-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="142d9-137">Den fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="142d9-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="142d9-138">Händelsen fångas när det inträffar i Azure Information Protection Unified Client-tillägg och tvingande skannrar</span><span class="sxs-lookup"><span data-stu-id="142d9-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="142d9-139">Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.</span><span class="sxs-lookup"><span data-stu-id="142d9-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="142d9-140">*Justeringstexten* förs också in utom för justering SharePoint Online och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="142d9-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="142d9-141">Känslighetsetiketter som utförs i Office inbyggda appar på Outlook samlar in den senaste åtgärden som skapades innan åtgärder för att spara/skicka filer/e-post.</span><span class="sxs-lookup"><span data-stu-id="142d9-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="142d9-142">Om användaren till exempel ändrar etikett i ett e-postmeddelande flera gånger innan det skickas fångas den sista etiketten på e-postmeddelandet när det skickas i granskningsloggen och rapporteras sedan i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="142d9-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="142d9-143">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-143">Source</span></span>  |<span data-ttu-id="142d9-144">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-144">Reported in activity explorer</span></span>|<span data-ttu-id="142d9-145">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-147">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-147">yes</span></span>         |
|<span data-ttu-id="142d9-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-148">Outlook</span></span>         |<span data-ttu-id="142d9-149">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-149">yes</span></span>         |<span data-ttu-id="142d9-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="142d9-150">Win 32</span></span>|
|<span data-ttu-id="142d9-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-152">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-152">yes</span></span>         |
|<span data-ttu-id="142d9-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-153">Exchange</span></span>         |<span data-ttu-id="142d9-154">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-154">yes</span></span>         |
|<span data-ttu-id="142d9-155">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-155">AIP unified client</span></span>         |<span data-ttu-id="142d9-156">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-156">yes</span></span>         |
|<span data-ttu-id="142d9-157">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-157">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-158">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-158">yes</span></span>         |
|<span data-ttu-id="142d9-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-159">MIP SDK</span></span>         |<span data-ttu-id="142d9-160">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-160">yes</span></span>         |
|<span data-ttu-id="142d9-161">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-161">RMS service</span></span>         |<span data-ttu-id="142d9-162">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-162">not applicable</span></span>         |
|<span data-ttu-id="142d9-163">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-164">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-164">no</span></span>         |<span data-ttu-id="142d9-165">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="142d9-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="142d9-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-166">MCAS</span></span>     |<span data-ttu-id="142d9-167">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="142d9-168">Känslighetsetikett borttagen</span><span class="sxs-lookup"><span data-stu-id="142d9-168">Sensitivity label removed</span></span>

<span data-ttu-id="142d9-169">Den här händelsen genereras varje gång en känslighetsetikett tas bort från en fil eller ett dokument.</span><span class="sxs-lookup"><span data-stu-id="142d9-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="142d9-170">Händelsen fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="142d9-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="142d9-171">Den fångas när den förekommer i Azure Information Protection-tillägg.</span><span class="sxs-lookup"><span data-stu-id="142d9-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="142d9-172">Känslighetsetiketter, med Office inbyggd MIP-etikett, på Outlook samlar in den senaste händelsen med etiketter som skapades innan åtgärderna spara/skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="142d9-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="142d9-173">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-173">Source</span></span>  |<span data-ttu-id="142d9-174">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-174">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-175">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-177">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-177">yes</span></span>         |
|<span data-ttu-id="142d9-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-178">Outlook</span></span>         |<span data-ttu-id="142d9-179">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-179">yes</span></span>         |<span data-ttu-id="142d9-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="142d9-180">Win 32</span></span>|
|<span data-ttu-id="142d9-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-182">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-182">yes</span></span>         |
|<span data-ttu-id="142d9-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-183">Exchange</span></span>         |<span data-ttu-id="142d9-184">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-184">yes</span></span>         |
|<span data-ttu-id="142d9-185">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-185">AIP unified client</span></span>         |<span data-ttu-id="142d9-186">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-186">yes</span></span>         |<span data-ttu-id="142d9-187">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-188">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-188">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-189">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-189">yes</span></span>         |<span data-ttu-id="142d9-190">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="142d9-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-191">MIP SDK</span></span>         |<span data-ttu-id="142d9-192">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-192">yes</span></span>         |<span data-ttu-id="142d9-193">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="142d9-194">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-194">RMS service</span></span>         |<span data-ttu-id="142d9-195">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-195">not applicable</span></span>         |
|<span data-ttu-id="142d9-196">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-197">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-197">no</span></span>         |<span data-ttu-id="142d9-198">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="142d9-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="142d9-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-199">MCAS</span></span>     |<span data-ttu-id="142d9-200">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="142d9-201">Känslighetsetikettsfil läst</span><span class="sxs-lookup"><span data-stu-id="142d9-201">Sensitivity label file read</span></span>

<span data-ttu-id="142d9-202">Den här händelsen genereras varje gång ett känslighetsetiketterat eller skyddat dokument öppnas.</span><span class="sxs-lookup"><span data-stu-id="142d9-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="142d9-203">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-203">Source</span></span>  |<span data-ttu-id="142d9-204">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-204">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-205">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-207">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-207">yes</span></span>         |
|<span data-ttu-id="142d9-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-208">Outlook</span></span>         |<span data-ttu-id="142d9-209">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-209">no</span></span>         |
|<span data-ttu-id="142d9-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-211">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-211">no</span></span>         |
|<span data-ttu-id="142d9-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-212">Exchange</span></span>         |<span data-ttu-id="142d9-213">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-213">no</span></span>         |
|<span data-ttu-id="142d9-214">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-214">AIP unified client</span></span>         |<span data-ttu-id="142d9-215">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-215">yes</span></span>         |<span data-ttu-id="142d9-216">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-217">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-217">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-218">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-218">yes</span></span>         |<span data-ttu-id="142d9-219">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-220">MIP SDK</span></span>         |<span data-ttu-id="142d9-221">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-221">yes</span></span>         |<span data-ttu-id="142d9-222">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-223">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-223">RMS service</span></span>         |<span data-ttu-id="142d9-224">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-224">yes</span></span>         |<span data-ttu-id="142d9-225">*Åtkomståtgärden* är mappad till *filläsningsåtgärden* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="142d9-226">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-227">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-227">no</span></span>         |<span data-ttu-id="142d9-228">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="142d9-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="142d9-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-229">MCAS</span></span>     |<span data-ttu-id="142d9-230">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="142d9-231">Upptäckta filer</span><span class="sxs-lookup"><span data-stu-id="142d9-231">Files discovered</span></span>

<span data-ttu-id="142d9-232">Händelsen genereras varje gång filer upptäcks när AIP-skanner används för att skanna känsliga data på olika platser och hittar filer.</span><span class="sxs-lookup"><span data-stu-id="142d9-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="142d9-233">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-233">Source</span></span>  |<span data-ttu-id="142d9-234">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-234">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-235">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-237">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-237">not applicable</span></span>         |
|<span data-ttu-id="142d9-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-238">Outlook</span></span>         |<span data-ttu-id="142d9-239">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-239">not applicable</span></span>         |
|<span data-ttu-id="142d9-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-241">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-241">not applicable</span></span>         |
|<span data-ttu-id="142d9-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-242">Exchange</span></span>         |<span data-ttu-id="142d9-243">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-243">not applicable</span></span>         |
|<span data-ttu-id="142d9-244">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-244">AIP unified client</span></span>         |<span data-ttu-id="142d9-245">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-245">not applicable</span></span>       |
|<span data-ttu-id="142d9-246">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-246">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-247">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-247">yes</span></span>         |<span data-ttu-id="142d9-248">Åtgärden för *AIP-identifiering* mappas till de filer som *identifierats i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-249">MIP SDK</span></span>         |<span data-ttu-id="142d9-250">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-250">yes</span></span>         |<span data-ttu-id="142d9-251">Åtgärden för att *identifiera AIP* mappas till den fil *som identifierats* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="142d9-252">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-252">RMS service</span></span>         |<span data-ttu-id="142d9-253">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-253">not applicable</span></span>         |
|<span data-ttu-id="142d9-254">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-255">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-255">not applicable</span></span>         |
|<span data-ttu-id="142d9-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-256">MCAS</span></span>     |<span data-ttu-id="142d9-257">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="142d9-258">Känslighetsetikettsfil har bytt namn</span><span class="sxs-lookup"><span data-stu-id="142d9-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="142d9-259">Den här händelsen genereras varje gång ett dokument med en känslighetsetikett byter namn.</span><span class="sxs-lookup"><span data-stu-id="142d9-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="142d9-260">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-260">Source</span></span>  | <span data-ttu-id="142d9-261">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-261">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-262">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-264">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-264">yes</span></span>         |
|<span data-ttu-id="142d9-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-265">Outlook</span></span>         |<span data-ttu-id="142d9-266">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-266">not applicable</span></span>         |
|<span data-ttu-id="142d9-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-268">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-268">no</span></span>        |
|<span data-ttu-id="142d9-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-269">Exchange</span></span>         |<span data-ttu-id="142d9-270">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-270">not applicable</span></span>         |
|<span data-ttu-id="142d9-271">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-271">AIP unified client</span></span>         |<span data-ttu-id="142d9-272">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-272">no</span></span>         |
|<span data-ttu-id="142d9-273">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-273">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-274">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-274">no</span></span>         |
|<span data-ttu-id="142d9-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-275">MIP SDK</span></span>         |<span data-ttu-id="142d9-276">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-276">no</span></span>         |
|<span data-ttu-id="142d9-277">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-277">RMS service</span></span>         |<span data-ttu-id="142d9-278">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-278">no</span></span>      |
|<span data-ttu-id="142d9-279">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-280">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-280">no</span></span>         |
|<span data-ttu-id="142d9-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-281">MCAS</span></span>     |<span data-ttu-id="142d9-282">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="142d9-283">Filen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="142d9-283">File removed</span></span>

<span data-ttu-id="142d9-284">Händelsen genereras varje gång AIP-skannern upptäcker att en tidigare skannad fil har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="142d9-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="142d9-285">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-285">Source</span></span>  |<span data-ttu-id="142d9-286">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-286">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-287">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-289">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-289">not applicable</span></span>         |
|<span data-ttu-id="142d9-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-290">Outlook</span></span>         |<span data-ttu-id="142d9-291">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-291">not applicable</span></span>         |
|<span data-ttu-id="142d9-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-293">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-293">not applicable</span></span>           |
|<span data-ttu-id="142d9-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-294">Exchange</span></span>         |<span data-ttu-id="142d9-295">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-295">not applicable</span></span>         |
|<span data-ttu-id="142d9-296">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-296">AIP unified client</span></span>         |<span data-ttu-id="142d9-297">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-297">not applicable</span></span>            |
|<span data-ttu-id="142d9-298">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-298">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-299">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-299">yes</span></span>         |
|<span data-ttu-id="142d9-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-300">MIP SDK</span></span>         |<span data-ttu-id="142d9-301">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-301">not applicable</span></span>            |
|<span data-ttu-id="142d9-302">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-302">RMS service</span></span>         |<span data-ttu-id="142d9-303">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-303">not applicable</span></span>         |
|<span data-ttu-id="142d9-304">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-305">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-305">not applicable</span></span>  |
|<span data-ttu-id="142d9-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-306">MCAS</span></span>     |<span data-ttu-id="142d9-307">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="142d9-308">Skydd tillämpat</span><span class="sxs-lookup"><span data-stu-id="142d9-308">Protection applied</span></span>

<span data-ttu-id="142d9-309">Den här händelsen genereras första gången skydd läggs till manuellt för ett objekt som inte har en etikett.</span><span class="sxs-lookup"><span data-stu-id="142d9-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="142d9-310">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-310">Source</span></span>  |<span data-ttu-id="142d9-311">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-311">Reported in activity explorer</span></span> | <span data-ttu-id="142d9-312">Obs!</span><span class="sxs-lookup"><span data-stu-id="142d9-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="142d9-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-314">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-314">no</span></span>         |
|<span data-ttu-id="142d9-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-315">Outlook</span></span>         |<span data-ttu-id="142d9-316">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-316">no</span></span>         |
|<span data-ttu-id="142d9-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-318">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-318">not applicable</span></span>           |
|<span data-ttu-id="142d9-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-319">Exchange</span></span>         |<span data-ttu-id="142d9-320">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-320">no</span></span>       |
|<span data-ttu-id="142d9-321">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-321">AIP unified client</span></span>         |<span data-ttu-id="142d9-322">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-322">yes</span></span>            |
|<span data-ttu-id="142d9-323">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-323">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-324">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-324">not applicable</span></span>         |
|<span data-ttu-id="142d9-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-325">MIP SDK</span></span>         |<span data-ttu-id="142d9-326">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-326">yes</span></span>            |
|<span data-ttu-id="142d9-327">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-327">RMS service</span></span>         |<span data-ttu-id="142d9-328">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-328">not applicable</span></span>         |
|<span data-ttu-id="142d9-329">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-330">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-330">not applicable</span></span>            |
|<span data-ttu-id="142d9-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-331">MCAS</span></span>     |<span data-ttu-id="142d9-332">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="142d9-333">Skydd har ändrats</span><span class="sxs-lookup"><span data-stu-id="142d9-333">Protection changed</span></span>

<span data-ttu-id="142d9-334">Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.</span><span class="sxs-lookup"><span data-stu-id="142d9-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="142d9-335">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-335">Source</span></span>  |<span data-ttu-id="142d9-336">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-338">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-338">no</span></span>         |
|<span data-ttu-id="142d9-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-339">Outlook</span></span>         |<span data-ttu-id="142d9-340">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-340">no</span></span>         |
|<span data-ttu-id="142d9-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-342">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-342">not applicable</span></span>           |
|<span data-ttu-id="142d9-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-343">Exchange</span></span>         |<span data-ttu-id="142d9-344">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-344">no</span></span>       |
|<span data-ttu-id="142d9-345">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-345">AIP unified client</span></span>         |<span data-ttu-id="142d9-346">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-346">yes</span></span>            |
|<span data-ttu-id="142d9-347">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-347">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-348">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-348">not applicable</span></span>         |
|<span data-ttu-id="142d9-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-349">MIP SDK</span></span>         |<span data-ttu-id="142d9-350">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-350">yes</span></span>            |
|<span data-ttu-id="142d9-351">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-351">RMS service</span></span>         |<span data-ttu-id="142d9-352">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-352">not applicable</span></span>         |
|<span data-ttu-id="142d9-353">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-354">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-354">not applicable</span></span>            |
|<span data-ttu-id="142d9-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-355">MCAS</span></span>     |<span data-ttu-id="142d9-356">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="142d9-357">Skydd har tagits bort</span><span class="sxs-lookup"><span data-stu-id="142d9-357">Protection removed</span></span>

<span data-ttu-id="142d9-358">Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.</span><span class="sxs-lookup"><span data-stu-id="142d9-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="142d9-359">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-359">Source</span></span>  |<span data-ttu-id="142d9-360">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="142d9-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="142d9-362">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-362">no</span></span>         |
|<span data-ttu-id="142d9-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="142d9-363">Outlook</span></span>         |<span data-ttu-id="142d9-364">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-364">no</span></span>         |
|<span data-ttu-id="142d9-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="142d9-366">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-366">not applicable</span></span>           |
|<span data-ttu-id="142d9-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-367">Exchange</span></span>         |<span data-ttu-id="142d9-368">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-368">no</span></span>       |
|<span data-ttu-id="142d9-369">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="142d9-369">AIP unified client</span></span>         |<span data-ttu-id="142d9-370">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-370">yes</span></span>            |
|<span data-ttu-id="142d9-371">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="142d9-371">AIP unified scanner</span></span>         |<span data-ttu-id="142d9-372">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-372">not applicable</span></span>         |
|<span data-ttu-id="142d9-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="142d9-373">MIP SDK</span></span>         |<span data-ttu-id="142d9-374">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-374">yes</span></span>            |
|<span data-ttu-id="142d9-375">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="142d9-375">RMS service</span></span>         |<span data-ttu-id="142d9-376">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-376">not applicable</span></span>         |
|<span data-ttu-id="142d9-377">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="142d9-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="142d9-378">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-378">not applicable</span></span>            |
|<span data-ttu-id="142d9-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-379">MCAS</span></span>     |<span data-ttu-id="142d9-380">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="142d9-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="142d9-381">Matchad DLP-princip</span><span class="sxs-lookup"><span data-stu-id="142d9-381">DLP policy matched</span></span>

<span data-ttu-id="142d9-382">Den här händelsen genereras varje gång en DLP-princip matchas i ett dokument eller e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="142d9-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="142d9-383">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-383">Source</span></span>  |<span data-ttu-id="142d9-384">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-385">Exchange</span></span>         |<span data-ttu-id="142d9-386">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-386">yes</span></span>       |
|<span data-ttu-id="142d9-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="142d9-387">SharePoint Online</span></span>|<span data-ttu-id="142d9-388">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-388">yes</span></span>          |
|<span data-ttu-id="142d9-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-389">OneDrive</span></span> |<span data-ttu-id="142d9-390">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-390">yes</span></span>|
|<span data-ttu-id="142d9-391">Teams</span><span class="sxs-lookup"><span data-stu-id="142d9-391">Teams</span></span> |<span data-ttu-id="142d9-392">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-392">yes</span></span>   |
|<span data-ttu-id="142d9-393">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="142d9-393">Windows 10 devices</span></span>         |<span data-ttu-id="142d9-394">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-394">yes</span></span> |
|<span data-ttu-id="142d9-395">MAC</span><span class="sxs-lookup"><span data-stu-id="142d9-395">MAC</span></span>         |<span data-ttu-id="142d9-396">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-396">no</span></span>     |
|<span data-ttu-id="142d9-397">lokalt</span><span class="sxs-lookup"><span data-stu-id="142d9-397">on-premises</span></span>         |<span data-ttu-id="142d9-398">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-398">no</span></span>|
|<span data-ttu-id="142d9-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="142d9-399">MCAS</span></span>     |<span data-ttu-id="142d9-400">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-400">no</span></span>        | 

<span data-ttu-id="142d9-401">Händelserna för Windows 10 enheter (Endpoint DLP) är:</span><span class="sxs-lookup"><span data-stu-id="142d9-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="142d9-402">fil borttagna</span><span class="sxs-lookup"><span data-stu-id="142d9-402">file deleted</span></span>
- <span data-ttu-id="142d9-403">fil skapad</span><span class="sxs-lookup"><span data-stu-id="142d9-403">file created</span></span>
- <span data-ttu-id="142d9-404">fil kopierad till Urklipp</span><span class="sxs-lookup"><span data-stu-id="142d9-404">file copied to clipboard</span></span>
- <span data-ttu-id="142d9-405">fil ändrad</span><span class="sxs-lookup"><span data-stu-id="142d9-405">file modified</span></span>
- <span data-ttu-id="142d9-406">fil som lästs</span><span class="sxs-lookup"><span data-stu-id="142d9-406">file read</span></span>
- <span data-ttu-id="142d9-407">fil utskriven</span><span class="sxs-lookup"><span data-stu-id="142d9-407">file printed</span></span>
- <span data-ttu-id="142d9-408">filen har bytt namn</span><span class="sxs-lookup"><span data-stu-id="142d9-408">file renamed</span></span>
- <span data-ttu-id="142d9-409">fil kopierad till nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="142d9-409">file copied to network share</span></span>
- <span data-ttu-id="142d9-410">fil som används av ej tillkomlig app</span><span class="sxs-lookup"><span data-stu-id="142d9-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="142d9-411">Bevarandeetikett tillämpad</span><span class="sxs-lookup"><span data-stu-id="142d9-411">Retention label applied</span></span> 

<span data-ttu-id="142d9-412">Den här händelsen genereras varje gång ett dokument utan etiketter etiketteras eller ett e-postmeddelande skickas med en bevarandeetikett.</span><span class="sxs-lookup"><span data-stu-id="142d9-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="142d9-413">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="142d9-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="142d9-414">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-414">Source</span></span>  |<span data-ttu-id="142d9-415">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-416">Exchange</span></span>         |<span data-ttu-id="142d9-417">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-417">no</span></span>       |
|<span data-ttu-id="142d9-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="142d9-418">SharePoint Online</span></span>|<span data-ttu-id="142d9-419">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-419">yes</span></span>          |
|<span data-ttu-id="142d9-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-420">OneDrive</span></span> |<span data-ttu-id="142d9-421">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="142d9-422">Bevarandeetikett har ändrats</span><span class="sxs-lookup"><span data-stu-id="142d9-422">Retention label changed</span></span>

<span data-ttu-id="142d9-423">Händelsen genereras varje gång en etikett uppdateras i ett dokument eller e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="142d9-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="142d9-424">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="142d9-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="142d9-425">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-425">Source</span></span>  |<span data-ttu-id="142d9-426">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-427">Exchange</span></span>         |<span data-ttu-id="142d9-428">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-428">no</span></span>       |
|<span data-ttu-id="142d9-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="142d9-429">SharePoint Online</span></span>|<span data-ttu-id="142d9-430">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-430">yes</span></span>          |
|<span data-ttu-id="142d9-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-431">OneDrive</span></span> |<span data-ttu-id="142d9-432">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="142d9-433">Bevarandeetikett borttagen</span><span class="sxs-lookup"><span data-stu-id="142d9-433">Retention label removed</span></span>

<span data-ttu-id="142d9-434">Händelsen genereras varje gång en etikett tas bort från en fil eller ett dokument.</span><span class="sxs-lookup"><span data-stu-id="142d9-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="142d9-435">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="142d9-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="142d9-436">Source</span><span class="sxs-lookup"><span data-stu-id="142d9-436">Source</span></span>  |<span data-ttu-id="142d9-437">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="142d9-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="142d9-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="142d9-438">Exchange</span></span>         |<span data-ttu-id="142d9-439">Nej</span><span class="sxs-lookup"><span data-stu-id="142d9-439">no</span></span>       |
|<span data-ttu-id="142d9-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="142d9-440">SharePoint Online</span></span>|<span data-ttu-id="142d9-441">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-441">yes</span></span>          |
|<span data-ttu-id="142d9-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="142d9-442">OneDrive</span></span> |<span data-ttu-id="142d9-443">ja</span><span class="sxs-lookup"><span data-stu-id="142d9-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="142d9-444">Kända problem</span><span class="sxs-lookup"><span data-stu-id="142d9-444">Known issues</span></span>
  
- <span data-ttu-id="142d9-445">När den rekommenderade etikettypen visas för en slutanvändare så fångas den inte upp.</span><span class="sxs-lookup"><span data-stu-id="142d9-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="142d9-446">Men om användaren väljer att använda den rekommenderade etiketten visas etiketten under fältet Hur *används* som *Rekommenderas*</span><span class="sxs-lookup"><span data-stu-id="142d9-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="142d9-447">Justeringstexten är för närvarande inte tillgänglig vid känslighetsetiketts nedgradering från Sharepoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="142d9-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="142d9-448">Typer av känslig information är för närvarande inte tillgängliga för aktiviteter med automatisk etikett från Word, Excel, PowerPoint och Outlook samt SharePoint Online och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="142d9-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
