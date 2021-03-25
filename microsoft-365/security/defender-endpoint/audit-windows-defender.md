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
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075393"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="19b40-104">Testa hur Microsoft Defender för slutpunktsfunktioner fungerar i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="19b40-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19b40-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="19b40-105">**Applies to:**</span></span>
- [<span data-ttu-id="19b40-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="19b40-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="19b40-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19b40-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="19b40-108">Du kan aktivera minskningsregler för attackytan, sårbarhetsskydd, nätverksskydd och kontrollerad mappåtkomst i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="19b40-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="19b40-109">I granskningsläget kan du se vad som *skulle* ha hänt om du hade aktiverat funktionen.</span><span class="sxs-lookup"><span data-stu-id="19b40-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="19b40-110">Du kanske vill aktivera granskningsläge när du testar hur funktionerna fungerar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="19b40-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="19b40-111">Det här hjälper till att säkerställa att dina verksamhetsbaserade appar inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="19b40-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="19b40-112">Du kan också få en uppfattning om hur många misstänkta filändringsförsök som görs under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="19b40-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="19b40-113">Funktionerna blockerar eller förhindrar inte att appar, skript eller filer ändras.</span><span class="sxs-lookup"><span data-stu-id="19b40-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="19b40-114">Men i Windows-händelseloggen spelar du in händelser som om funktionerna var helt aktiverade.</span><span class="sxs-lookup"><span data-stu-id="19b40-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="19b40-115">Med granskningsläge kan du granska händelseloggen och se vilken effekt funktionen skulle ha haft om den var aktiverad.</span><span class="sxs-lookup"><span data-stu-id="19b40-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="19b40-116">Du hittar de granskade posterna genom att gå till **Program och tjänster**  >  **Microsoft**  >  **Windows**  >  **Defender**  >  **Drift.**</span><span class="sxs-lookup"><span data-stu-id="19b40-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="19b40-117">Du kan använda Defender för Slutpunkt för att få mer information om varje händelse, särskilt för att undersöka regler för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="19b40-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="19b40-118">Med Defender för slutpunktskonsolen kan du undersöka problem som en del av [scenarierna för aviseringstid och undersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="19b40-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="19b40-119">Du kan använda grupprinciper, PowerShell och konfigurationstjänster för att aktivera granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="19b40-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="19b40-120">Du kan också gå till Windows Defender Testground-webbplatsen [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionerna fungerar och se hur de fungerar.</span><span class="sxs-lookup"><span data-stu-id="19b40-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="19b40-121">**Granskningsalternativ**</span><span class="sxs-lookup"><span data-stu-id="19b40-121">**Audit options**</span></span> | <span data-ttu-id="19b40-122">**Så här aktiverar du granskningsläge**</span><span class="sxs-lookup"><span data-stu-id="19b40-122">**How to enable audit mode**</span></span> | <span data-ttu-id="19b40-123">**Så här visar du händelser**</span><span class="sxs-lookup"><span data-stu-id="19b40-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="19b40-124">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="19b40-124">Audit applies to all events</span></span> | [<span data-ttu-id="19b40-125">Aktivera reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="19b40-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="19b40-126">Kontrollerade mappåtkomsthändelser</span><span class="sxs-lookup"><span data-stu-id="19b40-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="19b40-127">Granskningen gäller för enskilda regler</span><span class="sxs-lookup"><span data-stu-id="19b40-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="19b40-128">Aktivera minskningsregler för attackytor</span><span class="sxs-lookup"><span data-stu-id="19b40-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="19b40-129">Händelser för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="19b40-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="19b40-130">Granskning gäller för alla händelser</span><span class="sxs-lookup"><span data-stu-id="19b40-130">Audit applies to all events</span></span> | [<span data-ttu-id="19b40-131">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="19b40-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="19b40-132">Nätverksskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="19b40-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="19b40-133">Granskning gäller för enskilda åtgärder</span><span class="sxs-lookup"><span data-stu-id="19b40-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="19b40-134">Aktivera sårbarhetsskydd</span><span class="sxs-lookup"><span data-stu-id="19b40-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="19b40-135">Sårbarhetsskyddshändelser</span><span class="sxs-lookup"><span data-stu-id="19b40-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="19b40-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="19b40-136">Related topics</span></span>

* [<span data-ttu-id="19b40-137">Skydda enheter från sårbarheter</span><span class="sxs-lookup"><span data-stu-id="19b40-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="19b40-138">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="19b40-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="19b40-139">Skydda ditt nätverk</span><span class="sxs-lookup"><span data-stu-id="19b40-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="19b40-140">Skydda viktiga mappar</span><span class="sxs-lookup"><span data-stu-id="19b40-140">Protect important folders</span></span>](controlled-folders.md)
