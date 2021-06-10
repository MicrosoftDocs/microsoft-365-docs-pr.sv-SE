---
title: Ange inställningar för Microsoft Defender för Slutpunkt i Linux
ms.reviewer: ''
description: Här beskrivs hur du konfigurerar Microsoft Defender för Slutpunkt på Linux på företag.
keywords: microsoft, defender, Microsoft Defender för Endpoint, linux, installation, distribuera, avinstallation, installationse, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 00f6bdac66ae286bf55a875599f7097b14b06cb3
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861557"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7513-104">Ange inställningar för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="c7513-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c7513-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c7513-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7513-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7513-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7513-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7513-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7513-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c7513-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c7513-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c7513-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="c7513-110">Det här avsnittet innehåller instruktioner för hur du anger inställningar för Defender för Slutpunkt på Linux i företagsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="c7513-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="c7513-111">Om du är intresserad av att konfigurera produkten på en enhet från kommandoraden kan du gå till [Resurser](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c7513-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="c7513-112">I företagsmiljöer kan Defender för Slutpunkt i Linux hanteras via en konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="c7513-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="c7513-113">Den här profilen distribueras från valfri hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="c7513-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="c7513-114">Inställningar som hanteras av företaget har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="c7513-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="c7513-115">Med andra ord kan användarna i företaget inte ändra inställningar som anges i den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="c7513-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="c7513-116">I den här artikeln beskrivs profilens struktur (inklusive en rekommenderad profil som du kan använda för att komma igång) och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="c7513-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="c7513-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="c7513-117">Configuration profile structure</span></span>

<span data-ttu-id="c7513-118">Konfigurationsprofilen är en .json-fil som består av poster som identifieras av en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="c7513-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="c7513-119">Värdena kan vara enkla, till exempel numeriska värden eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="c7513-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="c7513-120">Vanligtvis använder du ett konfigurationsverktyg för att skicka en fil med ```mdatp_managed.json``` namnet på ```/etc/opt/microsoft/mdatp/managed/``` platsen.</span><span class="sxs-lookup"><span data-stu-id="c7513-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="c7513-121">Den översta nivån i konfigurationsprofilen omfattar produktomfattande inställningar och poster för underavsnitt av produkten, som förklaras mer detaljerat i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c7513-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="c7513-122">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="c7513-122">Antivirus engine preferences</span></span>

<span data-ttu-id="c7513-123">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i produkten.</span><span class="sxs-lookup"><span data-stu-id="c7513-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-124">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-124">**Key**</span></span> | <span data-ttu-id="c7513-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="c7513-125">antivirusEngine</span></span> |
| <span data-ttu-id="c7513-126">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-126">**Data type**</span></span> | <span data-ttu-id="c7513-127">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="c7513-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c7513-128">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-128">**Comments**</span></span> | <span data-ttu-id="c7513-129">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="c7513-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="c7513-130">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="c7513-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="c7513-131">Avgör om realtidsskydd (genomsökning av filer när de används) är aktiverat eller inte.</span><span class="sxs-lookup"><span data-stu-id="c7513-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-132">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-132">**Key**</span></span> | <span data-ttu-id="c7513-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="c7513-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="c7513-134">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-134">**Data type**</span></span> | <span data-ttu-id="c7513-135">Boolesk</span><span class="sxs-lookup"><span data-stu-id="c7513-135">Boolean</span></span> |
| <span data-ttu-id="c7513-136">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-136">**Possible values**</span></span> | <span data-ttu-id="c7513-137">true (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-137">true (default)</span></span> <br/> <span data-ttu-id="c7513-138">false</span><span class="sxs-lookup"><span data-stu-id="c7513-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="c7513-139">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="c7513-139">Enable / disable passive mode</span></span>

<span data-ttu-id="c7513-140">Avgör om antivirusmotorn körs i passiv form eller inte.</span><span class="sxs-lookup"><span data-stu-id="c7513-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="c7513-141">I passivt läge:</span><span class="sxs-lookup"><span data-stu-id="c7513-141">In passive mode:</span></span>
- <span data-ttu-id="c7513-142">Realtidsskydd är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="c7513-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="c7513-143">Skanning på begäran är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c7513-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="c7513-144">Automatisk åtgärd för hot är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="c7513-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="c7513-145">Säkerhetsintelligensuppdateringar aktiveras.</span><span class="sxs-lookup"><span data-stu-id="c7513-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="c7513-146">Statusmenyikonen är dold.</span><span class="sxs-lookup"><span data-stu-id="c7513-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-147">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-147">**Key**</span></span> | <span data-ttu-id="c7513-148">passivläge</span><span class="sxs-lookup"><span data-stu-id="c7513-148">passiveMode</span></span> |
| <span data-ttu-id="c7513-149">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-149">**Data type**</span></span> | <span data-ttu-id="c7513-150">Boolesk</span><span class="sxs-lookup"><span data-stu-id="c7513-150">Boolean</span></span> |
| <span data-ttu-id="c7513-151">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-151">**Possible values**</span></span> | <span data-ttu-id="c7513-152">false (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-152">false (default)</span></span> <br/> <span data-ttu-id="c7513-153">true</span><span class="sxs-lookup"><span data-stu-id="c7513-153">true</span></span> |
| <span data-ttu-id="c7513-154">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-154">**Comments**</span></span> | <span data-ttu-id="c7513-155">Tillgängligt i Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="c7513-156">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="c7513-156">Exclusion merge policy</span></span>

<span data-ttu-id="c7513-157">Anger kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="c7513-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="c7513-158">Det kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c7513-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="c7513-159">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="c7513-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-160">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-160">**Key**</span></span> | <span data-ttu-id="c7513-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c7513-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="c7513-162">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-162">**Data type**</span></span> | <span data-ttu-id="c7513-163">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-163">String</span></span> |
| <span data-ttu-id="c7513-164">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-164">**Possible values**</span></span> | <span data-ttu-id="c7513-165">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-165">merge (default)</span></span> <br/> <span data-ttu-id="c7513-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="c7513-166">admin_only</span></span> |
| <span data-ttu-id="c7513-167">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-167">**Comments**</span></span> | <span data-ttu-id="c7513-168">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="c7513-169">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="c7513-169">Scan exclusions</span></span>

<span data-ttu-id="c7513-170">Enheter som har uteslutits från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="c7513-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="c7513-171">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="c7513-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="c7513-172">(Undantag anges som en matris med objekt, administratören kan ange så många element som behövs, i valfri ordning.)</span><span class="sxs-lookup"><span data-stu-id="c7513-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-173">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-173">**Key**</span></span> | <span data-ttu-id="c7513-174">undantag</span><span class="sxs-lookup"><span data-stu-id="c7513-174">exclusions</span></span> |
| <span data-ttu-id="c7513-175">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-175">**Data type**</span></span> | <span data-ttu-id="c7513-176">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="c7513-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c7513-177">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-177">**Comments**</span></span> | <span data-ttu-id="c7513-178">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="c7513-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c7513-179">**Typ av undantag**</span><span class="sxs-lookup"><span data-stu-id="c7513-179">**Type of exclusion**</span></span>

<span data-ttu-id="c7513-180">Anger vilken typ av innehåll som undantas från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="c7513-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-181">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-181">**Key**</span></span> | <span data-ttu-id="c7513-182">$type</span><span class="sxs-lookup"><span data-stu-id="c7513-182">$type</span></span> |
| <span data-ttu-id="c7513-183">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-183">**Data type**</span></span> | <span data-ttu-id="c7513-184">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-184">String</span></span> |
| <span data-ttu-id="c7513-185">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-185">**Possible values**</span></span> | <span data-ttu-id="c7513-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="c7513-186">excludedPath</span></span> <br/> <span data-ttu-id="c7513-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="c7513-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="c7513-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="c7513-188">excludedFileName</span></span> |
|||

<span data-ttu-id="c7513-189">**Sökväg till utelämnat innehåll**</span><span class="sxs-lookup"><span data-stu-id="c7513-189">**Path to excluded content**</span></span>

<span data-ttu-id="c7513-190">Används för att utesluta innehåll från genomsökningen genom den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="c7513-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-191">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-191">**Key**</span></span> | <span data-ttu-id="c7513-192">sökväg</span><span class="sxs-lookup"><span data-stu-id="c7513-192">path</span></span> |
| <span data-ttu-id="c7513-193">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-193">**Data type**</span></span> | <span data-ttu-id="c7513-194">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-194">String</span></span> |
| <span data-ttu-id="c7513-195">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-195">**Possible values**</span></span> | <span data-ttu-id="c7513-196">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="c7513-196">valid paths</span></span> |
| <span data-ttu-id="c7513-197">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-197">**Comments**</span></span> | <span data-ttu-id="c7513-198">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="c7513-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c7513-199">**Sökvägstyp (fil/katalog)**</span><span class="sxs-lookup"><span data-stu-id="c7513-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="c7513-200">Anger om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="c7513-200">Indicates if the *path* property refers to a file or directory.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-201">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-201">**Key**</span></span> | <span data-ttu-id="c7513-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="c7513-202">isDirectory</span></span> |
| <span data-ttu-id="c7513-203">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-203">**Data type**</span></span> | <span data-ttu-id="c7513-204">Boolesk</span><span class="sxs-lookup"><span data-stu-id="c7513-204">Boolean</span></span> |
| <span data-ttu-id="c7513-205">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-205">**Possible values**</span></span> | <span data-ttu-id="c7513-206">false (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-206">false (default)</span></span> <br/> <span data-ttu-id="c7513-207">true</span><span class="sxs-lookup"><span data-stu-id="c7513-207">true</span></span> |
| <span data-ttu-id="c7513-208">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-208">**Comments**</span></span> | <span data-ttu-id="c7513-209">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="c7513-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c7513-210">**Filnamnstillägget är undantaget från genomsökningen**</span><span class="sxs-lookup"><span data-stu-id="c7513-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="c7513-211">Används för att utesluta innehåll från genomsökningen efter filnamnstillägget.</span><span class="sxs-lookup"><span data-stu-id="c7513-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-212">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-212">**Key**</span></span> | <span data-ttu-id="c7513-213">tillägg</span><span class="sxs-lookup"><span data-stu-id="c7513-213">extension</span></span> |
| <span data-ttu-id="c7513-214">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-214">**Data type**</span></span> | <span data-ttu-id="c7513-215">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-215">String</span></span> |
| <span data-ttu-id="c7513-216">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-216">**Possible values**</span></span> | <span data-ttu-id="c7513-217">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="c7513-217">valid file extensions</span></span> |
| <span data-ttu-id="c7513-218">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-218">**Comments**</span></span> | <span data-ttu-id="c7513-219">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="c7513-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="c7513-220">**Process som uteslutits från genomsökningen**</span><span class="sxs-lookup"><span data-stu-id="c7513-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="c7513-221">Anger en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="c7513-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="c7513-222">Processen kan antingen anges med sitt namn (till exempel `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="c7513-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-223">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-223">**Key**</span></span> | <span data-ttu-id="c7513-224">Namn</span><span class="sxs-lookup"><span data-stu-id="c7513-224">name</span></span> |
| <span data-ttu-id="c7513-225">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-225">**Data type**</span></span> | <span data-ttu-id="c7513-226">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-226">String</span></span> |
| <span data-ttu-id="c7513-227">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-227">**Possible values**</span></span> | <span data-ttu-id="c7513-228">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-228">any string</span></span> |
| <span data-ttu-id="c7513-229">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-229">**Comments**</span></span> | <span data-ttu-id="c7513-230">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="c7513-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="c7513-231">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="c7513-231">Allowed threats</span></span>

<span data-ttu-id="c7513-232">Lista över hot (identifieras med namnet) som inte blockeras av produkten och i stället får köras.</span><span class="sxs-lookup"><span data-stu-id="c7513-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-233">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-233">**Key**</span></span> | <span data-ttu-id="c7513-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="c7513-234">allowedThreats</span></span> |
| <span data-ttu-id="c7513-235">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-235">**Data type**</span></span> | <span data-ttu-id="c7513-236">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="c7513-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="c7513-237">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="c7513-237">Disallowed threat actions</span></span>

<span data-ttu-id="c7513-238">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="c7513-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="c7513-239">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="c7513-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-240">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-240">**Key**</span></span> | <span data-ttu-id="c7513-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="c7513-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="c7513-242">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-242">**Data type**</span></span> | <span data-ttu-id="c7513-243">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="c7513-243">Array of strings</span></span> |
| <span data-ttu-id="c7513-244">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-244">**Possible values**</span></span> | <span data-ttu-id="c7513-245">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="c7513-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="c7513-246">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="c7513-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="c7513-247">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-247">**Comments**</span></span> | <span data-ttu-id="c7513-248">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="c7513-249">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="c7513-249">Threat type settings</span></span>

<span data-ttu-id="c7513-250">Inställningen *för threatTypeSettings* i antivirusmotorn används för att styra hur vissa hottyper hanteras av produkten.</span><span class="sxs-lookup"><span data-stu-id="c7513-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-251">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-251">**Key**</span></span> | <span data-ttu-id="c7513-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="c7513-252">threatTypeSettings</span></span> |
| <span data-ttu-id="c7513-253">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-253">**Data type**</span></span> | <span data-ttu-id="c7513-254">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="c7513-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c7513-255">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-255">**Comments**</span></span> | <span data-ttu-id="c7513-256">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="c7513-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c7513-257">**Hottyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-257">**Threat type**</span></span>

<span data-ttu-id="c7513-258">Typ av hot som beteendet är konfigurerat för.</span><span class="sxs-lookup"><span data-stu-id="c7513-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-259">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-259">**Key**</span></span> | <span data-ttu-id="c7513-260">tangent</span><span class="sxs-lookup"><span data-stu-id="c7513-260">key</span></span> |
| <span data-ttu-id="c7513-261">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-261">**Data type**</span></span> | <span data-ttu-id="c7513-262">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-262">String</span></span> |
| <span data-ttu-id="c7513-263">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-263">**Possible values**</span></span> | <span data-ttu-id="c7513-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="c7513-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="c7513-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="c7513-265">archive_bomb</span></span> |
|||

<span data-ttu-id="c7513-266">**Åtgärd att vidta**</span><span class="sxs-lookup"><span data-stu-id="c7513-266">**Action to take**</span></span>

<span data-ttu-id="c7513-267">Åtgärd att vidta när de kommer över en typ av hot som anges i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c7513-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="c7513-268">Kan vara:</span><span class="sxs-lookup"><span data-stu-id="c7513-268">Can be:</span></span>

- <span data-ttu-id="c7513-269">**Granskning:** Enheten är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="c7513-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="c7513-270">**Blockering:** Enheten är skyddad mot den här typen av hot och du meddelas i säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="c7513-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="c7513-271">**Av:** Enheten är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="c7513-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-272">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-272">**Key**</span></span> | <span data-ttu-id="c7513-273">värde</span><span class="sxs-lookup"><span data-stu-id="c7513-273">value</span></span> |
| <span data-ttu-id="c7513-274">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-274">**Data type**</span></span> | <span data-ttu-id="c7513-275">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-275">String</span></span> |
| <span data-ttu-id="c7513-276">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-276">**Possible values**</span></span> | <span data-ttu-id="c7513-277">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-277">audit (default)</span></span> <br/> <span data-ttu-id="c7513-278">blockera</span><span class="sxs-lookup"><span data-stu-id="c7513-278">block</span></span> <br/> <span data-ttu-id="c7513-279">av</span><span class="sxs-lookup"><span data-stu-id="c7513-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="c7513-280">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="c7513-280">Threat type settings merge policy</span></span>

<span data-ttu-id="c7513-281">Anger kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="c7513-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="c7513-282">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c7513-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="c7513-283">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="c7513-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-284">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-284">**Key**</span></span> | <span data-ttu-id="c7513-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c7513-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="c7513-286">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-286">**Data type**</span></span> | <span data-ttu-id="c7513-287">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-287">String</span></span> |
| <span data-ttu-id="c7513-288">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-288">**Possible values**</span></span> | <span data-ttu-id="c7513-289">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-289">merge (default)</span></span> <br/> <span data-ttu-id="c7513-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="c7513-290">admin_only</span></span> |
| <span data-ttu-id="c7513-291">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-291">**Comments**</span></span> | <span data-ttu-id="c7513-292">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="c7513-293">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="c7513-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="c7513-294">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="c7513-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="c7513-295">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="c7513-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="c7513-296">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="c7513-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-297">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-297">**Key**</span></span> | <span data-ttu-id="c7513-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="c7513-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="c7513-299">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-299">**Data type**</span></span> | <span data-ttu-id="c7513-300">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-300">String</span></span> |
| <span data-ttu-id="c7513-301">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-301">**Possible values**</span></span> | <span data-ttu-id="c7513-302">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="c7513-302">90 (default).</span></span> <span data-ttu-id="c7513-303">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="c7513-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="c7513-304">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-304">**Comments**</span></span> | <span data-ttu-id="c7513-305">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="c7513-306">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="c7513-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="c7513-307">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="c7513-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="c7513-308">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="c7513-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-309">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-309">**Key**</span></span> | <span data-ttu-id="c7513-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="c7513-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="c7513-311">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-311">**Data type**</span></span> | <span data-ttu-id="c7513-312">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-312">String</span></span> |
| <span data-ttu-id="c7513-313">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-313">**Possible values**</span></span> | <span data-ttu-id="c7513-314">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="c7513-314">10000 (default).</span></span> <span data-ttu-id="c7513-315">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="c7513-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="c7513-316">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-316">**Comments**</span></span> | <span data-ttu-id="c7513-317">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7513-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="c7513-318">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="c7513-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="c7513-319">*CloudService-posten* i konfigurationsprofilen används för att konfigurera produktens molndrivna skyddsfunktion.</span><span class="sxs-lookup"><span data-stu-id="c7513-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-320">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-320">**Key**</span></span> | <span data-ttu-id="c7513-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="c7513-321">cloudService</span></span> |
| <span data-ttu-id="c7513-322">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-322">**Data type**</span></span> | <span data-ttu-id="c7513-323">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="c7513-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c7513-324">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c7513-324">**Comments**</span></span> | <span data-ttu-id="c7513-325">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="c7513-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="c7513-326">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="c7513-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="c7513-327">Avgör om moln levererat skydd är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="c7513-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="c7513-328">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="c7513-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-329">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-329">**Key**</span></span> | <span data-ttu-id="c7513-330">aktiverat</span><span class="sxs-lookup"><span data-stu-id="c7513-330">enabled</span></span> |
| <span data-ttu-id="c7513-331">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-331">**Data type**</span></span> | <span data-ttu-id="c7513-332">Boolesk</span><span class="sxs-lookup"><span data-stu-id="c7513-332">Boolean</span></span> |
| <span data-ttu-id="c7513-333">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-333">**Possible values**</span></span> | <span data-ttu-id="c7513-334">true (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-334">true (default)</span></span> <br/> <span data-ttu-id="c7513-335">false</span><span class="sxs-lookup"><span data-stu-id="c7513-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="c7513-336">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="c7513-336">Diagnostic collection level</span></span>

<span data-ttu-id="c7513-337">Diagnostikdata används för att hålla Defender för Slutpunkt säker och uppdaterad, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="c7513-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="c7513-338">Den här inställningen bestämmer nivån för diagnostik som skickas av produkten till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7513-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-339">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-339">**Key**</span></span> | <span data-ttu-id="c7513-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="c7513-340">diagnosticLevel</span></span> |
| <span data-ttu-id="c7513-341">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-341">**Data type**</span></span> | <span data-ttu-id="c7513-342">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-342">String</span></span> |
| <span data-ttu-id="c7513-343">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-343">**Possible values**</span></span> | <span data-ttu-id="c7513-344">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-344">optional (default)</span></span> <br/> <span data-ttu-id="c7513-345">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="c7513-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="c7513-346">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="c7513-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="c7513-347">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7513-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="c7513-348">Det finns tre nivåer för kontroll av exempelinskick:</span><span class="sxs-lookup"><span data-stu-id="c7513-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="c7513-349">**Ingen**: inga misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7513-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="c7513-350">**Valv**: endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c7513-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="c7513-351">Det här är standardvärdet för den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="c7513-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="c7513-352">**Alla**: alla misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7513-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-353">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-353">**Key**</span></span> | <span data-ttu-id="c7513-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="c7513-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="c7513-355">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-355">**Data type**</span></span> | <span data-ttu-id="c7513-356">Sträng</span><span class="sxs-lookup"><span data-stu-id="c7513-356">String</span></span> |
| <span data-ttu-id="c7513-357">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-357">**Possible values**</span></span> | <span data-ttu-id="c7513-358">none (ingen)</span><span class="sxs-lookup"><span data-stu-id="c7513-358">none</span></span> <br/> <span data-ttu-id="c7513-359">kassaskåp (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-359">safe (default)</span></span> <br/> <span data-ttu-id="c7513-360">alla</span><span class="sxs-lookup"><span data-stu-id="c7513-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="c7513-361">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="c7513-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="c7513-362">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="c7513-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="c7513-363">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="c7513-363">**Key**</span></span> | <span data-ttu-id="c7513-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="c7513-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="c7513-365">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="c7513-365">**Data type**</span></span> | <span data-ttu-id="c7513-366">Boolesk</span><span class="sxs-lookup"><span data-stu-id="c7513-366">Boolean</span></span> |
| <span data-ttu-id="c7513-367">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="c7513-367">**Possible values**</span></span> | <span data-ttu-id="c7513-368">true (standard)</span><span class="sxs-lookup"><span data-stu-id="c7513-368">true (default)</span></span> <br/> <span data-ttu-id="c7513-369">false</span><span class="sxs-lookup"><span data-stu-id="c7513-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="c7513-370">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="c7513-370">Recommended configuration profile</span></span>

<span data-ttu-id="c7513-371">För att komma igång rekommenderar vi följande konfigurationsprofil för ditt företag för att kunna dra nytta av alla skyddsfunktioner som Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="c7513-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="c7513-372">Följande konfigurationsprofil:</span><span class="sxs-lookup"><span data-stu-id="c7513-372">The following configuration profile will:</span></span>

- <span data-ttu-id="c7513-373">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="c7513-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="c7513-374">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="c7513-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="c7513-375">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="c7513-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="c7513-376">**Arkivposterna** (fil med hög komprimeringshastighet) granskas i produktloggarna</span><span class="sxs-lookup"><span data-stu-id="c7513-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="c7513-377">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="c7513-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="c7513-378">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="c7513-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="c7513-379">Aktivera automatisk exempelinskick på `safe` nivå</span><span class="sxs-lookup"><span data-stu-id="c7513-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="c7513-380">Exempelprofil</span><span class="sxs-lookup"><span data-stu-id="c7513-380">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="c7513-381">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="c7513-381">Full configuration profile example</span></span>

<span data-ttu-id="c7513-382">Följande konfigurationsprofil innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över produkten.</span><span class="sxs-lookup"><span data-stu-id="c7513-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="c7513-383">Fullständig profil</span><span class="sxs-lookup"><span data-stu-id="c7513-383">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="c7513-384">Validering av konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="c7513-384">Configuration profile validation</span></span>

<span data-ttu-id="c7513-385">Konfigurationsprofilen måste vara en giltig JSON-formaterad fil.</span><span class="sxs-lookup"><span data-stu-id="c7513-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="c7513-386">Det finns ett antal verktyg som kan användas för att verifiera detta.</span><span class="sxs-lookup"><span data-stu-id="c7513-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="c7513-387">Om du till exempel har `python` installerat på enheten:</span><span class="sxs-lookup"><span data-stu-id="c7513-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="c7513-388">Om JSON-koden är rätt utformad matar kommandot ovan ut den tillbaka till terminalen och returnerar en utgångskod för `0` .</span><span class="sxs-lookup"><span data-stu-id="c7513-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="c7513-389">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="c7513-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="c7513-390">Verifiera att filen mdatp_managed.jsfungerar som förväntat</span><span class="sxs-lookup"><span data-stu-id="c7513-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="c7513-391">Kontrollera att din /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfungerar korrekt genom att se "[managed]" bredvid de här inställningarna:</span><span class="sxs-lookup"><span data-stu-id="c7513-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>
- <span data-ttu-id="c7513-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="c7513-392">cloud_enabled</span></span>
- <span data-ttu-id="c7513-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="c7513-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="c7513-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="c7513-394">passice_mode_enabled</span></span>
- <span data-ttu-id="c7513-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="c7513-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="c7513-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="c7513-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="c7513-397">För mdatp_managed.jsatt börja gälla krävs ingen omstart av wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="c7513-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="c7513-398">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="c7513-398">Configuration profile deployment</span></span>

<span data-ttu-id="c7513-399">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via det hanteringsverktyg som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="c7513-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="c7513-400">Defender för slutpunkt i Linux läser den hanterade konfigurationen från *filen /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="c7513-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
