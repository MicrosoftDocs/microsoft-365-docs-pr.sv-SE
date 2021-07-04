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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289499"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5c2f0-104">Ange inställningar för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="5c2f0-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5c2f0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c2f0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c2f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c2f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c2f0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5c2f0-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5c2f0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c2f0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="5c2f0-110">Det här avsnittet innehåller instruktioner för hur du anger inställningar för Defender för Slutpunkt på Linux i företagsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="5c2f0-111">Om du är intresserad av att konfigurera produkten på en enhet från kommandoraden kan du gå till [Resurser](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="5c2f0-112">I företagsmiljöer kan Defender för Slutpunkt i Linux hanteras via en konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="5c2f0-113">Den här profilen distribueras från valfri hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="5c2f0-114">Inställningar som hanteras av företaget har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="5c2f0-115">Med andra ord kan användarna i företaget inte ändra inställningar som anges i den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="5c2f0-116">I den här artikeln beskrivs profilens struktur (inklusive en rekommenderad profil som du kan använda för att komma igång) och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="5c2f0-117">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="5c2f0-117">Configuration profile structure</span></span>

<span data-ttu-id="5c2f0-118">Konfigurationsprofilen är en .json-fil som består av poster som identifieras av en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="5c2f0-119">Värdena kan vara enkla, till exempel numeriska värden eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="5c2f0-120">Vanligtvis använder du ett konfigurationsverktyg för att skicka en fil med ```mdatp_managed.json``` namnet på ```/etc/opt/microsoft/mdatp/managed/``` platsen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="5c2f0-121">Den översta nivån i konfigurationsprofilen omfattar produktomfattande inställningar och poster för underavsnitt av produkten, som förklaras mer detaljerat i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="5c2f0-122">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="5c2f0-122">Antivirus engine preferences</span></span>

<span data-ttu-id="5c2f0-123">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i produkten.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-124">Description</span></span>|<span data-ttu-id="5c2f0-125">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-125">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-126">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-126">**Key**</span></span>|<span data-ttu-id="5c2f0-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="5c2f0-127">antivirusEngine</span></span>|
|<span data-ttu-id="5c2f0-128">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-128">**Data type**</span></span>|<span data-ttu-id="5c2f0-129">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="5c2f0-130">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-130">**Comments**</span></span>|<span data-ttu-id="5c2f0-131">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="5c2f0-132">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="5c2f0-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="5c2f0-133">Avgör om realtidsskydd (genomsökning av filer när de används) är aktiverat eller inte.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-134">Description</span></span>|<span data-ttu-id="5c2f0-135">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-135">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-136">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-136">**Key**</span></span>|<span data-ttu-id="5c2f0-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="5c2f0-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="5c2f0-138">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-138">**Data type**</span></span>|<span data-ttu-id="5c2f0-139">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5c2f0-139">Boolean</span></span>|
|<span data-ttu-id="5c2f0-140">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-140">**Possible values**</span></span>|<span data-ttu-id="5c2f0-141">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-141">true (default)</span></span> <p> <span data-ttu-id="5c2f0-142">false</span><span class="sxs-lookup"><span data-stu-id="5c2f0-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="5c2f0-143">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="5c2f0-143">Enable / disable passive mode</span></span>

<span data-ttu-id="5c2f0-144">Avgör om antivirusmotorn körs i passiv form eller inte.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="5c2f0-145">I passivt läge:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-145">In passive mode:</span></span>

- <span data-ttu-id="5c2f0-146">Realtidsskydd är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="5c2f0-147">Skanning på begäran är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="5c2f0-148">Automatisk åtgärd för hot är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="5c2f0-149">Säkerhetsintelligensuppdateringar aktiveras.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="5c2f0-150">Statusmenyikonen är dold.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-151">Description</span></span>|<span data-ttu-id="5c2f0-152">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-152">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-153">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-153">**Key**</span></span>|<span data-ttu-id="5c2f0-154">passivläge</span><span class="sxs-lookup"><span data-stu-id="5c2f0-154">passiveMode</span></span>|
|<span data-ttu-id="5c2f0-155">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-155">**Data type**</span></span>|<span data-ttu-id="5c2f0-156">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5c2f0-156">Boolean</span></span>|
|<span data-ttu-id="5c2f0-157">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-157">**Possible values**</span></span>|<span data-ttu-id="5c2f0-158">false (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-158">false (default)</span></span> <p> <span data-ttu-id="5c2f0-159">true</span><span class="sxs-lookup"><span data-stu-id="5c2f0-159">true</span></span>|
|<span data-ttu-id="5c2f0-160">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-160">**Comments**</span></span>|<span data-ttu-id="5c2f0-161">Tillgängligt i Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="5c2f0-162">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="5c2f0-162">Exclusion merge policy</span></span>

