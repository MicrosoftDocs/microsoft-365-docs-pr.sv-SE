---
title: Läs mer om Microsofts Efterlevnadstillägg
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Med Microsofts Efterlevnadstillägg utökas övervakning och kontroll av filaktiviteter och skyddsåtgärder mot Google Chrome-webbläsaren
ms.openlocfilehash: b8d9be88f42cce736cdbf66a97f4363106fa5820
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730492"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="16617-103">Läs mer om Microsofts Efterlevnadstillägg</span><span class="sxs-lookup"><span data-stu-id="16617-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="16617-104">[Dataförlustskydd för slutpunkt (slutpunkt DLP)](endpoint-dlp-learn-about.md) utökar funktionerna för aktivitetsövervakning och skydd i [Microsoft 365 dataförlustskydd (DLP)](dlp-learn-about-dlp.md) till känsliga objekt som finns på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="16617-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="16617-105">När enheter har installerats i efterlevnadslösningar för Microsoft 365 blir informationen om vad användare gör med känsliga objekt synlig i [aktivitetsutforskaren](data-classification-activity-explorer.md) och du kan vidta skyddsåtgärder för dessa objekt via [DLP-principer](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="16617-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="16617-106">När Microsofts efterlevnadstillägg har installerats på en Windows 10-enhet kan organisationer övervaka när en användare försöker komma åt eller ladda upp ett känsligt objekt till en molntjänst med hjälp av Google Chrome och vidta skyddsåtgärder via DLP.</span><span class="sxs-lookup"><span data-stu-id="16617-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="16617-107">Aktiviteter som du kan övervaka och vidta åtgärder för</span><span class="sxs-lookup"><span data-stu-id="16617-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="16617-108">Med Microsofts efterlevnadstillägg kan du granska och hantera följande typer av aktiviteter som användare gör med känsliga objekt på enheter med Windows 10.</span><span class="sxs-lookup"><span data-stu-id="16617-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="16617-109">aktivitet</span><span class="sxs-lookup"><span data-stu-id="16617-109">activity</span></span> |<span data-ttu-id="16617-110">beskrivning</span><span class="sxs-lookup"><span data-stu-id="16617-110">description</span></span>  | <span data-ttu-id="16617-111">principåtgärder som stöds</span><span class="sxs-lookup"><span data-stu-id="16617-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="16617-112">fil kopierad till molnet</span><span class="sxs-lookup"><span data-stu-id="16617-112">file copied to cloud</span></span>  | <span data-ttu-id="16617-113">Identifierar när en användare försöker ladda upp ett känsligt objekt till en begränsad tjänstdomän via webbläsaren Chrome</span><span class="sxs-lookup"><span data-stu-id="16617-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="16617-114">granska, blockera</span><span class="sxs-lookup"><span data-stu-id="16617-114">audit, block</span></span>|
|<span data-ttu-id="16617-115">fil utskriven</span><span class="sxs-lookup"><span data-stu-id="16617-115">file printed</span></span>  |<span data-ttu-id="16617-116">Identifierar när en användare försöker skriva ut ett känsligt objekt som är öppet i webbläsaren Chrome till en lokal skrivare eller nätverksskrivare</span><span class="sxs-lookup"><span data-stu-id="16617-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="16617-117">granska, blockera med åsidosättning, blockera</span><span class="sxs-lookup"><span data-stu-id="16617-117">audit, block with override, block</span></span>|
|<span data-ttu-id="16617-118">fil kopierad till Urklipp</span><span class="sxs-lookup"><span data-stu-id="16617-118">file copied to clipboard</span></span> |<span data-ttu-id="16617-119">Identifierar när en användare försöker kopiera information från ett känsligt objekt som visas i webbläsaren Chrome och klistrar sedan in den i ett annat program, en annan process eller ett annat objekt.</span><span class="sxs-lookup"><span data-stu-id="16617-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="16617-120">granska, blockera med åsidosättning, blockera</span><span class="sxs-lookup"><span data-stu-id="16617-120">audit, block with override, block</span></span>|
|<span data-ttu-id="16617-121">fil kopierad till flyttbar lagring</span><span class="sxs-lookup"><span data-stu-id="16617-121">file copied to removable storage</span></span>    | <span data-ttu-id="16617-122">Identifierar när en användare försöker kopiera ett känsligt objekt eller information från ett känsligt objekt som är öppet i webbläsaren Chrome till ett flyttbart medium eller USB-enhet</span><span class="sxs-lookup"><span data-stu-id="16617-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="16617-123">granska, blockera med åsidosättning, blockera</span><span class="sxs-lookup"><span data-stu-id="16617-123">audit, block with override, block</span></span>|
|<span data-ttu-id="16617-124">fil kopierad till nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="16617-124">file copied to network share</span></span>  |<span data-ttu-id="16617-125">Identifierar när en användare försöker kopiera ett känsligt objekt eller information från ett känsligt objekt som är öppet i webbläsaren Chrome till en nätverksresurs eller mappad nätverksenhet.</span><span class="sxs-lookup"><span data-stu-id="16617-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="16617-126">granska, blockera med åsidosättning, blockera</span><span class="sxs-lookup"><span data-stu-id="16617-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="16617-127">Distributionsprocess</span><span class="sxs-lookup"><span data-stu-id="16617-127">Deployment process</span></span>
1. [<span data-ttu-id="16617-128">Komma igång med dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="16617-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="16617-129">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="16617-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="16617-130">Installera tillägget på dina Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="16617-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="16617-131">[Skapa eller redigera DLP-principer](create-test-tune-dlp-policy.md) som begränsar uppladdning till molntjänst eller åtkomst av icke-tillåtet webbläsaråtgärder och tillämpa dem på dina Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="16617-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="16617-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="16617-132">Next steps</span></span>

<span data-ttu-id="16617-133">Se [Komma igång med Microsofts Efterlevnadstillägg](dlp-chrome-get-started.md) för fullständiga distributionsprocedurer och scenarier.</span><span class="sxs-lookup"><span data-stu-id="16617-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="16617-134">Se även</span><span class="sxs-lookup"><span data-stu-id="16617-134">See also</span></span>

- [<span data-ttu-id="16617-135">Komma igång med Microsofts Efterlevnadstillägg</span><span class="sxs-lookup"><span data-stu-id="16617-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="16617-136">Läs mer om dataförlustskydd för slutpunkt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16617-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="16617-137">Komma igång med Microsoft dataförlustskydd för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="16617-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="16617-138">Använda Microsofts dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="16617-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="16617-139">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="16617-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="16617-140">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="16617-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="16617-141">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="16617-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="16617-142">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="16617-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="16617-143">Hantering av interna risker</span><span class="sxs-lookup"><span data-stu-id="16617-143">Insider Risk management</span></span>](insider-risk-management.md)
