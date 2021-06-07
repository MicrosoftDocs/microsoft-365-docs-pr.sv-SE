---
title: Utvärdera regler för minskning av attackytan
description: Se hur minskning av attackytor blockerar och förhindrar attacker med det anpassade demoverktyget.
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, utvärdera, testa, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c2dea22cc8a0ebb875f83ebd5a3e42f723e5f254
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771327"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="3ab94-104">Utvärdera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="3ab94-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3ab94-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3ab94-105">**Applies to:**</span></span>

- [<span data-ttu-id="3ab94-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ab94-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3ab94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ab94-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3ab94-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3ab94-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ab94-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3ab94-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="3ab94-110">Minskningsregler för attackytan hjälper till att förhindra åtgärder som vanligtvis används av skadlig programvara för att avslöja enheter eller nätverk.</span><span class="sxs-lookup"><span data-stu-id="3ab94-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="3ab94-111">Minskningsregler för attackytor hjälper till att stänga av många av de vanliga instickspunkter som används av skadlig programvara och utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="3ab94-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="3ab94-112">Ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="3ab94-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="3ab94-113">Windows 10 Pro, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="3ab94-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3ab94-114">Windows 10 Enterprise, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="3ab94-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3ab94-115">Windows Server, [version 1803 (Halvårskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="3ab94-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3ab94-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3ab94-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3ab94-117">Lär dig hur du utvärderar regler för att minska attackytan genom att aktivera granskningsläge för att testa funktionen direkt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3ab94-117">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="3ab94-118">Du kan också besöka webbplatsen med microsoft Defender för slutpunktsdemonstration på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="3ab94-118">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="3ab94-119">Använd granskningsläge för att mäta påverkan</span><span class="sxs-lookup"><span data-stu-id="3ab94-119">Use audit mode to measure impact</span></span>

<span data-ttu-id="3ab94-120">Aktivera minskningsregler för attackytor i granskningsläge för att visa en post med appar som skulle ha blockerats om funktionen var helt aktiverad.</span><span class="sxs-lookup"><span data-stu-id="3ab94-120">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="3ab94-121">Testa hur funktionen fungerar i din organisation för att säkerställa att den inte påverkar dina verksamhetsbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="3ab94-121">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="3ab94-122">Du kan även få en uppfattning om hur ofta reglerna kommer att branda under normal användning.</span><span class="sxs-lookup"><span data-stu-id="3ab94-122">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="3ab94-123">Om du vill aktivera en minskningsregel för attackytor i granskningsläge använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3ab94-123">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="3ab94-124">Var `<rule ID>` finns ett [GUID-värde för minskningsregeln för attackytan](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="3ab94-124">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="3ab94-125">Använd följande PowerShell-cmdlet för att aktivera alla tillagda minskningsregler för attackytor i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="3ab94-125">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="3ab94-126">Om du vill granska hur minskningsregler för attackytor fungerar i organisationen måste du använda ett hanteringsverktyg för att distribuera den här inställningen till enheter i dina nätverk.</span><span class="sxs-lookup"><span data-stu-id="3ab94-126">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="3ab94-127">Du kan också använda grupprincip-, Intune- eller MDM-konfigurationstjänstleverantörer (MDM) för att konfigurera och distribuera inställningen.</span><span class="sxs-lookup"><span data-stu-id="3ab94-127">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="3ab94-128">Läs mer i huvudartikeln [om minskning av attackytor.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="3ab94-128">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="3ab94-129">Granska minskningar av attackytor i Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="3ab94-129">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="3ab94-130">Om du vill granska appar som skulle ha blockerats öppnar du Loggboken och filtrerar efter Händelse-ID 1121 i Microsoft-Windows-Windows Defender/operational log.</span><span class="sxs-lookup"><span data-stu-id="3ab94-130">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="3ab94-131">I följande tabell visas alla nätverksskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="3ab94-131">The following table lists all network protection events.</span></span>

<span data-ttu-id="3ab94-132">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="3ab94-132">Event ID</span></span> | <span data-ttu-id="3ab94-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3ab94-133">Description</span></span>
-|-
 <span data-ttu-id="3ab94-134">5007</span><span class="sxs-lookup"><span data-stu-id="3ab94-134">5007</span></span> | <span data-ttu-id="3ab94-135">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="3ab94-135">Event when settings are changed</span></span>
 <span data-ttu-id="3ab94-136">1121</span><span class="sxs-lookup"><span data-stu-id="3ab94-136">1121</span></span> | <span data-ttu-id="3ab94-137">Händelse när en minskningsregel för attackytan av fires i blockläge</span><span class="sxs-lookup"><span data-stu-id="3ab94-137">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="3ab94-138">1122</span><span class="sxs-lookup"><span data-stu-id="3ab94-138">1122</span></span> | <span data-ttu-id="3ab94-139">Händelse när en minskningsregel för attackytan i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="3ab94-139">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="3ab94-140">Anpassa regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="3ab94-140">Customize attack surface reduction rules</span></span>

<span data-ttu-id="3ab94-141">Under utvärderingen kanske du vill konfigurera varje regel individuellt eller exkludera vissa filer och processer från att utvärderas av funktionen.</span><span class="sxs-lookup"><span data-stu-id="3ab94-141">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="3ab94-142">Mer [information om hur du konfigurerar funktionen](customize-attack-surface-reduction.md) med hanteringsverktyg, bland annat Grupprincip och MDM-CSP-principer, finns i Anpassa minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="3ab94-142">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ab94-143">Se även</span><span class="sxs-lookup"><span data-stu-id="3ab94-143">See also</span></span>

* [<span data-ttu-id="3ab94-144">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="3ab94-144">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="3ab94-145">Använda granskningsläge för att utvärdera Windows Defender</span><span class="sxs-lookup"><span data-stu-id="3ab94-145">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="3ab94-146">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="3ab94-146">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