<span data-ttu-id="5c2f0-163">Anger kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="5c2f0-164">Det kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="5c2f0-165">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-166">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-166">Description</span></span>|<span data-ttu-id="5c2f0-167">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-167">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-168">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-168">**Key**</span></span>|<span data-ttu-id="5c2f0-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5c2f0-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="5c2f0-170">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-170">**Data type**</span></span>|<span data-ttu-id="5c2f0-171">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-171">String</span></span>|
|<span data-ttu-id="5c2f0-172">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-172">**Possible values**</span></span>|<span data-ttu-id="5c2f0-173">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-173">merge (default)</span></span> <p> <span data-ttu-id="5c2f0-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="5c2f0-174">admin_only</span></span>|
|<span data-ttu-id="5c2f0-175">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-175">**Comments**</span></span>|<span data-ttu-id="5c2f0-176">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="5c2f0-177">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-177">Scan exclusions</span></span>

<span data-ttu-id="5c2f0-178">Enheter som har uteslutits från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="5c2f0-179">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="5c2f0-180">(Undantag anges som en matris med objekt, administratören kan ange så många element som behövs, i valfri ordning.)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="5c2f0-181">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-181">Description</span></span>|<span data-ttu-id="5c2f0-182">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-182">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-183">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-183">**Key**</span></span>|<span data-ttu-id="5c2f0-184">undantag</span><span class="sxs-lookup"><span data-stu-id="5c2f0-184">exclusions</span></span>|
|<span data-ttu-id="5c2f0-185">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-185">**Data type**</span></span>|<span data-ttu-id="5c2f0-186">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="5c2f0-187">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-187">**Comments**</span></span>|<span data-ttu-id="5c2f0-188">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="5c2f0-189">Typ av undantag</span><span class="sxs-lookup"><span data-stu-id="5c2f0-189">Type of exclusion</span></span>

<span data-ttu-id="5c2f0-190">Anger vilken typ av innehåll som undantas från genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-191">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-191">Description</span></span>|<span data-ttu-id="5c2f0-192">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-192">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-193">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-193">**Key**</span></span>|<span data-ttu-id="5c2f0-194">$type</span><span class="sxs-lookup"><span data-stu-id="5c2f0-194">$type</span></span>|
|<span data-ttu-id="5c2f0-195">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-195">**Data type**</span></span>|<span data-ttu-id="5c2f0-196">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-196">String</span></span>|
|<span data-ttu-id="5c2f0-197">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-197">**Possible values**</span></span>|<span data-ttu-id="5c2f0-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="5c2f0-198">excludedPath</span></span> <p> <span data-ttu-id="5c2f0-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="5c2f0-199">excludedFileExtension</span></span> <p> <span data-ttu-id="5c2f0-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="5c2f0-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="5c2f0-201">Sökväg till utelämnat innehåll</span><span class="sxs-lookup"><span data-stu-id="5c2f0-201">Path to excluded content</span></span>

<span data-ttu-id="5c2f0-202">Används för att utesluta innehåll från genomsökningen genom den fullständiga sökvägen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-203">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-203">Description</span></span>|<span data-ttu-id="5c2f0-204">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-204">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-205">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-205">**Key**</span></span>|<span data-ttu-id="5c2f0-206">sökväg</span><span class="sxs-lookup"><span data-stu-id="5c2f0-206">path</span></span>|
|<span data-ttu-id="5c2f0-207">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-207">**Data type**</span></span>|<span data-ttu-id="5c2f0-208">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-208">String</span></span>|
|<span data-ttu-id="5c2f0-209">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-209">**Possible values**</span></span>|<span data-ttu-id="5c2f0-210">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="5c2f0-210">valid paths</span></span>|
|<span data-ttu-id="5c2f0-211">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-211">**Comments**</span></span>|<span data-ttu-id="5c2f0-212">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="5c2f0-213">Sökvägstyp (fil/katalog)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-213">Path type (file / directory)</span></span>

