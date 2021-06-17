---
title: Testa hur Microsoft Defender för slutpunktsfunktioner fungerar i granskningsläge
description: I granskningsläget kan du se hur Microsoft Defender för Slutpunkt skyddar dina enheter om det var aktiverat.
keywords: sårbarhetsskydd, granskning, granskning, läge, aktiverat, inaktiverat, testa, demo, utvärdera, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985102"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="63d26-104">Minska testytans attackyta i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="63d26-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63d26-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="63d26-105">**Applies to:**</span></span>

- [<span data-ttu-id="63d26-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="63d26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="63d26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63d26-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="63d26-108">Som en del av organisationens säkerhetsteam kan du konfigurera funktioner för att minska attackytan i granskningsläge och se hur de kommer att fungera.</span><span class="sxs-lookup"><span data-stu-id="63d26-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="63d26-109">I granskningsläge kan du aktivera:</span><span class="sxs-lookup"><span data-stu-id="63d26-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="63d26-110">Regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="63d26-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="63d26-111">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="63d26-111">Exploit protection</span></span>
- <span data-ttu-id="63d26-112">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="63d26-112">Network protection</span></span>
- <span data-ttu-id="63d26-113">Och kontrollerad mappåtkomst i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="63d26-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="63d26-114">I granskningsläget kan du se vad som *skulle* ha hänt om du hade aktiverat funktionen.</span><span class="sxs-lookup"><span data-stu-id="63d26-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="63d26-115">Du kan aktivera granskningsläge när du testar hur funktionerna fungerar.</span><span class="sxs-lookup"><span data-stu-id="63d26-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="63d26-116">Det här hjälper till att säkerställa att dina verksamhetsbaserade appar inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="63d26-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="63d26-117">Du kan också få en uppfattning om hur många misstänkta filändringsförsök som görs under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="63d26-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="63d26-118">Funktionerna blockerar eller förhindrar inte att appar, skript eller filer ändras.</span><span class="sxs-lookup"><span data-stu-id="63d26-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="63d26-119">Men i Windows händelseloggen visas händelser som om funktionerna är helt aktiverade.</span><span class="sxs-lookup"><span data-stu-id="63d26-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="63d26-120">Med granskningsläge kan du granska händelseloggen och se vilken effekt funktionen skulle ha haft om den var aktiverad.</span><span class="sxs-lookup"><span data-stu-id="63d26-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="63d26-121">Du hittar de granskade posterna genom att gå till **Program och tjänster som**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Drift.**</span><span class="sxs-lookup"><span data-stu-id="63d26-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="63d26-122">Använd Defender för Slutpunkt för att få mer information om varje händelse, särskilt för att undersöka regler för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="63d26-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="63d26-123">Med Defender för slutpunktskonsolen kan du undersöka problem som en del av [scenarierna för aviseringstid och undersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="63d26-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="63d26-124">Du kan aktivera granskningsläge med grupprincip-, PowerShell- och konfigurationstjänstleverantörer (CSP).</span><span class="sxs-lookup"><span data-stu-id="63d26-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="63d26-125">Du kan också besöka webbplatsen Windows Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionerna fungerar och se hur de fungerar.</span><span class="sxs-lookup"><span data-stu-id="63d26-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="63d26-126">Granskningsalternativ</span><span class="sxs-lookup"><span data-stu-id="63d26-126">Audit options</span></span> | <span data-ttu-id="63d26-127">Så här aktiverar du granskningsläge</span><span class="sxs-lookup"><span data-stu-id="63d26-127">How to enable audit mode</span></span> | <span data-ttu-id="63d26-128">Så här visar du händelser</span><span class="sxs-lookup"><span data-stu-id="63d26-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="63d26-129">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="63d26-129">Audit applies to all events</span></span> | [<span data-ttu-id="63d26-130">Aktivera kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="63d26-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="63d26-131">Kontrollerade mappåtkomsthändelser</span><span class="sxs-lookup"><span data-stu-id="63d26-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="63d26-132">Granskningen gäller för enskilda regler</span><span class="sxs-lookup"><span data-stu-id="63d26-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="63d26-133">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="63d26-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="63d26-134">Händelser för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="63d26-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="63d26-135">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="63d26-135">Audit applies to all events</span></span> | [<span data-ttu-id="63d26-136">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="63d26-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="63d26-137">Nätverksskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="63d26-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="63d26-138">Granskning gäller för enskilda åtgärder</span><span class="sxs-lookup"><span data-stu-id="63d26-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="63d26-139">Aktivera exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="63d26-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="63d26-140">Sårbarhetsskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="63d26-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
