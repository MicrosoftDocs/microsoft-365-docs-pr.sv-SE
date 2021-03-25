---
title: Utvärdera kontrollerad mappåtkomst
description: Se hur reglerad mappåtkomst kan skydda filer från att ändras av skadliga program.
keywords: Sårbarhetsskydd, windows 10, windows defender, utpressningstrojaner, skydda, utvärdera, testa, demo, prova
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
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218754"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="be7ec-104">Utvärdera kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="be7ec-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="be7ec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="be7ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="be7ec-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="be7ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="be7ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be7ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="be7ec-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="be7ec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="be7ec-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="be7ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="be7ec-110">[Kontrollerad mappåtkomst](controlled-folders.md) är en funktion som skyddar dokument och filer från att ändras av misstänkta eller skadliga program.</span><span class="sxs-lookup"><span data-stu-id="be7ec-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="be7ec-111">Reglerad mappåtkomst stöds i Windows Server 2019- och Windows 10-klienter.</span><span class="sxs-lookup"><span data-stu-id="be7ec-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="be7ec-112">Det är särskilt användbart för att skydda mot [utpressningstrojaner](https://www.microsoft.com/wdsi/threats/ransomware) som försöker kryptera dina filer och hålla kvar dem.</span><span class="sxs-lookup"><span data-stu-id="be7ec-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="be7ec-113">I den här artikeln får du hjälp att utvärdera kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="be7ec-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="be7ec-114">Här förklaras hur du aktiverar granskningsläge så att du kan testa funktionen direkt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="be7ec-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="be7ec-115">Du kan också besöka webbplatsen med microsoft Defender för slutpunktsdemonstration på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="be7ec-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="be7ec-116">Använd granskningsläge för att mäta påverkan</span><span class="sxs-lookup"><span data-stu-id="be7ec-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="be7ec-117">Aktivera kontrollerad mappåtkomst i granskningsläge för att se en post över vad *som skulle* ha hänt om det var helt aktiverat.</span><span class="sxs-lookup"><span data-stu-id="be7ec-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="be7ec-118">Testa hur funktionen fungerar i din organisation för att säkerställa att den inte påverkar dina verksamhetsbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="be7ec-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="be7ec-119">Du kan också få en uppfattning om hur många misstänkta filändringsförsök som vanligtvis görs under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="be7ec-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="be7ec-120">Om du vill aktivera granskningsläge använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="be7ec-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="be7ec-121">Om du vill granska hur kontrollerad mappåtkomst fungerar i organisationen måste du använda ett hanteringsverktyg för att distribuera den här inställningen till enheter i dina nätverk.</span><span class="sxs-lookup"><span data-stu-id="be7ec-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="be7ec-122">Du kan också använda Grupprincip, Intune, MDM (Mobile Device Management) eller Microsoft Endpoint Manager för att konfigurera och distribuera inställningen enligt beskrivningen i avsnittet huvudkontrollerad [mappåtkomst.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="be7ec-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="be7ec-123">Granska styrda mappåtkomsthändelser i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="be7ec-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="be7ec-124">Följande mappåtkomsthändelser som kontrolleras visas i Windows Loggboken under mappen Microsoft/Windows/Windows Defender/Drift.</span><span class="sxs-lookup"><span data-stu-id="be7ec-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="be7ec-125">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="be7ec-125">Event ID</span></span> | <span data-ttu-id="be7ec-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="be7ec-126">Description</span></span>
-|-
 <span data-ttu-id="be7ec-127">5007</span><span class="sxs-lookup"><span data-stu-id="be7ec-127">5007</span></span> | <span data-ttu-id="be7ec-128">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="be7ec-128">Event when settings are changed</span></span>
 <span data-ttu-id="be7ec-129">1124</span><span class="sxs-lookup"><span data-stu-id="be7ec-129">1124</span></span> | <span data-ttu-id="be7ec-130">Granskad kontrollerad mappåtkomsthändelse</span><span class="sxs-lookup"><span data-stu-id="be7ec-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="be7ec-131">1123</span><span class="sxs-lookup"><span data-stu-id="be7ec-131">1123</span></span> | <span data-ttu-id="be7ec-132">Blockerad reglerad mappåtkomsthändelse</span><span class="sxs-lookup"><span data-stu-id="be7ec-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="be7ec-133">Du kan konfigurera en prenumeration [på vidarebefordran av händelser så](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) att loggarna samlas in centralt.</span><span class="sxs-lookup"><span data-stu-id="be7ec-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="be7ec-134">Anpassa skyddade mappar och appar</span><span class="sxs-lookup"><span data-stu-id="be7ec-134">Customize protected folders and apps</span></span>

<span data-ttu-id="be7ec-135">Under utvärderingen kanske du vill lägga till i listan med skyddade mappar eller tillåta att vissa appar ändrar filer.</span><span class="sxs-lookup"><span data-stu-id="be7ec-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="be7ec-136">Se [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md) för att konfigurera funktionen med hanteringsverktyg, inklusive grupprinciper, PowerShell- och MDM-konfigurationstjänstleverantörer (CSP).</span><span class="sxs-lookup"><span data-stu-id="be7ec-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="be7ec-137">Se även</span><span class="sxs-lookup"><span data-stu-id="be7ec-137">See also</span></span>

* [<span data-ttu-id="be7ec-138">Skydda viktiga mappar med kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="be7ec-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="be7ec-139">Utvärdera Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="be7ec-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="be7ec-140">Använda granskningsläge</span><span class="sxs-lookup"><span data-stu-id="be7ec-140">Use audit mode</span></span>](audit-windows-defender.md)