<span data-ttu-id="5c2f0-214">Anger om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-215">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-215">Description</span></span>|<span data-ttu-id="5c2f0-216">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-216">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-217">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-217">**Key**</span></span>|<span data-ttu-id="5c2f0-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="5c2f0-218">isDirectory</span></span>|
|<span data-ttu-id="5c2f0-219">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-219">**Data type**</span></span>|<span data-ttu-id="5c2f0-220">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5c2f0-220">Boolean</span></span>|
|<span data-ttu-id="5c2f0-221">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-221">**Possible values**</span></span>|<span data-ttu-id="5c2f0-222">false (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-222">false (default)</span></span> <p> <span data-ttu-id="5c2f0-223">true</span><span class="sxs-lookup"><span data-stu-id="5c2f0-223">true</span></span>|
|<span data-ttu-id="5c2f0-224">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-224">**Comments**</span></span>|<span data-ttu-id="5c2f0-225">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="5c2f0-226">Filnamnstillägget är undantaget från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="5c2f0-226">File extension excluded from the scan</span></span>

<span data-ttu-id="5c2f0-227">Används för att utesluta innehåll från genomsökningen efter filnamnstillägget.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-228">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-228">Description</span></span>|<span data-ttu-id="5c2f0-229">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-229">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-230">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-230">**Key**</span></span>|<span data-ttu-id="5c2f0-231">tillägg</span><span class="sxs-lookup"><span data-stu-id="5c2f0-231">extension</span></span>|
|<span data-ttu-id="5c2f0-232">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-232">**Data type**</span></span>|<span data-ttu-id="5c2f0-233">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-233">String</span></span>|
|<span data-ttu-id="5c2f0-234">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-234">**Possible values**</span></span>|<span data-ttu-id="5c2f0-235">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="5c2f0-235">valid file extensions</span></span>|
|<span data-ttu-id="5c2f0-236">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-236">**Comments**</span></span>|<span data-ttu-id="5c2f0-237">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="5c2f0-238">Process som är undantagen från genomsökningen\*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="5c2f0-239">Anger en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="5c2f0-240">Processen kan antingen anges med sitt namn (till exempel `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="5c2f0-241">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-241">Description</span></span>|<span data-ttu-id="5c2f0-242">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-242">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-243">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-243">**Key**</span></span>|<span data-ttu-id="5c2f0-244">Namn</span><span class="sxs-lookup"><span data-stu-id="5c2f0-244">name</span></span>|
|<span data-ttu-id="5c2f0-245">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-245">**Data type**</span></span>|<span data-ttu-id="5c2f0-246">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-246">String</span></span>|
|<span data-ttu-id="5c2f0-247">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-247">**Possible values**</span></span>|<span data-ttu-id="5c2f0-248">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-248">any string</span></span>|
|<span data-ttu-id="5c2f0-249">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-249">**Comments**</span></span>|<span data-ttu-id="5c2f0-250">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="5c2f0-251">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="5c2f0-251">Allowed threats</span></span>

<span data-ttu-id="5c2f0-252">Lista över hot (identifieras med namnet) som inte blockeras av produkten och i stället får köras.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-253">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-253">Description</span></span>|<span data-ttu-id="5c2f0-254">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-254">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-255">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-255">**Key**</span></span>|<span data-ttu-id="5c2f0-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="5c2f0-256">allowedThreats</span></span>|
|<span data-ttu-id="5c2f0-257">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-257">**Data type**</span></span>|<span data-ttu-id="5c2f0-258">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5c2f0-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="5c2f0-259">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="5c2f0-259">Disallowed threat actions</span></span>

<span data-ttu-id="5c2f0-260">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="5c2f0-261">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-262">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-262">Description</span></span>|<span data-ttu-id="5c2f0-263">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-263">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-264">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-264">**Key**</span></span>|<span data-ttu-id="5c2f0-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="5c2f0-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="5c2f0-266">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-266">**Data type**</span></span>|<span data-ttu-id="5c2f0-267">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5c2f0-267">Array of strings</span></span>|
|<span data-ttu-id="5c2f0-268">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-268">**Possible values**</span></span>|<span data-ttu-id="5c2f0-269">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="5c2f0-270">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="5c2f0-271">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-271">**Comments**</span></span>|<span data-ttu-id="5c2f0-272">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="5c2f0-273">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="5c2f0-273">Threat type settings</span></span>

