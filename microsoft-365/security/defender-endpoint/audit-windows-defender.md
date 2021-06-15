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
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925665"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="19314-104">Minska testytans attackyta i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="19314-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19314-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="19314-105">**Applies to:**</span></span>
- [<span data-ttu-id="19314-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="19314-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="19314-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19314-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="19314-108">Om du är en del av organisationens säkerhetsteam kan du konfigurera funktioner för att minska attackytan i granskningsläge och se hur de fungerar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="19314-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="19314-109">I synnerhet kan du aktivera minskningsregler för attackytor, sårbarhetsskydd, nätverksskydd och kontrollerad mappåtkomst i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="19314-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="19314-110">I granskningsläget kan du se vad som *skulle* ha hänt om du hade aktiverat funktionen.</span><span class="sxs-lookup"><span data-stu-id="19314-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="19314-111">Du kanske vill aktivera granskningsläge när du testar hur funktionerna fungerar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="19314-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="19314-112">Det här hjälper till att säkerställa att dina verksamhetsbaserade appar inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="19314-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="19314-113">Du kan också få en uppfattning om hur många misstänkta filändringsförsök som görs under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="19314-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="19314-114">Funktionerna blockerar eller förhindrar inte att appar, skript eller filer ändras.</span><span class="sxs-lookup"><span data-stu-id="19314-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="19314-115">Men i Windows händelseloggen visas händelser som om funktionerna är helt aktiverade.</span><span class="sxs-lookup"><span data-stu-id="19314-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="19314-116">Med granskningsläge kan du granska händelseloggen och se vilken effekt funktionen skulle ha haft om den var aktiverad.</span><span class="sxs-lookup"><span data-stu-id="19314-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="19314-117">Du hittar de granskade posterna genom att gå till **Program och tjänster som**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Drift.**</span><span class="sxs-lookup"><span data-stu-id="19314-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="19314-118">Du kan använda Defender för Slutpunkt för att få mer information om varje händelse, särskilt för att undersöka regler för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="19314-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="19314-119">Med Defender för slutpunktskonsolen kan du undersöka problem som en del av [scenarierna för aviseringstid och undersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="19314-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="19314-120">Du kan använda grupprinciper, PowerShell och konfigurationstjänster för att aktivera granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="19314-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="19314-121">Du kan också besöka webbplatsen Windows Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionerna fungerar och se hur de fungerar.</span><span class="sxs-lookup"><span data-stu-id="19314-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="19314-122">Granskningsalternativ</span><span class="sxs-lookup"><span data-stu-id="19314-122">Audit options</span></span> | <span data-ttu-id="19314-123">Så här aktiverar du granskningsläge</span><span class="sxs-lookup"><span data-stu-id="19314-123">How to enable audit mode</span></span> | <span data-ttu-id="19314-124">Så här visar du händelser</span><span class="sxs-lookup"><span data-stu-id="19314-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="19314-125">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="19314-125">Audit applies to all events</span></span> | [<span data-ttu-id="19314-126">Aktivera kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="19314-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="19314-127">Kontrollerade mappåtkomsthändelser</span><span class="sxs-lookup"><span data-stu-id="19314-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="19314-128">Granskningen gäller för enskilda regler</span><span class="sxs-lookup"><span data-stu-id="19314-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="19314-129">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="19314-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="19314-130">Händelser för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="19314-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="19314-131">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="19314-131">Audit applies to all events</span></span> | [<span data-ttu-id="19314-132">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="19314-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="19314-133">Nätverksskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="19314-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="19314-134">Granskning gäller för enskilda åtgärder</span><span class="sxs-lookup"><span data-stu-id="19314-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="19314-135">Aktivera exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="19314-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="19314-136">Sårbarhetsskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="19314-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


