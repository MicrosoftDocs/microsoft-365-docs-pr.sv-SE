---
title: Skapa indikatorer för filer
ms.reviewer: ''
description: Skapa indikatorer för en filhash som definierar identifiering, skydd och undantag för enheter.
keywords: fil, hash, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730540"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="09c02-104">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="09c02-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09c02-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="09c02-105">**Applies to:**</span></span>
- [<span data-ttu-id="09c02-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="09c02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09c02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09c02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="09c02-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="09c02-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09c02-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="09c02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="09c02-110">Förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="09c02-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="09c02-111">Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den.</span><span class="sxs-lookup"><span data-stu-id="09c02-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="09c02-112">Den här åtgärden gör att den inte kan läsas, skrivas eller köras på enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="09c02-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="09c02-113">Du kan skapa indikatorer för filer på tre olika sätt:</span><span class="sxs-lookup"><span data-stu-id="09c02-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="09c02-114">Genom att skapa en indikator via inställningssidan</span><span class="sxs-lookup"><span data-stu-id="09c02-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="09c02-115">Genom att skapa en sammanhangsberoende indikator med knappen lägg till indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="09c02-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="09c02-116">Genom att skapa en indikator via [indikator-API:t](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="09c02-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="09c02-117">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="09c02-117">Before you begin</span></span>

<span data-ttu-id="09c02-118">Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för filer:</span><span class="sxs-lookup"><span data-stu-id="09c02-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="09c02-119">Den här funktionen är tillgänglig om din **organisation använder Microsoft Defender Antivirus (i aktivt läge) och** **molnbaserat skydd är aktiverat.**</span><span class="sxs-lookup"><span data-stu-id="09c02-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="09c02-120">Mer information finns i [Hantera molnbaserat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="09c02-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="09c02-121">Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="09c02-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="09c02-122">Se [Månadsplattform och motorversioner](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="09c02-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="09c02-123">Stöds på enheter med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.</span><span class="sxs-lookup"><span data-stu-id="09c02-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="09c02-124">För att börja blockera filer måste du först aktivera [funktionen "blockera eller tillåt" i](advanced-features.md) Inställningar.</span><span class="sxs-lookup"><span data-stu-id="09c02-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="09c02-125">Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben.</span><span class="sxs-lookup"><span data-stu-id="09c02-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="09c02-126">Det har för närvarande stöd för bärbara körbara (PE) filer, .exe och .dll filer.</span><span class="sxs-lookup"><span data-stu-id="09c02-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="09c02-127">Täckningen utökas med tiden.</span><span class="sxs-lookup"><span data-stu-id="09c02-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="09c02-128">Skapa en indikator för filer från inställningssidan</span><span class="sxs-lookup"><span data-stu-id="09c02-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="09c02-129">I navigeringsfönstret väljer du Inställningar > **Indikatorer**.</span><span class="sxs-lookup"><span data-stu-id="09c02-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="09c02-130">Välj fliken **Filhash.**  </span><span class="sxs-lookup"><span data-stu-id="09c02-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="09c02-131">Välj **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="09c02-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="09c02-132">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="09c02-132">Specify the following details:</span></span>
    - <span data-ttu-id="09c02-133">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="09c02-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="09c02-134">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="09c02-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="09c02-135">Omfattning – Definiera enhetens omfattning.</span><span class="sxs-lookup"><span data-stu-id="09c02-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="09c02-136">Granska informationen på fliken Sammanfattning och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="09c02-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="09c02-137">Skapa en sammanhangsberoende indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="09c02-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="09c02-138">Ett av alternativen när du vidtar [svarsåtgärder för en fil är](respond-file-alerts.md)att lägga till en indikator för   filen.</span><span class="sxs-lookup"><span data-stu-id="09c02-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="09c02-139">När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en enhet i organisationen försöker köra den.</span><span class="sxs-lookup"><span data-stu-id="09c02-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="09c02-140">Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.</span><span class="sxs-lookup"><span data-stu-id="09c02-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="09c02-141">Vanligtvis används filblock och tas bort inom några minuter, men det kan ta upp till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="09c02-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="09c02-142">Om det finns filindikatorprinciper som står i konflikt tillämpas den säkrare principens tillämpningsprincip.</span><span class="sxs-lookup"><span data-stu-id="09c02-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="09c02-143">En SHA-256-princip för hash-kod för filer har till exempel företräde framför en MD5-princip för hash-hash-kod för filer om båda hash-typerna definierar samma fil.</span><span class="sxs-lookup"><span data-stu-id="09c02-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="09c02-144">Om grupprincipen EnableFileHashComputation är inaktiverad minskar blockeringsprecisionen för filens IoC.</span><span class="sxs-lookup"><span data-stu-id="09c02-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="09c02-145">Men aktivering av EnableFileHashComputation kan påverka enhetens prestanda.</span><span class="sxs-lookup"><span data-stu-id="09c02-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="09c02-146">Till exempel kan kopiering av stora filer från en nätverksresurs till din lokala enhet, särskilt via en VPN-anslutning, påverka enhetens prestanda.</span><span class="sxs-lookup"><span data-stu-id="09c02-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="09c02-147">Mer information om grupprincipen EnableFileHashComputation finns i [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="09c02-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="09c02-148">Hantering av policykonflikter</span><span class="sxs-lookup"><span data-stu-id="09c02-148">Policy conflict handling</span></span>  

<span data-ttu-id="09c02-149">Konflikter i hanteringen av certifikat- och fil-IoC-policyer följer nedanstående ordning:</span><span class="sxs-lookup"><span data-stu-id="09c02-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="09c02-150">Om filen inte tillåts av Windows Defender programkontrollen och AppLocker-framtvinga-principen/-principerna blockerar **du**</span><span class="sxs-lookup"><span data-stu-id="09c02-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="09c02-151">Annars om filen tillåts av Microsoft Defender Antivirus och sedan **Tillåt**</span><span class="sxs-lookup"><span data-stu-id="09c02-151">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="09c02-152">Annars om filen blockeras eller varnas av ett block eller varnar fil-IoC ska du **blockera/varna**</span><span class="sxs-lookup"><span data-stu-id="09c02-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="09c02-153">Annars om filen tillåts av en IoC-princip för filen klickar du på **Tillåt**</span><span class="sxs-lookup"><span data-stu-id="09c02-153">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="09c02-154">Om filen annars blockeras av ASR-regler, CFA, AV, SmartScreen och sedan **Blockera**</span><span class="sxs-lookup"><span data-stu-id="09c02-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="09c02-155">Tillåt **annars** (skickar Windows Defender programkontroll & AppLocker-principen, inga IoC-regler gäller för den)</span><span class="sxs-lookup"><span data-stu-id="09c02-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="09c02-156">Om det finns IoC-principer i konflikt med samma tillämpningstyp och mål tillämpas principen för den säkrare hashen (vilket innebär längre).</span><span class="sxs-lookup"><span data-stu-id="09c02-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="09c02-157">En SHA-256-IoC-princip för filshashar vinner till exempel över en MD5-IoC-princip för filshashar om båda hashtyperna definierar samma fil.</span><span class="sxs-lookup"><span data-stu-id="09c02-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="09c02-158">Observera att Hantering av hot och säkerhetsrisker blockerat sårbart program använder fil-IoCs för tillämpning och kommer att följa den ordning som beskrivs ovan för hantering av konflikter.</span><span class="sxs-lookup"><span data-stu-id="09c02-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="09c02-159">Exempel</span><span class="sxs-lookup"><span data-stu-id="09c02-159">Examples</span></span>

|<span data-ttu-id="09c02-160">Komponent</span><span class="sxs-lookup"><span data-stu-id="09c02-160">Component</span></span> |<span data-ttu-id="09c02-161">Tillämpning av komponenter</span><span class="sxs-lookup"><span data-stu-id="09c02-161">Component enforcement</span></span> |<span data-ttu-id="09c02-162">Filindikatoråtgärd</span><span class="sxs-lookup"><span data-stu-id="09c02-162">File indicator Action</span></span> |<span data-ttu-id="09c02-163">Resultat</span><span class="sxs-lookup"><span data-stu-id="09c02-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="09c02-164">Undantag för filsökväg för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="09c02-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="09c02-165">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-165">Allow</span></span> |<span data-ttu-id="09c02-166">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-166">Block</span></span> |<span data-ttu-id="09c02-167">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-167">Block</span></span>
|<span data-ttu-id="09c02-168">Minskningsregel för attackytan</span><span class="sxs-lookup"><span data-stu-id="09c02-168">Attack surface reduction rule</span></span> |<span data-ttu-id="09c02-169">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-169">Block</span></span> |<span data-ttu-id="09c02-170">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-170">Allow</span></span> |<span data-ttu-id="09c02-171">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-171">Allow</span></span>
|<span data-ttu-id="09c02-172">Windows Defender-programreglering</span><span class="sxs-lookup"><span data-stu-id="09c02-172">Windows Defender Application Control</span></span> |<span data-ttu-id="09c02-173">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-173">Allow</span></span> |<span data-ttu-id="09c02-174">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-174">Block</span></span> |<span data-ttu-id="09c02-175">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-175">Allow</span></span> |
|<span data-ttu-id="09c02-176">Windows Defender-programreglering</span><span class="sxs-lookup"><span data-stu-id="09c02-176">Windows Defender Application Control</span></span> |<span data-ttu-id="09c02-177">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-177">Block</span></span> |<span data-ttu-id="09c02-178">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-178">Allow</span></span> |<span data-ttu-id="09c02-179">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-179">Block</span></span>
|<span data-ttu-id="09c02-180">Microsoft Defender Antivirus undantag</span><span class="sxs-lookup"><span data-stu-id="09c02-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="09c02-181">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-181">Allow</span></span> |<span data-ttu-id="09c02-182">Blockera</span><span class="sxs-lookup"><span data-stu-id="09c02-182">Block</span></span> |<span data-ttu-id="09c02-183">Tillåt</span><span class="sxs-lookup"><span data-stu-id="09c02-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="09c02-184">Se även</span><span class="sxs-lookup"><span data-stu-id="09c02-184">See also</span></span>

- [<span data-ttu-id="09c02-185">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="09c02-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="09c02-186">Skapa indikatorer för IP:er och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="09c02-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="09c02-187">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="09c02-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="09c02-188">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="09c02-188">Manage indicators</span></span>](indicator-manage.md)