<span data-ttu-id="5c2f0-274">Inställningen *för threatTypeSettings* i antivirusmotorn används för att styra hur vissa hottyper hanteras av produkten.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-275">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-275">Description</span></span>|<span data-ttu-id="5c2f0-276">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-276">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-277">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-277">**Key**</span></span>|<span data-ttu-id="5c2f0-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="5c2f0-278">threatTypeSettings</span></span>|
|<span data-ttu-id="5c2f0-279">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-279">**Data type**</span></span>|<span data-ttu-id="5c2f0-280">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="5c2f0-281">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-281">**Comments**</span></span>|<span data-ttu-id="5c2f0-282">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="5c2f0-283">Hottyp</span><span class="sxs-lookup"><span data-stu-id="5c2f0-283">Threat type</span></span>

<span data-ttu-id="5c2f0-284">Typ av hot som beteendet är konfigurerat för.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-285">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-285">Description</span></span>|<span data-ttu-id="5c2f0-286">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-286">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-287">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-287">**Key**</span></span>|<span data-ttu-id="5c2f0-288">tangent</span><span class="sxs-lookup"><span data-stu-id="5c2f0-288">key</span></span>|
|<span data-ttu-id="5c2f0-289">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-289">**Data type**</span></span>|<span data-ttu-id="5c2f0-290">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-290">String</span></span>|
|<span data-ttu-id="5c2f0-291">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-291">**Possible values**</span></span>|<span data-ttu-id="5c2f0-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="5c2f0-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="5c2f0-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="5c2f0-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="5c2f0-294">Åtgärd att vidta</span><span class="sxs-lookup"><span data-stu-id="5c2f0-294">Action to take</span></span>

<span data-ttu-id="5c2f0-295">Åtgärd att vidta när de kommer över en typ av hot som anges i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="5c2f0-296">Kan vara:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-296">Can be:</span></span>

- <span data-ttu-id="5c2f0-297">**Granskning:** Enheten är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="5c2f0-298">**Blockering:** Enheten är skyddad mot den här typen av hot och du meddelas i säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="5c2f0-299">**Av:** Enheten är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-300">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-300">Description</span></span>|<span data-ttu-id="5c2f0-301">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-301">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-302">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-302">**Key**</span></span>|<span data-ttu-id="5c2f0-303">värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-303">value</span></span>|
|<span data-ttu-id="5c2f0-304">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-304">**Data type**</span></span>|<span data-ttu-id="5c2f0-305">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-305">String</span></span>|
|<span data-ttu-id="5c2f0-306">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-306">**Possible values**</span></span>|<span data-ttu-id="5c2f0-307">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-307">audit (default)</span></span> <p> <span data-ttu-id="5c2f0-308">blockera</span><span class="sxs-lookup"><span data-stu-id="5c2f0-308">block</span></span> <p> <span data-ttu-id="5c2f0-309">av</span><span class="sxs-lookup"><span data-stu-id="5c2f0-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="5c2f0-310">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="5c2f0-310">Threat type settings merge policy</span></span>

