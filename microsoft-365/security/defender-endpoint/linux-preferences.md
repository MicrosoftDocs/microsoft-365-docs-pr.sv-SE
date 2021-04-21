---
title: Ange inställningar för Microsoft Defender för Slutpunkt i Linux
ms.reviewer: ''
description: Här beskrivs hur du konfigurerar Microsoft Defender för Slutpunkt på Linux på företag.
keywords: microsoft, defender, atp, linux, installation, distribuera, avinstallation, enkel, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
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
ms.openlocfilehash: 2c162d652656afb61f1d74bad9ec963825d25a14
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903876"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5a76d-104">Ange inställningar för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="5a76d-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5a76d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5a76d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a76d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5a76d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a76d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a76d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5a76d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5a76d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5a76d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5a76d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="5a76d-110">Det här avsnittet innehåller instruktioner för hur du anger inställningar för Defender för Slutpunkt för Linux i företagsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="5a76d-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="5a76d-111">Om du är intresserad av att konfigurera produkten på en enhet från kommandoraden kan du gå till [Resurser](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5a76d-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="5a76d-112">I företagsmiljöer kan Defender för Endpoint för Linux hanteras via en konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="5a76d-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="5a76d-113">Den här profilen distribueras från valfri hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="5a76d-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="5a76d-114">Inställningar som hanteras av företaget har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="5a76d-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="5a76d-115">Med andra ord kan användarna i företaget inte ändra inställningar som anges i den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="5a76d-116">I den här artikeln beskrivs profilens struktur (inklusive en rekommenderad profil som du kan använda för att komma igång) och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="5a76d-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="5a76d-117">Configuration profile structure</span></span>

<span data-ttu-id="5a76d-118">Konfigurationsprofilen är en .json-fil som består av poster som identifieras av en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="5a76d-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="5a76d-119">Värdena kan vara enkla, till exempel numeriska värden eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="5a76d-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="5a76d-120">Vanligtvis använder du ett konfigurationsverktyg för att skicka en fil med ```mdatp_managed.json``` namnet på ```/etc/opt/microsoft/mdatp/managed/``` platsen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="5a76d-121">Den översta nivån i konfigurationsprofilen omfattar produktomfattande inställningar och poster för underavsnitt av produkten, som förklaras mer detaljerat i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="5a76d-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="5a76d-122">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="5a76d-122">Antivirus engine preferences</span></span>

<span data-ttu-id="5a76d-123">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i produkten.</span><span class="sxs-lookup"><span data-stu-id="5a76d-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-124">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-124">**Key**</span></span> | <span data-ttu-id="5a76d-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="5a76d-125">antivirusEngine</span></span> |
| <span data-ttu-id="5a76d-126">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-126">**Data type**</span></span> | <span data-ttu-id="5a76d-127">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a76d-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a76d-128">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-128">**Comments**</span></span> | <span data-ttu-id="5a76d-129">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a76d-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="5a76d-130">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="5a76d-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="5a76d-131">Avgör om realtidsskydd (genomsökning av filer när de används) är aktiverat eller inte.</span><span class="sxs-lookup"><span data-stu-id="5a76d-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-132">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-132">**Key**</span></span> | <span data-ttu-id="5a76d-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="5a76d-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="5a76d-134">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-134">**Data type**</span></span> | <span data-ttu-id="5a76d-135">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5a76d-135">Boolean</span></span> |
| <span data-ttu-id="5a76d-136">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-136">**Possible values**</span></span> | <span data-ttu-id="5a76d-137">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-137">true (default)</span></span> <br/> <span data-ttu-id="5a76d-138">false</span><span class="sxs-lookup"><span data-stu-id="5a76d-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="5a76d-139">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="5a76d-139">Enable / disable passive mode</span></span>

<span data-ttu-id="5a76d-140">Avgör om antivirusmotorn körs i passiv form eller inte.</span><span class="sxs-lookup"><span data-stu-id="5a76d-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="5a76d-141">I passivt läge:</span><span class="sxs-lookup"><span data-stu-id="5a76d-141">In passive mode:</span></span>
- <span data-ttu-id="5a76d-142">Realtidsskydd är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="5a76d-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="5a76d-143">Skanning på begäran är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5a76d-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="5a76d-144">Automatisk åtgärd för hot är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="5a76d-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="5a76d-145">Säkerhetsintelligensuppdateringar aktiveras.</span><span class="sxs-lookup"><span data-stu-id="5a76d-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="5a76d-146">Statusmenyikonen är dold.</span><span class="sxs-lookup"><span data-stu-id="5a76d-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-147">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-147">**Key**</span></span> | <span data-ttu-id="5a76d-148">passivläge</span><span class="sxs-lookup"><span data-stu-id="5a76d-148">passiveMode</span></span> |
| <span data-ttu-id="5a76d-149">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-149">**Data type**</span></span> | <span data-ttu-id="5a76d-150">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5a76d-150">Boolean</span></span> |
| <span data-ttu-id="5a76d-151">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-151">**Possible values**</span></span> | <span data-ttu-id="5a76d-152">false (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-152">false (default)</span></span> <br/> <span data-ttu-id="5a76d-153">true</span><span class="sxs-lookup"><span data-stu-id="5a76d-153">true</span></span> |
| <span data-ttu-id="5a76d-154">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-154">**Comments**</span></span> | <span data-ttu-id="5a76d-155">Tillgängligt i Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="5a76d-156">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="5a76d-156">Exclusion merge policy</span></span>

<span data-ttu-id="5a76d-157">Anger kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="5a76d-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="5a76d-158">Det kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5a76d-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="5a76d-159">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="5a76d-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-160">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-160">**Key**</span></span> | <span data-ttu-id="5a76d-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5a76d-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="5a76d-162">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-162">**Data type**</span></span> | <span data-ttu-id="5a76d-163">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-163">String</span></span> |
| <span data-ttu-id="5a76d-164">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-164">**Possible values**</span></span> | <span data-ttu-id="5a76d-165">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-165">merge (default)</span></span> <br/> <span data-ttu-id="5a76d-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="5a76d-166">admin_only</span></span> |
| <span data-ttu-id="5a76d-167">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-167">**Comments**</span></span> | <span data-ttu-id="5a76d-168">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="5a76d-169">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="5a76d-169">Scan exclusions</span></span>

<span data-ttu-id="5a76d-170">Enheter som har uteslutits från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="5a76d-171">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="5a76d-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-172">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-172">**Key**</span></span> | <span data-ttu-id="5a76d-173">undantag</span><span class="sxs-lookup"><span data-stu-id="5a76d-173">exclusions</span></span> |
| <span data-ttu-id="5a76d-174">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-174">**Data type**</span></span> | <span data-ttu-id="5a76d-175">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a76d-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a76d-176">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-176">**Comments**</span></span> | <span data-ttu-id="5a76d-177">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a76d-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="5a76d-178">**Typ av undantag**</span><span class="sxs-lookup"><span data-stu-id="5a76d-178">**Type of exclusion**</span></span>

<span data-ttu-id="5a76d-179">Anger vilken typ av innehåll som undantas från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-180">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-180">**Key**</span></span> | <span data-ttu-id="5a76d-181">$type</span><span class="sxs-lookup"><span data-stu-id="5a76d-181">$type</span></span> |
| <span data-ttu-id="5a76d-182">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-182">**Data type**</span></span> | <span data-ttu-id="5a76d-183">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-183">String</span></span> |
| <span data-ttu-id="5a76d-184">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-184">**Possible values**</span></span> | <span data-ttu-id="5a76d-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="5a76d-185">excludedPath</span></span> <br/> <span data-ttu-id="5a76d-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="5a76d-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="5a76d-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="5a76d-187">excludedFileName</span></span> |
|||

<span data-ttu-id="5a76d-188">**Sökväg till utelämnat innehåll**</span><span class="sxs-lookup"><span data-stu-id="5a76d-188">**Path to excluded content**</span></span>

<span data-ttu-id="5a76d-189">Används för att utesluta innehåll från genomsökningen genom den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-190">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-190">**Key**</span></span> | <span data-ttu-id="5a76d-191">sökväg</span><span class="sxs-lookup"><span data-stu-id="5a76d-191">path</span></span> |
| <span data-ttu-id="5a76d-192">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-192">**Data type**</span></span> | <span data-ttu-id="5a76d-193">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-193">String</span></span> |
| <span data-ttu-id="5a76d-194">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-194">**Possible values**</span></span> | <span data-ttu-id="5a76d-195">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="5a76d-195">valid paths</span></span> |
| <span data-ttu-id="5a76d-196">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-196">**Comments**</span></span> | <span data-ttu-id="5a76d-197">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="5a76d-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="5a76d-198">**Sökvägstyp (fil/katalog)**</span><span class="sxs-lookup"><span data-stu-id="5a76d-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="5a76d-199">Anger om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="5a76d-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="5a76d-200">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-200">**Key**</span></span> | <span data-ttu-id="5a76d-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="5a76d-201">isDirectory</span></span> |
| <span data-ttu-id="5a76d-202">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-202">**Data type**</span></span> | <span data-ttu-id="5a76d-203">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5a76d-203">Boolean</span></span> |
| <span data-ttu-id="5a76d-204">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-204">**Possible values**</span></span> | <span data-ttu-id="5a76d-205">false (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-205">false (default)</span></span> <br/> <span data-ttu-id="5a76d-206">true</span><span class="sxs-lookup"><span data-stu-id="5a76d-206">true</span></span> |
| <span data-ttu-id="5a76d-207">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-207">**Comments**</span></span> | <span data-ttu-id="5a76d-208">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="5a76d-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="5a76d-209">**Filnamnstillägget är undantaget från genomsökningen**</span><span class="sxs-lookup"><span data-stu-id="5a76d-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="5a76d-210">Används för att utesluta innehåll från genomsökningen efter filnamnstillägget.</span><span class="sxs-lookup"><span data-stu-id="5a76d-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-211">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-211">**Key**</span></span> | <span data-ttu-id="5a76d-212">tillägg</span><span class="sxs-lookup"><span data-stu-id="5a76d-212">extension</span></span> |
| <span data-ttu-id="5a76d-213">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-213">**Data type**</span></span> | <span data-ttu-id="5a76d-214">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-214">String</span></span> |
| <span data-ttu-id="5a76d-215">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-215">**Possible values**</span></span> | <span data-ttu-id="5a76d-216">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="5a76d-216">valid file extensions</span></span> |
| <span data-ttu-id="5a76d-217">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-217">**Comments**</span></span> | <span data-ttu-id="5a76d-218">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="5a76d-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="5a76d-219">**Process som uteslutits från genomsökningen**</span><span class="sxs-lookup"><span data-stu-id="5a76d-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="5a76d-220">Anger en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="5a76d-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="5a76d-221">Processen kan antingen anges med sitt namn (till exempel `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="5a76d-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-222">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-222">**Key**</span></span> | <span data-ttu-id="5a76d-223">Namn</span><span class="sxs-lookup"><span data-stu-id="5a76d-223">name</span></span> |
| <span data-ttu-id="5a76d-224">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-224">**Data type**</span></span> | <span data-ttu-id="5a76d-225">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-225">String</span></span> |
| <span data-ttu-id="5a76d-226">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-226">**Possible values**</span></span> | <span data-ttu-id="5a76d-227">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-227">any string</span></span> |
| <span data-ttu-id="5a76d-228">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-228">**Comments**</span></span> | <span data-ttu-id="5a76d-229">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="5a76d-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="5a76d-230">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="5a76d-230">Allowed threats</span></span>

<span data-ttu-id="5a76d-231">Lista över hot (identifieras med namnet) som inte blockeras av produkten och i stället får köras.</span><span class="sxs-lookup"><span data-stu-id="5a76d-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-232">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-232">**Key**</span></span> | <span data-ttu-id="5a76d-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="5a76d-233">allowedThreats</span></span> |
| <span data-ttu-id="5a76d-234">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-234">**Data type**</span></span> | <span data-ttu-id="5a76d-235">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a76d-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="5a76d-236">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="5a76d-236">Disallowed threat actions</span></span>

<span data-ttu-id="5a76d-237">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="5a76d-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="5a76d-238">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="5a76d-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-239">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-239">**Key**</span></span> | <span data-ttu-id="5a76d-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="5a76d-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="5a76d-241">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-241">**Data type**</span></span> | <span data-ttu-id="5a76d-242">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a76d-242">Array of strings</span></span> |
| <span data-ttu-id="5a76d-243">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-243">**Possible values**</span></span> | <span data-ttu-id="5a76d-244">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="5a76d-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="5a76d-245">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="5a76d-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="5a76d-246">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-246">**Comments**</span></span> | <span data-ttu-id="5a76d-247">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="5a76d-248">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="5a76d-248">Threat type settings</span></span>

<span data-ttu-id="5a76d-249">Inställningen *för threatTypeSettings* i antivirusmotorn används för att styra hur vissa hottyper hanteras av produkten.</span><span class="sxs-lookup"><span data-stu-id="5a76d-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-250">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-250">**Key**</span></span> | <span data-ttu-id="5a76d-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="5a76d-251">threatTypeSettings</span></span> |
| <span data-ttu-id="5a76d-252">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-252">**Data type**</span></span> | <span data-ttu-id="5a76d-253">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a76d-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a76d-254">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-254">**Comments**</span></span> | <span data-ttu-id="5a76d-255">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a76d-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="5a76d-256">**Hottyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-256">**Threat type**</span></span>

<span data-ttu-id="5a76d-257">Typ av hot som beteendet är konfigurerat för.</span><span class="sxs-lookup"><span data-stu-id="5a76d-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-258">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-258">**Key**</span></span> | <span data-ttu-id="5a76d-259">tangent</span><span class="sxs-lookup"><span data-stu-id="5a76d-259">key</span></span> |
| <span data-ttu-id="5a76d-260">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-260">**Data type**</span></span> | <span data-ttu-id="5a76d-261">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-261">String</span></span> |
| <span data-ttu-id="5a76d-262">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-262">**Possible values**</span></span> | <span data-ttu-id="5a76d-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="5a76d-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="5a76d-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="5a76d-264">archive_bomb</span></span> |
|||

<span data-ttu-id="5a76d-265">**Åtgärd att vidta**</span><span class="sxs-lookup"><span data-stu-id="5a76d-265">**Action to take**</span></span>

<span data-ttu-id="5a76d-266">Åtgärd att vidta när de kommer över en typ av hot som anges i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="5a76d-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="5a76d-267">Kan vara:</span><span class="sxs-lookup"><span data-stu-id="5a76d-267">Can be:</span></span>

- <span data-ttu-id="5a76d-268">**Granskning:** Enheten är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="5a76d-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="5a76d-269">**Blockering:** Enheten är skyddad mot den här typen av hot och du meddelas i säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="5a76d-270">**Av:** Enheten är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="5a76d-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-271">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-271">**Key**</span></span> | <span data-ttu-id="5a76d-272">värde</span><span class="sxs-lookup"><span data-stu-id="5a76d-272">value</span></span> |
| <span data-ttu-id="5a76d-273">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-273">**Data type**</span></span> | <span data-ttu-id="5a76d-274">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-274">String</span></span> |
| <span data-ttu-id="5a76d-275">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-275">**Possible values**</span></span> | <span data-ttu-id="5a76d-276">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-276">audit (default)</span></span> <br/> <span data-ttu-id="5a76d-277">blockera</span><span class="sxs-lookup"><span data-stu-id="5a76d-277">block</span></span> <br/> <span data-ttu-id="5a76d-278">av</span><span class="sxs-lookup"><span data-stu-id="5a76d-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="5a76d-279">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="5a76d-279">Threat type settings merge policy</span></span>

<span data-ttu-id="5a76d-280">Anger kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="5a76d-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="5a76d-281">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5a76d-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="5a76d-282">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="5a76d-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-283">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-283">**Key**</span></span> | <span data-ttu-id="5a76d-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5a76d-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="5a76d-285">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-285">**Data type**</span></span> | <span data-ttu-id="5a76d-286">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-286">String</span></span> |
| <span data-ttu-id="5a76d-287">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-287">**Possible values**</span></span> | <span data-ttu-id="5a76d-288">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-288">merge (default)</span></span> <br/> <span data-ttu-id="5a76d-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="5a76d-289">admin_only</span></span> |
| <span data-ttu-id="5a76d-290">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-290">**Comments**</span></span> | <span data-ttu-id="5a76d-291">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="5a76d-292">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="5a76d-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="5a76d-293">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="5a76d-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="5a76d-294">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="5a76d-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="5a76d-295">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="5a76d-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-296">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-296">**Key**</span></span> | <span data-ttu-id="5a76d-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="5a76d-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="5a76d-298">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-298">**Data type**</span></span> | <span data-ttu-id="5a76d-299">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-299">String</span></span> |
| <span data-ttu-id="5a76d-300">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-300">**Possible values**</span></span> | <span data-ttu-id="5a76d-301">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="5a76d-301">90 (default).</span></span> <span data-ttu-id="5a76d-302">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="5a76d-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="5a76d-303">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-303">**Comments**</span></span> | <span data-ttu-id="5a76d-304">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="5a76d-305">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="5a76d-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="5a76d-306">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="5a76d-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="5a76d-307">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="5a76d-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-308">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-308">**Key**</span></span> | <span data-ttu-id="5a76d-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="5a76d-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="5a76d-310">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-310">**Data type**</span></span> | <span data-ttu-id="5a76d-311">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-311">String</span></span> |
| <span data-ttu-id="5a76d-312">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-312">**Possible values**</span></span> | <span data-ttu-id="5a76d-313">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="5a76d-313">10000 (default).</span></span> <span data-ttu-id="5a76d-314">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="5a76d-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="5a76d-315">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-315">**Comments**</span></span> | <span data-ttu-id="5a76d-316">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5a76d-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="5a76d-317">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="5a76d-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="5a76d-318">*CloudService-posten* i konfigurationsprofilen används för att konfigurera produktens molndrivna skyddsfunktion.</span><span class="sxs-lookup"><span data-stu-id="5a76d-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-319">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-319">**Key**</span></span> | <span data-ttu-id="5a76d-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="5a76d-320">cloudService</span></span> |
| <span data-ttu-id="5a76d-321">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-321">**Data type**</span></span> | <span data-ttu-id="5a76d-322">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a76d-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a76d-323">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a76d-323">**Comments**</span></span> | <span data-ttu-id="5a76d-324">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a76d-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="5a76d-325">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="5a76d-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="5a76d-326">Avgör om moln levererat skydd är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="5a76d-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="5a76d-327">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="5a76d-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-328">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-328">**Key**</span></span> | <span data-ttu-id="5a76d-329">aktiverat</span><span class="sxs-lookup"><span data-stu-id="5a76d-329">enabled</span></span> |
| <span data-ttu-id="5a76d-330">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-330">**Data type**</span></span> | <span data-ttu-id="5a76d-331">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5a76d-331">Boolean</span></span> |
| <span data-ttu-id="5a76d-332">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-332">**Possible values**</span></span> | <span data-ttu-id="5a76d-333">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-333">true (default)</span></span> <br/> <span data-ttu-id="5a76d-334">false</span><span class="sxs-lookup"><span data-stu-id="5a76d-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="5a76d-335">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="5a76d-335">Diagnostic collection level</span></span>

<span data-ttu-id="5a76d-336">Diagnostikdata används för att hålla Defender för Slutpunkt säker och uppdaterad, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="5a76d-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="5a76d-337">Den här inställningen bestämmer nivån för diagnostik som skickas av produkten till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a76d-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-338">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-338">**Key**</span></span> | <span data-ttu-id="5a76d-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="5a76d-339">diagnosticLevel</span></span> |
| <span data-ttu-id="5a76d-340">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-340">**Data type**</span></span> | <span data-ttu-id="5a76d-341">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-341">String</span></span> |
| <span data-ttu-id="5a76d-342">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-342">**Possible values**</span></span> | <span data-ttu-id="5a76d-343">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-343">optional (default)</span></span> <br/> <span data-ttu-id="5a76d-344">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="5a76d-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="5a76d-345">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="5a76d-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="5a76d-346">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a76d-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="5a76d-347">Det finns tre nivåer för kontroll av exempelinskick:</span><span class="sxs-lookup"><span data-stu-id="5a76d-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="5a76d-348">**Ingen**: inga misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a76d-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="5a76d-349">**Kassaskåp**: endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5a76d-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="5a76d-350">Det här är standardvärdet för den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="5a76d-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="5a76d-351">**Alla**: alla misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a76d-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-352">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-352">**Key**</span></span> | <span data-ttu-id="5a76d-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="5a76d-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="5a76d-354">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-354">**Data type**</span></span> | <span data-ttu-id="5a76d-355">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a76d-355">String</span></span> |
| <span data-ttu-id="5a76d-356">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-356">**Possible values**</span></span> | <span data-ttu-id="5a76d-357">none (ingen)</span><span class="sxs-lookup"><span data-stu-id="5a76d-357">none</span></span> <br/> <span data-ttu-id="5a76d-358">kassaskåp (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-358">safe (default)</span></span> <br/> <span data-ttu-id="5a76d-359">alla</span><span class="sxs-lookup"><span data-stu-id="5a76d-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="5a76d-360">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="5a76d-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="5a76d-361">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="5a76d-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="5a76d-362">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a76d-362">**Key**</span></span> | <span data-ttu-id="5a76d-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="5a76d-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="5a76d-364">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a76d-364">**Data type**</span></span> | <span data-ttu-id="5a76d-365">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5a76d-365">Boolean</span></span> |
| <span data-ttu-id="5a76d-366">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a76d-366">**Possible values**</span></span> | <span data-ttu-id="5a76d-367">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5a76d-367">true (default)</span></span> <br/> <span data-ttu-id="5a76d-368">false</span><span class="sxs-lookup"><span data-stu-id="5a76d-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="5a76d-369">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5a76d-369">Recommended configuration profile</span></span>

<span data-ttu-id="5a76d-370">För att komma igång rekommenderar vi följande konfigurationsprofil för ditt företag för att kunna dra nytta av alla skyddsfunktioner som Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="5a76d-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="5a76d-371">Följande konfigurationsprofil:</span><span class="sxs-lookup"><span data-stu-id="5a76d-371">The following configuration profile will:</span></span>

- <span data-ttu-id="5a76d-372">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="5a76d-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="5a76d-373">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="5a76d-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="5a76d-374">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="5a76d-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="5a76d-375">**Arkivposterna** (fil med hög komprimeringshastighet) granskas i produktloggarna</span><span class="sxs-lookup"><span data-stu-id="5a76d-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="5a76d-376">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="5a76d-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="5a76d-377">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="5a76d-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="5a76d-378">Aktivera automatisk exempelinskick på `safe` nivå</span><span class="sxs-lookup"><span data-stu-id="5a76d-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="5a76d-379">Exempelprofil</span><span class="sxs-lookup"><span data-stu-id="5a76d-379">Sample profile</span></span>

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
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="5a76d-380">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5a76d-380">Full configuration profile example</span></span>

<span data-ttu-id="5a76d-381">Följande konfigurationsprofil innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över produkten.</span><span class="sxs-lookup"><span data-stu-id="5a76d-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="5a76d-382">Fullständig profil</span><span class="sxs-lookup"><span data-stu-id="5a76d-382">Full profile</span></span>

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
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
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
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="5a76d-383">Validering av konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5a76d-383">Configuration profile validation</span></span>

<span data-ttu-id="5a76d-384">Konfigurationsprofilen måste vara en giltig JSON-formaterad fil.</span><span class="sxs-lookup"><span data-stu-id="5a76d-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="5a76d-385">Det finns ett antal verktyg som kan användas för att verifiera detta.</span><span class="sxs-lookup"><span data-stu-id="5a76d-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="5a76d-386">Om du till exempel har `python` installerat på enheten:</span><span class="sxs-lookup"><span data-stu-id="5a76d-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="5a76d-387">Om JSON-koden är rätt utformad matar kommandot ovan ut den tillbaka till terminalen och returnerar en utgångskod för `0` .</span><span class="sxs-lookup"><span data-stu-id="5a76d-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="5a76d-388">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="5a76d-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="5a76d-389">Verifiera att filen mdatp_managed.jsfungerar som förväntat</span><span class="sxs-lookup"><span data-stu-id="5a76d-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="5a76d-390">Kontrollera att din /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfungerar korrekt genom att se "[managed]" bredvid de här inställningarna:</span><span class="sxs-lookup"><span data-stu-id="5a76d-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="5a76d-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="5a76d-391">cloud_enabled</span></span>
- <span data-ttu-id="5a76d-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="5a76d-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="5a76d-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="5a76d-393">passice_mode_enabled</span></span>
- <span data-ttu-id="5a76d-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="5a76d-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="5a76d-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="5a76d-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="5a76d-396">För mdatp_managed.jsatt börja gälla krävs ingen omstart av wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="5a76d-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="5a76d-397">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="5a76d-397">Configuration profile deployment</span></span>

<span data-ttu-id="5a76d-398">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via det hanteringsverktyg som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="5a76d-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="5a76d-399">Defender för Endpoint för Linux läser den hanterade konfigurationen från *filen /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="5a76d-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
