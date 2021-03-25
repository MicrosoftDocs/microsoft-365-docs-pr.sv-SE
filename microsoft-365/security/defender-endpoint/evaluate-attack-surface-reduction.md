---
title: Utvärdera minskningsregler för attackytor
description: Se hur minskning av attackytor blockerar och förhindrar attacker med det anpassade demoverktyget.
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, utvärdera, testa, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 13b1ac5f71f2bc24ad6f52af6722e12fab935270
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075833"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="0b881-104">Utvärdera minskningsregler för attackytor</span><span class="sxs-lookup"><span data-stu-id="0b881-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0b881-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0b881-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b881-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b881-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0b881-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b881-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0b881-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0b881-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0b881-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0b881-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="0b881-110">Minskningsregler för attackytan hjälper till att förhindra åtgärder som vanligtvis används av skadlig programvara för att avslöja enheter eller nätverk.</span><span class="sxs-lookup"><span data-stu-id="0b881-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="0b881-111">Ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="0b881-111">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="0b881-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="0b881-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0b881-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="0b881-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0b881-114">Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="0b881-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="0b881-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0b881-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="0b881-116">Lär dig hur du utvärderar regler för att minska attackytan genom att aktivera granskningsläge för att testa funktionen direkt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="0b881-116">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="0b881-117">Du kan också besöka webbplatsen med microsoft Defender för slutpunktsdemonstration på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="0b881-117">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="0b881-118">Använd granskningsläge för att mäta påverkan</span><span class="sxs-lookup"><span data-stu-id="0b881-118">Use audit mode to measure impact</span></span>

<span data-ttu-id="0b881-119">Aktivera minskningsregler för attackytor i granskningsläge för att visa en post med appar som skulle ha blockerats om funktionen var helt aktiverad.</span><span class="sxs-lookup"><span data-stu-id="0b881-119">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="0b881-120">Testa hur funktionen fungerar i din organisation för att säkerställa att den inte påverkar dina verksamhetsbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="0b881-120">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="0b881-121">Du kan även få en uppfattning om hur ofta reglerna kommer att branda under normal användning.</span><span class="sxs-lookup"><span data-stu-id="0b881-121">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="0b881-122">Om du vill aktivera en minskningsregel för attackytor i granskningsläge använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b881-122">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="0b881-123">Var `<rule ID>` finns ett [GUID-värde för minskningsregeln för attackytan](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="0b881-123">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="0b881-124">Använd följande PowerShell-cmdlet för att aktivera alla tillagda minskningsregler för attackytor i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="0b881-124">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="0b881-125">Om du vill granska hur minskningsregler för attackytor fungerar i organisationen måste du använda ett hanteringsverktyg för att distribuera den här inställningen till enheter i dina nätverk.</span><span class="sxs-lookup"><span data-stu-id="0b881-125">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="0b881-126">Du kan också använda grupprincip-, Intune- eller MDM-konfigurationstjänstleverantörer (MDM) för att konfigurera och distribuera inställningen.</span><span class="sxs-lookup"><span data-stu-id="0b881-126">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="0b881-127">Läs mer i huvudartikeln [om minskning av attackytor.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="0b881-127">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="0b881-128">Granska händelser för att minska attackytan i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="0b881-128">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="0b881-129">Om du vill granska appar som skulle ha blockerats öppnar du Loggboken och filtrerar efter Händelse-ID 1121 i Microsoft-Windows-Windows Defender/driftloggen.</span><span class="sxs-lookup"><span data-stu-id="0b881-129">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="0b881-130">I följande tabell visas alla nätverksskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="0b881-130">The following table lists all network protection events.</span></span>

<span data-ttu-id="0b881-131">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="0b881-131">Event ID</span></span> | <span data-ttu-id="0b881-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0b881-132">Description</span></span>
-|-
 <span data-ttu-id="0b881-133">5007</span><span class="sxs-lookup"><span data-stu-id="0b881-133">5007</span></span> | <span data-ttu-id="0b881-134">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="0b881-134">Event when settings are changed</span></span>
 <span data-ttu-id="0b881-135">1121</span><span class="sxs-lookup"><span data-stu-id="0b881-135">1121</span></span> | <span data-ttu-id="0b881-136">Händelse när en minskningsregel för attackytan av fires i blockläge</span><span class="sxs-lookup"><span data-stu-id="0b881-136">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="0b881-137">1122</span><span class="sxs-lookup"><span data-stu-id="0b881-137">1122</span></span> | <span data-ttu-id="0b881-138">Händelse när en minskningsregel för attackytan i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="0b881-138">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="0b881-139">Anpassa minskningsregler för attackytor</span><span class="sxs-lookup"><span data-stu-id="0b881-139">Customize attack surface reduction rules</span></span>

<span data-ttu-id="0b881-140">Under utvärderingen kanske du vill konfigurera varje regel individuellt eller exkludera vissa filer och processer från att utvärderas av funktionen.</span><span class="sxs-lookup"><span data-stu-id="0b881-140">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="0b881-141">Mer [information om hur du konfigurerar funktionen](customize-attack-surface-reduction.md) med hanteringsverktyg, bland annat Grupprincip och MDM-CSP-principer, finns i Anpassa minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="0b881-141">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b881-142">Se även</span><span class="sxs-lookup"><span data-stu-id="0b881-142">See also</span></span>

* [<span data-ttu-id="0b881-143">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="0b881-143">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="0b881-144">Använda granskningsläge för att utvärdera Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0b881-144">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="0b881-145">Vanliga frågor och svar om att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="0b881-145">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