<span data-ttu-id="5c2f0-311">Anger kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="5c2f0-312">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="5c2f0-313">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-314">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-314">Description</span></span>|<span data-ttu-id="5c2f0-315">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-315">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-316">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-316">**Key**</span></span>|<span data-ttu-id="5c2f0-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5c2f0-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="5c2f0-318">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-318">**Data type**</span></span>|<span data-ttu-id="5c2f0-319">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-319">String</span></span>|
|<span data-ttu-id="5c2f0-320">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-320">**Possible values**</span></span>|<span data-ttu-id="5c2f0-321">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-321">merge (default)</span></span> <p> <span data-ttu-id="5c2f0-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="5c2f0-322">admin_only</span></span>|
|<span data-ttu-id="5c2f0-323">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-323">**Comments**</span></span>|<span data-ttu-id="5c2f0-324">Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="5c2f0-325">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="5c2f0-326">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="5c2f0-327">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="5c2f0-328">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-329">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-329">Description</span></span>|<span data-ttu-id="5c2f0-330">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-330">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-331">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-331">**Key**</span></span>|<span data-ttu-id="5c2f0-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="5c2f0-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="5c2f0-333">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-333">**Data type**</span></span>|<span data-ttu-id="5c2f0-334">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-334">String</span></span>|
|<span data-ttu-id="5c2f0-335">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-335">**Possible values**</span></span>|<span data-ttu-id="5c2f0-336">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-336">90 (default).</span></span> <span data-ttu-id="5c2f0-337">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="5c2f0-338">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-338">**Comments**</span></span>|<span data-ttu-id="5c2f0-339">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="5c2f0-340">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="5c2f0-341">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="5c2f0-342">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-343">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-343">Description</span></span>|<span data-ttu-id="5c2f0-344">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-344">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-345">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-345">**Key**</span></span>|<span data-ttu-id="5c2f0-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="5c2f0-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="5c2f0-347">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-347">**Data type**</span></span>|<span data-ttu-id="5c2f0-348">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-348">String</span></span>|
|<span data-ttu-id="5c2f0-349">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-349">**Possible values**</span></span>|<span data-ttu-id="5c2f0-350">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="5c2f0-350">10000 (default).</span></span> <span data-ttu-id="5c2f0-351">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="5c2f0-352">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-352">**Comments**</span></span>|<span data-ttu-id="5c2f0-353">Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="5c2f0-354">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="5c2f0-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="5c2f0-355">*CloudService-posten* i konfigurationsprofilen används för att konfigurera produktens molndrivna skyddsfunktion.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-356">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-356">Description</span></span>|<span data-ttu-id="5c2f0-357">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-357">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-358">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-358">**Key**</span></span>|<span data-ttu-id="5c2f0-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="5c2f0-359">cloudService</span></span>|
|<span data-ttu-id="5c2f0-360">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-360">**Data type**</span></span>|<span data-ttu-id="5c2f0-361">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="5c2f0-362">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-362">**Comments**</span></span>|<span data-ttu-id="5c2f0-363">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="5c2f0-364">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="5c2f0-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="5c2f0-365">Avgör om moln levererat skydd är aktiverat på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="5c2f0-366">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-367">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-367">Description</span></span>|<span data-ttu-id="5c2f0-368">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-368">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-369">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-369">**Key**</span></span>|<span data-ttu-id="5c2f0-370">aktiverat</span><span class="sxs-lookup"><span data-stu-id="5c2f0-370">enabled</span></span>|
|<span data-ttu-id="5c2f0-371">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-371">**Data type**</span></span>|<span data-ttu-id="5c2f0-372">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5c2f0-372">Boolean</span></span>|
|<span data-ttu-id="5c2f0-373">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-373">**Possible values**</span></span>|<span data-ttu-id="5c2f0-374">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-374">true (default)</span></span> <p> <span data-ttu-id="5c2f0-375">false</span><span class="sxs-lookup"><span data-stu-id="5c2f0-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="5c2f0-376">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="5c2f0-376">Diagnostic collection level</span></span>

