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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="42f7f-103">Märka aktiviteter som är tillgängliga i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="42f7f-104">Känslighetsetikett används</span><span class="sxs-lookup"><span data-stu-id="42f7f-104">Sensitivity label applied</span></span>

<span data-ttu-id="42f7f-105">Den här händelsen genereras varje gång ett dokument utan etikett sätts i etiketter eller ett e-postmeddelande skickas med en känslighetsetikett.</span><span class="sxs-lookup"><span data-stu-id="42f7f-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="42f7f-106">Den fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="42f7f-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="42f7f-107">Den fångas när den förekommer i Azure Information Protection-tillägg.</span><span class="sxs-lookup"><span data-stu-id="42f7f-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="42f7f-108">Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.</span><span class="sxs-lookup"><span data-stu-id="42f7f-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="42f7f-109">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-109">Source</span></span>  |<span data-ttu-id="42f7f-110">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-110">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-111">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="42f7f-112">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="42f7f-113">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-113">yes</span></span> |
|<span data-ttu-id="42f7f-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-114">Outlook</span></span>| <span data-ttu-id="42f7f-115">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-115">yes</span></span> |<span data-ttu-id="42f7f-116">från Win 32</span><span class="sxs-lookup"><span data-stu-id="42f7f-116">from Win 32</span></span> |
|<span data-ttu-id="42f7f-117">SharePoint online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="42f7f-118">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-118">yes</span></span> | |
|<span data-ttu-id="42f7f-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-119">Exchange</span></span>        |<span data-ttu-id="42f7f-120">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-120">yes</span></span>         | |
|<span data-ttu-id="42f7f-121">Enhetlig klient och enhetlig AIP-skanner i Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="42f7f-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="42f7f-122">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-122">yes</span></span> |<span data-ttu-id="42f7f-123">Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="42f7f-124">Microsoft information protection (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="42f7f-125">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-125">yes</span></span>|<span data-ttu-id="42f7f-126">Åtgärden för ny *etikett i* AIP mappas till etiketten som *används i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="42f7f-127">RMS (Rights Management Service)</span><span class="sxs-lookup"><span data-stu-id="42f7f-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="42f7f-128">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-128">not applicable</span></span>         | |
|<span data-ttu-id="42f7f-129">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-129">Power BI desktop and web</span></span>        | <span data-ttu-id="42f7f-130">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-130">no</span></span>| <span data-ttu-id="42f7f-131">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="42f7f-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="42f7f-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="42f7f-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="42f7f-133">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="42f7f-134">Känslighetsetikett har ändrats</span><span class="sxs-lookup"><span data-stu-id="42f7f-134">Sensitivity label changed</span></span>

<span data-ttu-id="42f7f-135">Den här händelsen genereras varje gång en känslighetsetikett uppdateras i dokumentet eller e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="42f7f-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="42f7f-136">För källorna AIP Unified Client, Unified Scanner och  MIP SDK har AIP-uppgraderingsetiketten och nedgraderingsetikettsmapparna till aktivitetsutforskaren *ändrats* </span><span class="sxs-lookup"><span data-stu-id="42f7f-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="42f7f-137">Den fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="42f7f-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="42f7f-138">Händelsen fångas när det inträffar i Azure Information Protection Unified Client-tillägg och tvingande skannrar</span><span class="sxs-lookup"><span data-stu-id="42f7f-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="42f7f-139">Åtgärder för uppgradering och nedgradering av etiketter kan också övervakas via *fältet och filtret för händelsetypen* Etikett.</span><span class="sxs-lookup"><span data-stu-id="42f7f-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="42f7f-140">*Justeringstexten* förs också in utom för justering SharePoint Online och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="42f7f-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="42f7f-141">Känslighetsetiketter som utförs i Office inbyggda appar på Outlook samlar in den senaste åtgärden som skapades innan åtgärder för att spara/skicka filer/e-post.</span><span class="sxs-lookup"><span data-stu-id="42f7f-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="42f7f-142">Om användaren till exempel ändrar etikett i ett e-postmeddelande flera gånger innan det skickas fångas den sista etiketten på e-postmeddelandet när det skickas i granskningsloggen och rapporteras sedan i aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="42f7f-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="42f7f-143">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-143">Source</span></span>  |<span data-ttu-id="42f7f-144">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-144">Reported in activity explorer</span></span>|<span data-ttu-id="42f7f-145">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-146">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-147">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-147">yes</span></span>         |
|<span data-ttu-id="42f7f-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-148">Outlook</span></span>         |<span data-ttu-id="42f7f-149">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-149">yes</span></span>         |<span data-ttu-id="42f7f-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="42f7f-150">Win 32</span></span>|
|<span data-ttu-id="42f7f-151">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-152">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-152">yes</span></span>         |
|<span data-ttu-id="42f7f-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-153">Exchange</span></span>         |<span data-ttu-id="42f7f-154">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-154">yes</span></span>         |
|<span data-ttu-id="42f7f-155">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-155">AIP unified client</span></span>         |<span data-ttu-id="42f7f-156">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-156">yes</span></span>         |
|<span data-ttu-id="42f7f-157">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-157">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-158">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-158">yes</span></span>         |
|<span data-ttu-id="42f7f-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-159">MIP SDK</span></span>         |<span data-ttu-id="42f7f-160">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-160">yes</span></span>         |
|<span data-ttu-id="42f7f-161">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-161">RMS service</span></span>         |<span data-ttu-id="42f7f-162">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-162">not applicable</span></span>         |
|<span data-ttu-id="42f7f-163">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-164">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-164">no</span></span>         |<span data-ttu-id="42f7f-165">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="42f7f-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="42f7f-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-166">MCAS</span></span>     |<span data-ttu-id="42f7f-167">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="42f7f-168">Känslighetsetikett borttagen</span><span class="sxs-lookup"><span data-stu-id="42f7f-168">Sensitivity label removed</span></span>

<span data-ttu-id="42f7f-169">Den här händelsen genereras varje gång en känslighetsetikett tas bort från en fil eller ett dokument.</span><span class="sxs-lookup"><span data-stu-id="42f7f-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="42f7f-170">Händelsen fångas när du sparar i Office program och webbprogram.</span><span class="sxs-lookup"><span data-stu-id="42f7f-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="42f7f-171">Den fångas när den förekommer i Azure Information Protection-tillägg.</span><span class="sxs-lookup"><span data-stu-id="42f7f-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="42f7f-172">Känslighetsetiketter, med Office inbyggd MIP-etikett, på Outlook samlar in den senaste händelsen med etiketter som skapades innan åtgärderna spara/skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="42f7f-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="42f7f-173">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-173">Source</span></span>  |<span data-ttu-id="42f7f-174">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-174">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-175">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-176">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-177">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-177">yes</span></span>         |
|<span data-ttu-id="42f7f-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-178">Outlook</span></span>         |<span data-ttu-id="42f7f-179">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-179">yes</span></span>         |<span data-ttu-id="42f7f-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="42f7f-180">Win 32</span></span>|
|<span data-ttu-id="42f7f-181">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-182">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-182">yes</span></span>         |
|<span data-ttu-id="42f7f-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-183">Exchange</span></span>         |<span data-ttu-id="42f7f-184">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-184">yes</span></span>         |
|<span data-ttu-id="42f7f-185">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-185">AIP unified client</span></span>         |<span data-ttu-id="42f7f-186">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-186">yes</span></span>         |<span data-ttu-id="42f7f-187">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-188">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-188">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-189">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-189">yes</span></span>         |<span data-ttu-id="42f7f-190">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="42f7f-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-191">MIP SDK</span></span>         |<span data-ttu-id="42f7f-192">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-192">yes</span></span>         |<span data-ttu-id="42f7f-193">Åtgärden Ta bort *etikett i* AIP är mappad till åtgärden ta *bort etikett* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="42f7f-194">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-194">RMS service</span></span>         |<span data-ttu-id="42f7f-195">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-195">not applicable</span></span>         |
|<span data-ttu-id="42f7f-196">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-197">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-197">no</span></span>         |<span data-ttu-id="42f7f-198">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="42f7f-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="42f7f-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-199">MCAS</span></span>     |<span data-ttu-id="42f7f-200">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="42f7f-201">Känslighetsetikettsfil läst</span><span class="sxs-lookup"><span data-stu-id="42f7f-201">Sensitivity label file read</span></span>

<span data-ttu-id="42f7f-202">Den här händelsen genereras varje gång ett känslighetsetiketterat eller skyddat dokument öppnas.</span><span class="sxs-lookup"><span data-stu-id="42f7f-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="42f7f-203">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-203">Source</span></span>  |<span data-ttu-id="42f7f-204">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-204">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-205">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-206">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-207">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-207">yes</span></span>         |
|<span data-ttu-id="42f7f-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-208">Outlook</span></span>         |<span data-ttu-id="42f7f-209">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-209">no</span></span>         |
|<span data-ttu-id="42f7f-210">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-211">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-211">no</span></span>         |
|<span data-ttu-id="42f7f-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-212">Exchange</span></span>         |<span data-ttu-id="42f7f-213">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-213">no</span></span>         |
|<span data-ttu-id="42f7f-214">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-214">AIP unified client</span></span>         |<span data-ttu-id="42f7f-215">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-215">yes</span></span>         |<span data-ttu-id="42f7f-216">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-217">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-217">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-218">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-218">yes</span></span>         |<span data-ttu-id="42f7f-219">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-220">MIP SDK</span></span>         |<span data-ttu-id="42f7f-221">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-221">yes</span></span>         |<span data-ttu-id="42f7f-222">*AIP-åtkomståtgärden* mappas till *läsåtgärden för* filen i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-223">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-223">RMS service</span></span>         |<span data-ttu-id="42f7f-224">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-224">yes</span></span>         |<span data-ttu-id="42f7f-225">*Åtkomståtgärden* är mappad till *filläsningsåtgärden* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="42f7f-226">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-227">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-227">no</span></span>         |<span data-ttu-id="42f7f-228">tillgängliga i Microsoft 365 granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="42f7f-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="42f7f-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-229">MCAS</span></span>     |<span data-ttu-id="42f7f-230">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="42f7f-231">Upptäckta filer</span><span class="sxs-lookup"><span data-stu-id="42f7f-231">Files discovered</span></span>

<span data-ttu-id="42f7f-232">Händelsen genereras varje gång filer upptäcks när AIP-skanner används för att skanna känsliga data på olika platser och hittar filer.</span><span class="sxs-lookup"><span data-stu-id="42f7f-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="42f7f-233">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-233">Source</span></span>  |<span data-ttu-id="42f7f-234">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-234">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-235">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-236">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-237">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-237">not applicable</span></span>         |
|<span data-ttu-id="42f7f-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-238">Outlook</span></span>         |<span data-ttu-id="42f7f-239">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-239">not applicable</span></span>         |
|<span data-ttu-id="42f7f-240">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-241">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-241">not applicable</span></span>         |
|<span data-ttu-id="42f7f-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-242">Exchange</span></span>         |<span data-ttu-id="42f7f-243">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-243">not applicable</span></span>         |
|<span data-ttu-id="42f7f-244">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-244">AIP unified client</span></span>         |<span data-ttu-id="42f7f-245">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-245">not applicable</span></span>       |
|<span data-ttu-id="42f7f-246">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-246">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-247">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-247">yes</span></span>         |<span data-ttu-id="42f7f-248">Åtgärden för *AIP-identifiering* mappas till de filer som *identifierats i* aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-249">MIP SDK</span></span>         |<span data-ttu-id="42f7f-250">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-250">yes</span></span>         |<span data-ttu-id="42f7f-251">Åtgärden för att *identifiera AIP* mappas till den fil *som identifierats* i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="42f7f-252">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-252">RMS service</span></span>         |<span data-ttu-id="42f7f-253">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-253">not applicable</span></span>         |
|<span data-ttu-id="42f7f-254">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-255">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-255">not applicable</span></span>         |
|<span data-ttu-id="42f7f-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-256">MCAS</span></span>     |<span data-ttu-id="42f7f-257">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="42f7f-258">Känslighetsetikettsfil har bytt namn</span><span class="sxs-lookup"><span data-stu-id="42f7f-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="42f7f-259">Den här händelsen genereras varje gång ett dokument med en känslighetsetikett byter namn.</span><span class="sxs-lookup"><span data-stu-id="42f7f-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="42f7f-260">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-260">Source</span></span>  | <span data-ttu-id="42f7f-261">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-261">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-262">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-263">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-264">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-264">yes</span></span>         |
|<span data-ttu-id="42f7f-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-265">Outlook</span></span>         |<span data-ttu-id="42f7f-266">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-266">not applicable</span></span>         |
|<span data-ttu-id="42f7f-267">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-268">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-268">no</span></span>        |
|<span data-ttu-id="42f7f-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-269">Exchange</span></span>         |<span data-ttu-id="42f7f-270">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-270">not applicable</span></span>         |
|<span data-ttu-id="42f7f-271">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-271">AIP unified client</span></span>         |<span data-ttu-id="42f7f-272">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-272">no</span></span>         |
|<span data-ttu-id="42f7f-273">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-273">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-274">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-274">no</span></span>         |
|<span data-ttu-id="42f7f-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-275">MIP SDK</span></span>         |<span data-ttu-id="42f7f-276">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-276">no</span></span>         |
|<span data-ttu-id="42f7f-277">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-277">RMS service</span></span>         |<span data-ttu-id="42f7f-278">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-278">no</span></span>      |
|<span data-ttu-id="42f7f-279">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-280">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-280">no</span></span>         |
|<span data-ttu-id="42f7f-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-281">MCAS</span></span>     |<span data-ttu-id="42f7f-282">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="42f7f-283">Filen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="42f7f-283">File removed</span></span>

<span data-ttu-id="42f7f-284">Händelsen genereras varje gång AIP-skannern upptäcker att en tidigare skannad fil har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="42f7f-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="42f7f-285">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-285">Source</span></span>  |<span data-ttu-id="42f7f-286">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-286">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-287">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-288">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-289">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-289">not applicable</span></span>         |
|<span data-ttu-id="42f7f-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-290">Outlook</span></span>         |<span data-ttu-id="42f7f-291">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-291">not applicable</span></span>         |
|<span data-ttu-id="42f7f-292">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-293">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-293">not applicable</span></span>           |
|<span data-ttu-id="42f7f-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-294">Exchange</span></span>         |<span data-ttu-id="42f7f-295">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-295">not applicable</span></span>         |
|<span data-ttu-id="42f7f-296">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-296">AIP unified client</span></span>         |<span data-ttu-id="42f7f-297">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-297">not applicable</span></span>            |
|<span data-ttu-id="42f7f-298">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-298">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-299">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-299">yes</span></span>         |
|<span data-ttu-id="42f7f-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-300">MIP SDK</span></span>         |<span data-ttu-id="42f7f-301">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-301">not applicable</span></span>            |
|<span data-ttu-id="42f7f-302">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-302">RMS service</span></span>         |<span data-ttu-id="42f7f-303">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-303">not applicable</span></span>         |
|<span data-ttu-id="42f7f-304">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-305">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-305">not applicable</span></span>  |
|<span data-ttu-id="42f7f-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-306">MCAS</span></span>     |<span data-ttu-id="42f7f-307">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="42f7f-308">Skydd tillämpat</span><span class="sxs-lookup"><span data-stu-id="42f7f-308">Protection applied</span></span>

<span data-ttu-id="42f7f-309">Den här händelsen genereras första gången skydd läggs till manuellt för ett objekt som inte har en etikett.</span><span class="sxs-lookup"><span data-stu-id="42f7f-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="42f7f-310">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-310">Source</span></span>  |<span data-ttu-id="42f7f-311">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-311">Reported in activity explorer</span></span> | <span data-ttu-id="42f7f-312">Obs!</span><span class="sxs-lookup"><span data-stu-id="42f7f-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="42f7f-313">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-314">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-314">no</span></span>         |
|<span data-ttu-id="42f7f-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-315">Outlook</span></span>         |<span data-ttu-id="42f7f-316">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-316">no</span></span>         |
|<span data-ttu-id="42f7f-317">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-318">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-318">not applicable</span></span>           |
|<span data-ttu-id="42f7f-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-319">Exchange</span></span>         |<span data-ttu-id="42f7f-320">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-320">no</span></span>       |
|<span data-ttu-id="42f7f-321">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-321">AIP unified client</span></span>         |<span data-ttu-id="42f7f-322">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-322">yes</span></span>            |
|<span data-ttu-id="42f7f-323">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-323">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-324">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-324">not applicable</span></span>         |
|<span data-ttu-id="42f7f-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-325">MIP SDK</span></span>         |<span data-ttu-id="42f7f-326">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-326">yes</span></span>            |
|<span data-ttu-id="42f7f-327">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-327">RMS service</span></span>         |<span data-ttu-id="42f7f-328">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-328">not applicable</span></span>         |
|<span data-ttu-id="42f7f-329">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-330">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-330">not applicable</span></span>            |
|<span data-ttu-id="42f7f-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-331">MCAS</span></span>     |<span data-ttu-id="42f7f-332">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="42f7f-333">Skydd har ändrats</span><span class="sxs-lookup"><span data-stu-id="42f7f-333">Protection changed</span></span>

<span data-ttu-id="42f7f-334">Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.</span><span class="sxs-lookup"><span data-stu-id="42f7f-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="42f7f-335">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-335">Source</span></span>  |<span data-ttu-id="42f7f-336">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-337">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-338">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-338">no</span></span>         |
|<span data-ttu-id="42f7f-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-339">Outlook</span></span>         |<span data-ttu-id="42f7f-340">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-340">no</span></span>         |
|<span data-ttu-id="42f7f-341">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-342">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-342">not applicable</span></span>           |
|<span data-ttu-id="42f7f-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-343">Exchange</span></span>         |<span data-ttu-id="42f7f-344">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-344">no</span></span>       |
|<span data-ttu-id="42f7f-345">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-345">AIP unified client</span></span>         |<span data-ttu-id="42f7f-346">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-346">yes</span></span>            |
|<span data-ttu-id="42f7f-347">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-347">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-348">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-348">not applicable</span></span>         |
|<span data-ttu-id="42f7f-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-349">MIP SDK</span></span>         |<span data-ttu-id="42f7f-350">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-350">yes</span></span>            |
|<span data-ttu-id="42f7f-351">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-351">RMS service</span></span>         |<span data-ttu-id="42f7f-352">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-352">not applicable</span></span>         |
|<span data-ttu-id="42f7f-353">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-354">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-354">not applicable</span></span>            |
|<span data-ttu-id="42f7f-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-355">MCAS</span></span>     |<span data-ttu-id="42f7f-356">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="42f7f-357">Skydd har tagits bort</span><span class="sxs-lookup"><span data-stu-id="42f7f-357">Protection removed</span></span>

<span data-ttu-id="42f7f-358">Den här händelsen genereras varje gång skyddet för ett dokument utan etikett ändras manuellt.</span><span class="sxs-lookup"><span data-stu-id="42f7f-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="42f7f-359">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-359">Source</span></span>  |<span data-ttu-id="42f7f-360">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-361">Word, Excel, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="42f7f-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="42f7f-362">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-362">no</span></span>         |
|<span data-ttu-id="42f7f-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="42f7f-363">Outlook</span></span>         |<span data-ttu-id="42f7f-364">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-364">no</span></span>         |
|<span data-ttu-id="42f7f-365">SharePoint Online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="42f7f-366">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-366">not applicable</span></span>           |
|<span data-ttu-id="42f7f-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-367">Exchange</span></span>         |<span data-ttu-id="42f7f-368">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-368">no</span></span>       |
|<span data-ttu-id="42f7f-369">Enhetlig AIP-klient</span><span class="sxs-lookup"><span data-stu-id="42f7f-369">AIP unified client</span></span>         |<span data-ttu-id="42f7f-370">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-370">yes</span></span>            |
|<span data-ttu-id="42f7f-371">AIP unified scanner</span><span class="sxs-lookup"><span data-stu-id="42f7f-371">AIP unified scanner</span></span>         |<span data-ttu-id="42f7f-372">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-372">not applicable</span></span>         |
|<span data-ttu-id="42f7f-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="42f7f-373">MIP SDK</span></span>         |<span data-ttu-id="42f7f-374">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-374">yes</span></span>            |
|<span data-ttu-id="42f7f-375">RMS-tjänst</span><span class="sxs-lookup"><span data-stu-id="42f7f-375">RMS service</span></span>         |<span data-ttu-id="42f7f-376">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-376">not applicable</span></span>         |
|<span data-ttu-id="42f7f-377">Power BI dator och webb</span><span class="sxs-lookup"><span data-stu-id="42f7f-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="42f7f-378">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-378">not applicable</span></span>            |
|<span data-ttu-id="42f7f-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-379">MCAS</span></span>     |<span data-ttu-id="42f7f-380">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="42f7f-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="42f7f-381">Matchad DLP-princip</span><span class="sxs-lookup"><span data-stu-id="42f7f-381">DLP policy matched</span></span>

<span data-ttu-id="42f7f-382">Den här händelsen genereras varje gång en DLP-princip matchas i ett dokument eller e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="42f7f-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="42f7f-383">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-383">Source</span></span>  |<span data-ttu-id="42f7f-384">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-385">Exchange</span></span>         |<span data-ttu-id="42f7f-386">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-386">yes</span></span>       |
|<span data-ttu-id="42f7f-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="42f7f-387">SharePoint Online</span></span>|<span data-ttu-id="42f7f-388">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-388">yes</span></span>          |
|<span data-ttu-id="42f7f-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-389">OneDrive</span></span> |<span data-ttu-id="42f7f-390">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-390">yes</span></span>|
|<span data-ttu-id="42f7f-391">Teams</span><span class="sxs-lookup"><span data-stu-id="42f7f-391">Teams</span></span> |<span data-ttu-id="42f7f-392">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-392">yes</span></span>   |
|<span data-ttu-id="42f7f-393">Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="42f7f-393">Windows 10 devices</span></span>         |<span data-ttu-id="42f7f-394">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-394">yes</span></span> |
|<span data-ttu-id="42f7f-395">MAC</span><span class="sxs-lookup"><span data-stu-id="42f7f-395">MAC</span></span>         |<span data-ttu-id="42f7f-396">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-396">no</span></span>     |
|<span data-ttu-id="42f7f-397">lokalt</span><span class="sxs-lookup"><span data-stu-id="42f7f-397">on-premises</span></span>         |<span data-ttu-id="42f7f-398">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-398">no</span></span>|
|<span data-ttu-id="42f7f-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="42f7f-399">MCAS</span></span>     |<span data-ttu-id="42f7f-400">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-400">no</span></span>        | 

<span data-ttu-id="42f7f-401">Händelserna för Windows 10 enheter (Endpoint DLP) är:</span><span class="sxs-lookup"><span data-stu-id="42f7f-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="42f7f-402">fil borttagna</span><span class="sxs-lookup"><span data-stu-id="42f7f-402">file deleted</span></span>
- <span data-ttu-id="42f7f-403">fil skapad</span><span class="sxs-lookup"><span data-stu-id="42f7f-403">file created</span></span>
- <span data-ttu-id="42f7f-404">fil kopierad till Urklipp</span><span class="sxs-lookup"><span data-stu-id="42f7f-404">file copied to clipboard</span></span>
- <span data-ttu-id="42f7f-405">fil ändrad</span><span class="sxs-lookup"><span data-stu-id="42f7f-405">file modified</span></span>
- <span data-ttu-id="42f7f-406">fil som lästs</span><span class="sxs-lookup"><span data-stu-id="42f7f-406">file read</span></span>
- <span data-ttu-id="42f7f-407">fil utskriven</span><span class="sxs-lookup"><span data-stu-id="42f7f-407">file printed</span></span>
- <span data-ttu-id="42f7f-408">filen har bytt namn</span><span class="sxs-lookup"><span data-stu-id="42f7f-408">file renamed</span></span>
- <span data-ttu-id="42f7f-409">fil kopierad till nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="42f7f-409">file copied to network share</span></span>
- <span data-ttu-id="42f7f-410">fil som används av ej tillkomlig app</span><span class="sxs-lookup"><span data-stu-id="42f7f-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="42f7f-411">Bevarandeetikett tillämpad</span><span class="sxs-lookup"><span data-stu-id="42f7f-411">Retention label applied</span></span> 

<span data-ttu-id="42f7f-412">Den här händelsen genereras varje gång ett dokument utan etiketter etiketteras eller ett e-postmeddelande skickas med en bevarandeetikett.</span><span class="sxs-lookup"><span data-stu-id="42f7f-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="42f7f-413">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="42f7f-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="42f7f-414">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-414">Source</span></span>  |<span data-ttu-id="42f7f-415">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-416">Exchange</span></span>         |<span data-ttu-id="42f7f-417">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-417">no</span></span>       |
|<span data-ttu-id="42f7f-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="42f7f-418">SharePoint Online</span></span>|<span data-ttu-id="42f7f-419">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-419">yes</span></span>          |
|<span data-ttu-id="42f7f-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-420">OneDrive</span></span> |<span data-ttu-id="42f7f-421">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="42f7f-422">Bevarandeetikett har ändrats</span><span class="sxs-lookup"><span data-stu-id="42f7f-422">Retention label changed</span></span>

<span data-ttu-id="42f7f-423">Händelsen genereras varje gång en etikett uppdateras i ett dokument eller e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="42f7f-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="42f7f-424">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="42f7f-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="42f7f-425">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-425">Source</span></span>  |<span data-ttu-id="42f7f-426">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-427">Exchange</span></span>         |<span data-ttu-id="42f7f-428">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-428">no</span></span>       |
|<span data-ttu-id="42f7f-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="42f7f-429">SharePoint Online</span></span>|<span data-ttu-id="42f7f-430">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-430">yes</span></span>          |
|<span data-ttu-id="42f7f-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-431">OneDrive</span></span> |<span data-ttu-id="42f7f-432">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="42f7f-433">Bevarandeetikett borttagen</span><span class="sxs-lookup"><span data-stu-id="42f7f-433">Retention label removed</span></span>

<span data-ttu-id="42f7f-434">Händelsen genereras varje gång en etikett tas bort från en fil eller ett dokument.</span><span class="sxs-lookup"><span data-stu-id="42f7f-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="42f7f-435">Den sparas när du sparar ett dokument och när den skickas till ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="42f7f-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="42f7f-436">Source</span><span class="sxs-lookup"><span data-stu-id="42f7f-436">Source</span></span>  |<span data-ttu-id="42f7f-437">Rapporterad i Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="42f7f-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="42f7f-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="42f7f-438">Exchange</span></span>         |<span data-ttu-id="42f7f-439">nej</span><span class="sxs-lookup"><span data-stu-id="42f7f-439">no</span></span>       |
|<span data-ttu-id="42f7f-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="42f7f-440">SharePoint Online</span></span>|<span data-ttu-id="42f7f-441">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-441">yes</span></span>          |
|<span data-ttu-id="42f7f-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="42f7f-442">OneDrive</span></span> |<span data-ttu-id="42f7f-443">ja</span><span class="sxs-lookup"><span data-stu-id="42f7f-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="42f7f-444">Kända problem</span><span class="sxs-lookup"><span data-stu-id="42f7f-444">Known issues</span></span>
  
- <span data-ttu-id="42f7f-445">När den rekommenderade etikettypen visas för en slutanvändare så fångas den inte upp.</span><span class="sxs-lookup"><span data-stu-id="42f7f-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="42f7f-446">Men om användaren väljer att använda den rekommenderade etiketten visas etiketten under fältet Hur *används* som *Rekommenderas*</span><span class="sxs-lookup"><span data-stu-id="42f7f-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="42f7f-447">Justeringstexten är för närvarande inte tillgänglig vid känslighetsetiketts nedgradering från Sharepoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="42f7f-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="42f7f-448">Typer av känslig information är för närvarande inte tillgängliga för aktiviteter med automatisk etikett från Word, Excel, PowerPoint och Outlook samt SharePoint Online och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="42f7f-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