<span data-ttu-id="5c2f0-377">Diagnostikdata används för att hålla Defender för Slutpunkt säker och uppdaterad, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="5c2f0-378">Den här inställningen bestämmer nivån för diagnostik som skickas av produkten till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-379">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-379">Description</span></span>|<span data-ttu-id="5c2f0-380">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-380">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-381">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-381">**Key**</span></span>|<span data-ttu-id="5c2f0-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="5c2f0-382">diagnosticLevel</span></span>|
|<span data-ttu-id="5c2f0-383">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-383">**Data type**</span></span>|<span data-ttu-id="5c2f0-384">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-384">String</span></span>|
|<span data-ttu-id="5c2f0-385">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-385">**Possible values**</span></span>|<span data-ttu-id="5c2f0-386">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-386">optional (default)</span></span> <p> <span data-ttu-id="5c2f0-387">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="5c2f0-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="5c2f0-388">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="5c2f0-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="5c2f0-389">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="5c2f0-390">Det finns tre nivåer för kontroll av exempelinskick:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="5c2f0-391">**Ingen**: inga misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="5c2f0-392">**Valv**: endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="5c2f0-393">Det här är standardvärdet för den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="5c2f0-394">**Alla**: alla misstänkta exempel skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="5c2f0-395">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-395">Description</span></span>|<span data-ttu-id="5c2f0-396">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-396">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-397">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-397">**Key**</span></span>|<span data-ttu-id="5c2f0-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="5c2f0-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="5c2f0-399">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-399">**Data type**</span></span>|<span data-ttu-id="5c2f0-400">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c2f0-400">String</span></span>|
|<span data-ttu-id="5c2f0-401">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-401">**Possible values**</span></span>|<span data-ttu-id="5c2f0-402">none (ingen)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-402">none</span></span> <p> <span data-ttu-id="5c2f0-403">kassaskåp (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-403">safe (default)</span></span> <p> <span data-ttu-id="5c2f0-404">alla</span><span class="sxs-lookup"><span data-stu-id="5c2f0-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="5c2f0-405">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="5c2f0-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="5c2f0-406">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="5c2f0-407">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c2f0-407">Description</span></span>|<span data-ttu-id="5c2f0-408">Värde</span><span class="sxs-lookup"><span data-stu-id="5c2f0-408">Value</span></span>|
|---|---|
|<span data-ttu-id="5c2f0-409">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-409">**Key**</span></span>|<span data-ttu-id="5c2f0-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="5c2f0-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="5c2f0-411">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-411">**Data type**</span></span>|<span data-ttu-id="5c2f0-412">Boolesk</span><span class="sxs-lookup"><span data-stu-id="5c2f0-412">Boolean</span></span>|
|<span data-ttu-id="5c2f0-413">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5c2f0-413">**Possible values**</span></span>|<span data-ttu-id="5c2f0-414">true (standard)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-414">true (default)</span></span> <p> <span data-ttu-id="5c2f0-415">false</span><span class="sxs-lookup"><span data-stu-id="5c2f0-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="5c2f0-416">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5c2f0-416">Recommended configuration profile</span></span>

<span data-ttu-id="5c2f0-417">För att komma igång rekommenderar vi följande konfigurationsprofil för ditt företag för att kunna dra nytta av alla skyddsfunktioner som Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="5c2f0-418">Följande konfigurationsprofil:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-418">The following configuration profile will:</span></span>

- <span data-ttu-id="5c2f0-419">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="5c2f0-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="5c2f0-420">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="5c2f0-421">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="5c2f0-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="5c2f0-422">**Arkivposterna** (fil med hög komprimeringshastighet) granskas i produktloggarna</span><span class="sxs-lookup"><span data-stu-id="5c2f0-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="5c2f0-423">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="5c2f0-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="5c2f0-424">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="5c2f0-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="5c2f0-425">Aktivera automatisk exempelinskick på `safe` nivå</span><span class="sxs-lookup"><span data-stu-id="5c2f0-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="5c2f0-426">Exempelprofil</span><span class="sxs-lookup"><span data-stu-id="5c2f0-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="5c2f0-427">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5c2f0-427">Full configuration profile example</span></span>

<span data-ttu-id="5c2f0-428">Följande konfigurationsprofil innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över produkten.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="5c2f0-429">Fullständig profil</span><span class="sxs-lookup"><span data-stu-id="5c2f0-429">Full profile</span></span>

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

## <a name="configuration-profile-validation"></a><span data-ttu-id="5c2f0-430">Validering av konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="5c2f0-430">Configuration profile validation</span></span>

<span data-ttu-id="5c2f0-431">Konfigurationsprofilen måste vara en giltig JSON-formaterad fil.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="5c2f0-432">Det finns ett antal verktyg som kan användas för att verifiera detta.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="5c2f0-433">Om du till exempel har `python` installerat på enheten:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="5c2f0-434">Om JSON-koden är rätt utformad matar kommandot ovan ut den tillbaka till terminalen och returnerar en utgångskod för `0` .</span><span class="sxs-lookup"><span data-stu-id="5c2f0-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="5c2f0-435">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="5c2f0-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="5c2f0-436">Verifiera att filen mdatp_managed.jsfungerar som förväntat</span><span class="sxs-lookup"><span data-stu-id="5c2f0-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="5c2f0-437">Kontrollera att din /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfungerar korrekt genom att se "[managed]" bredvid de här inställningarna:</span><span class="sxs-lookup"><span data-stu-id="5c2f0-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="5c2f0-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="5c2f0-438">cloud_enabled</span></span>
- <span data-ttu-id="5c2f0-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="5c2f0-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="5c2f0-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="5c2f0-440">passive_mode_enabled</span></span>
- <span data-ttu-id="5c2f0-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="5c2f0-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="5c2f0-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="5c2f0-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="5c2f0-443">För mdatp_managed.jsatt börja gälla krävs ingen omstart av wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="5c2f0-444">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="5c2f0-444">Configuration profile deployment</span></span>

<span data-ttu-id="5c2f0-445">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via det hanteringsverktyg som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="5c2f0-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="5c2f0-446">Defender för slutpunkt i Linux läser den hanterade konfigurationen från *filen /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*</span><span class="sxs-lookup"><span data-stu-id="5c2f0-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
