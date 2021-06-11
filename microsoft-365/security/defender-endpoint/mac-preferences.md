---
title: Ange inställningar för Microsoft Defender för Slutpunkt på Mac
description: Konfigurera MMicrosoft Defender för Slutpunkt på Mac i företagsorganisationer.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, hantering, inställningar, företag, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346408"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="51fb6-104">Ange inställningar för Microsoft Defender för Slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="51fb6-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51fb6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="51fb6-105">**Applies to:**</span></span>

- [<span data-ttu-id="51fb6-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="51fb6-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="51fb6-107">Den här artikeln innehåller instruktioner för hur du anger inställningar för Microsoft Defender för Slutpunkt på macOS i företagsorganisationer.</span><span class="sxs-lookup"><span data-stu-id="51fb6-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="51fb6-108">Information om hur du konfigurerar Microsoft Defender för slutpunkt i macOS med kommandoradsgränssnittet finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="51fb6-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="51fb6-109">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="51fb6-109">Summary</span></span>

<span data-ttu-id="51fb6-110">I företagsorganisationer kan Microsoft Defender för slutpunkt i macOS hanteras via en konfigurationsprofil som distribueras med ett av flera hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="51fb6-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="51fb6-111">De inställningar som hanteras av ditt säkerhetsteam har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="51fb6-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="51fb6-112">Om du vill ändra inställningar som ställts in via konfigurationsprofilen krävs eskalerade behörigheter och är inte tillgängligt för användare utan administrativ behörighet.</span><span class="sxs-lookup"><span data-stu-id="51fb6-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="51fb6-113">I den här artikeln beskrivs konfigurationsprofilens struktur, en rekommenderad profil som du kan använda för att komma igång och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="51fb6-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="51fb6-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="51fb6-114">Configuration profile structure</span></span>

<span data-ttu-id="51fb6-115">Konfigurationsprofilen är en *PLIST-fil* som består av poster som identifieras med en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="51fb6-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="51fb6-116">Värdena kan antingen vara enkla (till exempel ett numeriskt värde) eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="51fb6-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="51fb6-117">Konfigurationsprofilens layout beror på vilken hanteringskonsol du använder.</span><span class="sxs-lookup"><span data-stu-id="51fb6-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="51fb6-118">Följande avsnitt innehåller exempel på konfigurationsprofiler för JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="51fb6-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="51fb6-119">Den översta nivån i konfigurationsprofilen innehåller produktomfattande inställningar och poster för underavsnitt av Microsoft Defender för slutpunkt, som förklaras mer ingående i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="51fb6-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="51fb6-120">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="51fb6-120">Antivirus engine preferences</span></span>

<span data-ttu-id="51fb6-121">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="51fb6-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="51fb6-122">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-122">Section</span></span>|<span data-ttu-id="51fb6-123">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-124">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-125">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-125">**Key**</span></span> | <span data-ttu-id="51fb6-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="51fb6-126">antivirusEngine</span></span> |
| <span data-ttu-id="51fb6-127">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-127">**Data type**</span></span> | <span data-ttu-id="51fb6-128">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-129">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-129">**Comments**</span></span> | <span data-ttu-id="51fb6-130">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="51fb6-131">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="51fb6-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="51fb6-132">Ange om du vill aktivera realtidsskydd som genomsöker filer när de används.</span><span class="sxs-lookup"><span data-stu-id="51fb6-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="51fb6-133">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-133">Section</span></span>|<span data-ttu-id="51fb6-134">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-135">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-136">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-136">**Key**</span></span> | <span data-ttu-id="51fb6-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="51fb6-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="51fb6-138">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-138">**Data type**</span></span> | <span data-ttu-id="51fb6-139">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-139">Boolean</span></span> |
| <span data-ttu-id="51fb6-140">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-140">**Possible values**</span></span> | <span data-ttu-id="51fb6-141">true (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-141">true (default)</span></span> <br/> <span data-ttu-id="51fb6-142">false</span><span class="sxs-lookup"><span data-stu-id="51fb6-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="51fb6-143">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="51fb6-143">Enable / disable passive mode</span></span>

<span data-ttu-id="51fb6-144">Ange om antivirusmotorn körs i passiv form.</span><span class="sxs-lookup"><span data-stu-id="51fb6-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="51fb6-145">Passivt läge har följande konsekvenser:</span><span class="sxs-lookup"><span data-stu-id="51fb6-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="51fb6-146">Realtidsskydd är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="51fb6-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="51fb6-147">Skanning på begäran är aktiverat</span><span class="sxs-lookup"><span data-stu-id="51fb6-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="51fb6-148">Automatisk åtgärd för hot är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="51fb6-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="51fb6-149">Säkerhetsintelligensuppdateringar är aktiverat</span><span class="sxs-lookup"><span data-stu-id="51fb6-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="51fb6-150">Statusmenyikonen är dold</span><span class="sxs-lookup"><span data-stu-id="51fb6-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="51fb6-151">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-151">Section</span></span>|<span data-ttu-id="51fb6-152">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-153">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-154">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-154">**Key**</span></span> | <span data-ttu-id="51fb6-155">passivläge</span><span class="sxs-lookup"><span data-stu-id="51fb6-155">passiveMode</span></span> |
| <span data-ttu-id="51fb6-156">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-156">**Data type**</span></span> | <span data-ttu-id="51fb6-157">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-157">Boolean</span></span> |
| <span data-ttu-id="51fb6-158">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-158">**Possible values**</span></span> | <span data-ttu-id="51fb6-159">false (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-159">false (default)</span></span> <br/> <span data-ttu-id="51fb6-160">true</span><span class="sxs-lookup"><span data-stu-id="51fb6-160">true</span></span> |
| <span data-ttu-id="51fb6-161">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-161">**Comments**</span></span> | <span data-ttu-id="51fb6-162">Tillgängligt i Microsoft Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="51fb6-163">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="51fb6-163">Exclusion merge policy</span></span>

<span data-ttu-id="51fb6-164">Ange kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="51fb6-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="51fb6-165">Det här kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="51fb6-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="51fb6-166">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="51fb6-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="51fb6-167">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-167">Section</span></span>|<span data-ttu-id="51fb6-168">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-169">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-170">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-170">**Key**</span></span> | <span data-ttu-id="51fb6-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="51fb6-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="51fb6-172">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-172">**Data type**</span></span> | <span data-ttu-id="51fb6-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-173">String</span></span> |
| <span data-ttu-id="51fb6-174">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-174">**Possible values**</span></span> | <span data-ttu-id="51fb6-175">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-175">merge (default)</span></span> <br/> <span data-ttu-id="51fb6-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="51fb6-176">admin_only</span></span> |
| <span data-ttu-id="51fb6-177">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-177">**Comments**</span></span> | <span data-ttu-id="51fb6-178">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="51fb6-179">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="51fb6-179">Scan exclusions</span></span>

<span data-ttu-id="51fb6-180">Ange enheter som inte ska genomsökas.</span><span class="sxs-lookup"><span data-stu-id="51fb6-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="51fb6-181">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="51fb6-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="51fb6-182">(Undantag anges som en matris med objekt, administratören kan ange så många element som behövs, i valfri ordning.)</span><span class="sxs-lookup"><span data-stu-id="51fb6-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="51fb6-183">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-183">Section</span></span>|<span data-ttu-id="51fb6-184">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-185">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-186">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-186">**Key**</span></span> | <span data-ttu-id="51fb6-187">undantag</span><span class="sxs-lookup"><span data-stu-id="51fb6-187">exclusions</span></span> |
| <span data-ttu-id="51fb6-188">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-188">**Data type**</span></span> | <span data-ttu-id="51fb6-189">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-190">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-190">**Comments**</span></span> | <span data-ttu-id="51fb6-191">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="51fb6-192">Typ av undantag</span><span class="sxs-lookup"><span data-stu-id="51fb6-192">Type of exclusion</span></span>

<span data-ttu-id="51fb6-193">Ange innehåll som ska undantas från att genomsökas efter typ.</span><span class="sxs-lookup"><span data-stu-id="51fb6-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="51fb6-194">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-194">Section</span></span>|<span data-ttu-id="51fb6-195">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-196">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-197">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-197">**Key**</span></span> | <span data-ttu-id="51fb6-198">$type</span><span class="sxs-lookup"><span data-stu-id="51fb6-198">$type</span></span> |
| <span data-ttu-id="51fb6-199">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-199">**Data type**</span></span> | <span data-ttu-id="51fb6-200">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-200">String</span></span> |
| <span data-ttu-id="51fb6-201">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-201">**Possible values**</span></span> | <span data-ttu-id="51fb6-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="51fb6-202">excludedPath</span></span> <br/> <span data-ttu-id="51fb6-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="51fb6-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="51fb6-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="51fb6-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="51fb6-205">Sökväg till utelämnat innehåll</span><span class="sxs-lookup"><span data-stu-id="51fb6-205">Path to excluded content</span></span>

<span data-ttu-id="51fb6-206">Ange innehåll som inte ska genomsökas efter fullständig sökväg.</span><span class="sxs-lookup"><span data-stu-id="51fb6-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="51fb6-207">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-207">Section</span></span>|<span data-ttu-id="51fb6-208">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-209">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-210">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-210">**Key**</span></span> | <span data-ttu-id="51fb6-211">sökväg</span><span class="sxs-lookup"><span data-stu-id="51fb6-211">path</span></span> |
| <span data-ttu-id="51fb6-212">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-212">**Data type**</span></span> | <span data-ttu-id="51fb6-213">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-213">String</span></span> |
| <span data-ttu-id="51fb6-214">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-214">**Possible values**</span></span> | <span data-ttu-id="51fb6-215">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="51fb6-215">valid paths</span></span> |
| <span data-ttu-id="51fb6-216">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-216">**Comments**</span></span> | <span data-ttu-id="51fb6-217">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="51fb6-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="51fb6-218">Undantagstyper som stöds</span><span class="sxs-lookup"><span data-stu-id="51fb6-218">Supported exclusion types</span></span>

<span data-ttu-id="51fb6-219">I följande tabell visas de undantagstyper som stöds av Defender för slutpunkt på Mac.</span><span class="sxs-lookup"><span data-stu-id="51fb6-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="51fb6-220">Exkludering</span><span class="sxs-lookup"><span data-stu-id="51fb6-220">Exclusion</span></span> | <span data-ttu-id="51fb6-221">Definition</span><span class="sxs-lookup"><span data-stu-id="51fb6-221">Definition</span></span> | <span data-ttu-id="51fb6-222">Exempel</span><span class="sxs-lookup"><span data-stu-id="51fb6-222">Examples</span></span>
---|---|---
<span data-ttu-id="51fb6-223">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="51fb6-223">File extension</span></span> | <span data-ttu-id="51fb6-224">Alla filer med tillägget, var som helst på enheten</span><span class="sxs-lookup"><span data-stu-id="51fb6-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="51fb6-225">Fil</span><span class="sxs-lookup"><span data-stu-id="51fb6-225">File</span></span> | <span data-ttu-id="51fb6-226">En specifik fil som identifieras med den fullständiga sökvägen</span><span class="sxs-lookup"><span data-stu-id="51fb6-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="51fb6-227">Mapp</span><span class="sxs-lookup"><span data-stu-id="51fb6-227">Folder</span></span> | <span data-ttu-id="51fb6-228">Alla filer under den angivna mappen (rekursivt)</span><span class="sxs-lookup"><span data-stu-id="51fb6-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="51fb6-229">Process</span><span class="sxs-lookup"><span data-stu-id="51fb6-229">Process</span></span> | <span data-ttu-id="51fb6-230">En specifik process (anges antingen med den fullständiga sökvägen eller filnamnet) och alla filer som öppnas av den</span><span class="sxs-lookup"><span data-stu-id="51fb6-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="51fb6-231">Sökvägarna ovan måste vara hårda länkar, inte symboliska länkar, för att uteslutas.</span><span class="sxs-lookup"><span data-stu-id="51fb6-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="51fb6-232">Du kan kontrollera om en sökväg är en symbolisk länk genom att köra `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="51fb6-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="51fb6-233">Undantag för filer, mappar och processer stöder följande jokertecken:</span><span class="sxs-lookup"><span data-stu-id="51fb6-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="51fb6-234">Jokertecken</span><span class="sxs-lookup"><span data-stu-id="51fb6-234">Wildcard</span></span> | <span data-ttu-id="51fb6-235">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="51fb6-235">Description</span></span> | <span data-ttu-id="51fb6-236">Exempel</span><span class="sxs-lookup"><span data-stu-id="51fb6-236">Example</span></span> | <span data-ttu-id="51fb6-237">Matchningar</span><span class="sxs-lookup"><span data-stu-id="51fb6-237">Matches</span></span> | <span data-ttu-id="51fb6-238">Matchar inte</span><span class="sxs-lookup"><span data-stu-id="51fb6-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="51fb6-239">Matchar valbara antal tecken inklusive inga (observera att när det här jokertecknet används inuti en sökväg kommer det bara att ersätta en mapp)</span><span class="sxs-lookup"><span data-stu-id="51fb6-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="51fb6-240">?</span><span class="sxs-lookup"><span data-stu-id="51fb6-240">?</span></span> | <span data-ttu-id="51fb6-241">Matchar ett enstaka tecken</span><span class="sxs-lookup"><span data-stu-id="51fb6-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="51fb6-242">Sökvägstyp (fil/katalog)</span><span class="sxs-lookup"><span data-stu-id="51fb6-242">Path type (file / directory)</span></span>

<span data-ttu-id="51fb6-243">Ange om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="51fb6-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="51fb6-244">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-244">Section</span></span>|<span data-ttu-id="51fb6-245">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-246">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-247">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-247">**Key**</span></span> | <span data-ttu-id="51fb6-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="51fb6-248">isDirectory</span></span> |
| <span data-ttu-id="51fb6-249">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-249">**Data type**</span></span> | <span data-ttu-id="51fb6-250">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-250">Boolean</span></span> |
| <span data-ttu-id="51fb6-251">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-251">**Possible values**</span></span> | <span data-ttu-id="51fb6-252">false (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-252">false (default)</span></span> <br/> <span data-ttu-id="51fb6-253">true</span><span class="sxs-lookup"><span data-stu-id="51fb6-253">true</span></span> |
| <span data-ttu-id="51fb6-254">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-254">**Comments**</span></span> | <span data-ttu-id="51fb6-255">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="51fb6-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="51fb6-256">Filnamnstillägget är undantaget från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="51fb6-256">File extension excluded from the scan</span></span>

<span data-ttu-id="51fb6-257">Ange innehåll som ska undantas från att genomsökas efter filtillägg.</span><span class="sxs-lookup"><span data-stu-id="51fb6-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="51fb6-258">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-258">Section</span></span>|<span data-ttu-id="51fb6-259">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-260">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-261">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-261">**Key**</span></span> | <span data-ttu-id="51fb6-262">tillägg</span><span class="sxs-lookup"><span data-stu-id="51fb6-262">extension</span></span> |
| <span data-ttu-id="51fb6-263">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-263">**Data type**</span></span> | <span data-ttu-id="51fb6-264">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-264">String</span></span> |
| <span data-ttu-id="51fb6-265">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-265">**Possible values**</span></span> | <span data-ttu-id="51fb6-266">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="51fb6-266">valid file extensions</span></span> |
| <span data-ttu-id="51fb6-267">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-267">**Comments**</span></span> | <span data-ttu-id="51fb6-268">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="51fb6-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="51fb6-269">Process som uteslutits från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="51fb6-269">Process excluded from the scan</span></span>

<span data-ttu-id="51fb6-270">Ange en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="51fb6-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="51fb6-271">Processen kan antingen anges med sitt namn (t.ex. `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="51fb6-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="51fb6-272">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-272">Section</span></span>|<span data-ttu-id="51fb6-273">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-274">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-275">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-275">**Key**</span></span> | <span data-ttu-id="51fb6-276">Namn</span><span class="sxs-lookup"><span data-stu-id="51fb6-276">name</span></span> |
| <span data-ttu-id="51fb6-277">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-277">**Data type**</span></span> | <span data-ttu-id="51fb6-278">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-278">String</span></span> |
| <span data-ttu-id="51fb6-279">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-279">**Possible values**</span></span> | <span data-ttu-id="51fb6-280">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-280">any string</span></span> |
| <span data-ttu-id="51fb6-281">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-281">**Comments**</span></span> | <span data-ttu-id="51fb6-282">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="51fb6-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="51fb6-283">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="51fb6-283">Allowed threats</span></span>

<span data-ttu-id="51fb6-284">Ange hot med namn som inte blockeras av Defender för Slutpunkt på Mac.</span><span class="sxs-lookup"><span data-stu-id="51fb6-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="51fb6-285">Dessa hot kommer att tillåtas att köras.</span><span class="sxs-lookup"><span data-stu-id="51fb6-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="51fb6-286">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-286">Section</span></span>|<span data-ttu-id="51fb6-287">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-288">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-289">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-289">**Key**</span></span> | <span data-ttu-id="51fb6-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="51fb6-290">allowedThreats</span></span> |
| <span data-ttu-id="51fb6-291">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-291">**Data type**</span></span> | <span data-ttu-id="51fb6-292">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="51fb6-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="51fb6-293">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="51fb6-293">Disallowed threat actions</span></span>

<span data-ttu-id="51fb6-294">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="51fb6-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="51fb6-295">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="51fb6-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="51fb6-296">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-296">Section</span></span>|<span data-ttu-id="51fb6-297">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-298">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-299">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-299">**Key**</span></span> | <span data-ttu-id="51fb6-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="51fb6-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="51fb6-301">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-301">**Data type**</span></span> | <span data-ttu-id="51fb6-302">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="51fb6-302">Array of strings</span></span> |
| <span data-ttu-id="51fb6-303">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-303">**Possible values**</span></span> | <span data-ttu-id="51fb6-304">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="51fb6-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="51fb6-305">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="51fb6-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="51fb6-306">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-306">**Comments**</span></span> | <span data-ttu-id="51fb6-307">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="51fb6-308">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="51fb6-308">Threat type settings</span></span>

<span data-ttu-id="51fb6-309">Ange hur vissa hottyper hanteras av Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="51fb6-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="51fb6-310">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-310">Section</span></span>|<span data-ttu-id="51fb6-311">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-312">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-313">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-313">**Key**</span></span> | <span data-ttu-id="51fb6-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="51fb6-314">threatTypeSettings</span></span> |
| <span data-ttu-id="51fb6-315">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-315">**Data type**</span></span> | <span data-ttu-id="51fb6-316">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-317">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-317">**Comments**</span></span> | <span data-ttu-id="51fb6-318">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="51fb6-319">Hottyp</span><span class="sxs-lookup"><span data-stu-id="51fb6-319">Threat type</span></span>

<span data-ttu-id="51fb6-320">Ange hottyper.</span><span class="sxs-lookup"><span data-stu-id="51fb6-320">Specify threat types.</span></span>

|<span data-ttu-id="51fb6-321">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-321">Section</span></span>|<span data-ttu-id="51fb6-322">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-323">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-324">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-324">**Key**</span></span> | <span data-ttu-id="51fb6-325">tangent</span><span class="sxs-lookup"><span data-stu-id="51fb6-325">key</span></span> |
| <span data-ttu-id="51fb6-326">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-326">**Data type**</span></span> | <span data-ttu-id="51fb6-327">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-327">String</span></span> |
| <span data-ttu-id="51fb6-328">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-328">**Possible values**</span></span> | <span data-ttu-id="51fb6-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="51fb6-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="51fb6-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="51fb6-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="51fb6-331">Åtgärd att vidta</span><span class="sxs-lookup"><span data-stu-id="51fb6-331">Action to take</span></span>

<span data-ttu-id="51fb6-332">Ange vilken åtgärd som ska vidtas när ett hot av den typ som anges i föregående avsnitt identifieras.</span><span class="sxs-lookup"><span data-stu-id="51fb6-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="51fb6-333">Välj bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="51fb6-333">Choose from the following options:</span></span>

- <span data-ttu-id="51fb6-334">**Granskning:** din enhet är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="51fb6-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="51fb6-335">**Blockering:** din enhet är skyddad mot den här typen av hot och du meddelas i användargränssnittet och säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="51fb6-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="51fb6-336">**Av:** din enhet är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="51fb6-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="51fb6-337">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-337">Section</span></span>|<span data-ttu-id="51fb6-338">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-339">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-340">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-340">**Key**</span></span> | <span data-ttu-id="51fb6-341">värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-341">value</span></span> |
| <span data-ttu-id="51fb6-342">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-342">**Data type**</span></span> | <span data-ttu-id="51fb6-343">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-343">String</span></span> |
| <span data-ttu-id="51fb6-344">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-344">**Possible values**</span></span> | <span data-ttu-id="51fb6-345">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-345">audit (default)</span></span> <br/> <span data-ttu-id="51fb6-346">blockera</span><span class="sxs-lookup"><span data-stu-id="51fb6-346">block</span></span> <br/> <span data-ttu-id="51fb6-347">av</span><span class="sxs-lookup"><span data-stu-id="51fb6-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="51fb6-348">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="51fb6-348">Threat type settings merge policy</span></span>

<span data-ttu-id="51fb6-349">Ange kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="51fb6-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="51fb6-350">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="51fb6-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="51fb6-351">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="51fb6-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="51fb6-352">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-352">Section</span></span>|<span data-ttu-id="51fb6-353">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-354">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-355">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-355">**Key**</span></span> | <span data-ttu-id="51fb6-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="51fb6-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="51fb6-357">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-357">**Data type**</span></span> | <span data-ttu-id="51fb6-358">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-358">String</span></span> |
| <span data-ttu-id="51fb6-359">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-359">**Possible values**</span></span> | <span data-ttu-id="51fb6-360">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-360">merge (default)</span></span> <br/> <span data-ttu-id="51fb6-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="51fb6-361">admin_only</span></span> |
| <span data-ttu-id="51fb6-362">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-362">**Comments**</span></span> | <span data-ttu-id="51fb6-363">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="51fb6-364">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="51fb6-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="51fb6-365">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="51fb6-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="51fb6-366">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="51fb6-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="51fb6-367">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="51fb6-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="51fb6-368">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-368">Section</span></span>|<span data-ttu-id="51fb6-369">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-370">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-371">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-371">**Key**</span></span> | <span data-ttu-id="51fb6-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="51fb6-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="51fb6-373">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-373">**Data type**</span></span> | <span data-ttu-id="51fb6-374">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-374">String</span></span> |
| <span data-ttu-id="51fb6-375">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-375">**Possible values**</span></span> | <span data-ttu-id="51fb6-376">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="51fb6-376">90 (default).</span></span> <span data-ttu-id="51fb6-377">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="51fb6-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="51fb6-378">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-378">**Comments**</span></span> | <span data-ttu-id="51fb6-379">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="51fb6-380">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="51fb6-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="51fb6-381">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="51fb6-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="51fb6-382">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="51fb6-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="51fb6-383">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-383">Section</span></span>|<span data-ttu-id="51fb6-384">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-385">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-386">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-386">**Key**</span></span> | <span data-ttu-id="51fb6-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="51fb6-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="51fb6-388">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-388">**Data type**</span></span> | <span data-ttu-id="51fb6-389">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-389">String</span></span> |
| <span data-ttu-id="51fb6-390">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-390">**Possible values**</span></span> | <span data-ttu-id="51fb6-391">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="51fb6-391">10000 (default).</span></span> <span data-ttu-id="51fb6-392">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="51fb6-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="51fb6-393">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-393">**Comments**</span></span> | <span data-ttu-id="51fb6-394">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="51fb6-395">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="51fb6-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="51fb6-396">Konfigurera de molnbaserade skyddsfunktionerna i Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="51fb6-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="51fb6-397">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-397">Section</span></span>|<span data-ttu-id="51fb6-398">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-399">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-400">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-400">**Key**</span></span> | <span data-ttu-id="51fb6-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="51fb6-401">cloudService</span></span> |
| <span data-ttu-id="51fb6-402">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-402">**Data type**</span></span> | <span data-ttu-id="51fb6-403">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-404">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-404">**Comments**</span></span> | <span data-ttu-id="51fb6-405">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="51fb6-406">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="51fb6-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="51fb6-407">Ange om du vill aktivera moln levererat skydd på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="51fb6-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="51fb6-408">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="51fb6-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="51fb6-409">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-409">Section</span></span>|<span data-ttu-id="51fb6-410">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-411">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-412">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-412">**Key**</span></span> | <span data-ttu-id="51fb6-413">aktiverat</span><span class="sxs-lookup"><span data-stu-id="51fb6-413">enabled</span></span> |
| <span data-ttu-id="51fb6-414">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-414">**Data type**</span></span> | <span data-ttu-id="51fb6-415">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-415">Boolean</span></span> |
| <span data-ttu-id="51fb6-416">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-416">**Possible values**</span></span> | <span data-ttu-id="51fb6-417">true (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-417">true (default)</span></span> <br/> <span data-ttu-id="51fb6-418">false</span><span class="sxs-lookup"><span data-stu-id="51fb6-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="51fb6-419">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="51fb6-419">Diagnostic collection level</span></span>

<span data-ttu-id="51fb6-420">Diagnostikdata används för att hålla Microsoft Defender för Endpoint säkert och uppdaterat, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="51fb6-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="51fb6-421">Den här inställningen bestämmer nivån för diagnostik som skickas av Microsoft Defender för Slutpunkt till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51fb6-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="51fb6-422">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-422">Section</span></span>|<span data-ttu-id="51fb6-423">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-424">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-425">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-425">**Key**</span></span> | <span data-ttu-id="51fb6-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="51fb6-426">diagnosticLevel</span></span> |
| <span data-ttu-id="51fb6-427">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-427">**Data type**</span></span> | <span data-ttu-id="51fb6-428">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-428">String</span></span> |
| <span data-ttu-id="51fb6-429">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-429">**Possible values**</span></span> | <span data-ttu-id="51fb6-430">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-430">optional (default)</span></span> <br/> <span data-ttu-id="51fb6-431">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="51fb6-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="51fb6-432">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="51fb6-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="51fb6-433">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51fb6-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="51fb6-434">Du uppmanas att ange om den inskickade filen troligen innehåller personlig information.</span><span class="sxs-lookup"><span data-stu-id="51fb6-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="51fb6-435">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-435">Section</span></span>|<span data-ttu-id="51fb6-436">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-437">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-438">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-438">**Key**</span></span> | <span data-ttu-id="51fb6-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="51fb6-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="51fb6-440">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-440">**Data type**</span></span> | <span data-ttu-id="51fb6-441">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-441">Boolean</span></span> |
| <span data-ttu-id="51fb6-442">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-442">**Possible values**</span></span> | <span data-ttu-id="51fb6-443">true (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-443">true (default)</span></span> <br/> <span data-ttu-id="51fb6-444">false</span><span class="sxs-lookup"><span data-stu-id="51fb6-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="51fb6-445">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="51fb6-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="51fb6-446">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="51fb6-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="51fb6-447">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-447">Section</span></span>|<span data-ttu-id="51fb6-448">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-449">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-449">**Key**</span></span> | <span data-ttu-id="51fb6-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="51fb6-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="51fb6-451">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-451">**Data type**</span></span> | <span data-ttu-id="51fb6-452">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-452">Boolean</span></span> |
| <span data-ttu-id="51fb6-453">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-453">**Possible values**</span></span> | <span data-ttu-id="51fb6-454">true (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-454">true (default)</span></span> <br/> <span data-ttu-id="51fb6-455">false</span><span class="sxs-lookup"><span data-stu-id="51fb6-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="51fb6-456">Inställningar för användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-456">User interface preferences</span></span>

<span data-ttu-id="51fb6-457">Hantera inställningar för användargränssnittet i Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="51fb6-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="51fb6-458">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-458">Section</span></span>|<span data-ttu-id="51fb6-459">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-460">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-461">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-461">**Key**</span></span> | <span data-ttu-id="51fb6-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="51fb6-462">userInterface</span></span> |
| <span data-ttu-id="51fb6-463">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-463">**Data type**</span></span> | <span data-ttu-id="51fb6-464">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-465">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-465">**Comments**</span></span> | <span data-ttu-id="51fb6-466">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="51fb6-467">Visa/dölj statusmenyikon</span><span class="sxs-lookup"><span data-stu-id="51fb6-467">Show / hide status menu icon</span></span>

<span data-ttu-id="51fb6-468">Ange om du vill visa eller dölja statusmenyikonen i det övre högra hörnet av skärmen.</span><span class="sxs-lookup"><span data-stu-id="51fb6-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="51fb6-469">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-469">Section</span></span>|<span data-ttu-id="51fb6-470">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-471">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-472">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-472">**Key**</span></span> | <span data-ttu-id="51fb6-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="51fb6-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="51fb6-474">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-474">**Data type**</span></span> | <span data-ttu-id="51fb6-475">Boolesk</span><span class="sxs-lookup"><span data-stu-id="51fb6-475">Boolean</span></span> |
| <span data-ttu-id="51fb6-476">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-476">**Possible values**</span></span> | <span data-ttu-id="51fb6-477">false (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-477">false (default)</span></span> <br/> <span data-ttu-id="51fb6-478">true</span><span class="sxs-lookup"><span data-stu-id="51fb6-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="51fb6-479">Visa/dölj alternativ för att skicka feedback</span><span class="sxs-lookup"><span data-stu-id="51fb6-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="51fb6-480">Ange om användare kan skicka feedback till Microsoft genom att gå till `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="51fb6-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="51fb6-481">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-481">Section</span></span>|<span data-ttu-id="51fb6-482">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-483">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-484">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-484">**Key**</span></span> | <span data-ttu-id="51fb6-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="51fb6-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="51fb6-486">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-486">**Data type**</span></span> | <span data-ttu-id="51fb6-487">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-487">String</span></span> |
| <span data-ttu-id="51fb6-488">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-488">**Possible values**</span></span> | <span data-ttu-id="51fb6-489">aktiverad (standard)</span><span class="sxs-lookup"><span data-stu-id="51fb6-489">enabled (default)</span></span> <br/> <span data-ttu-id="51fb6-490">inaktiverad</span><span class="sxs-lookup"><span data-stu-id="51fb6-490">disabled</span></span> |
| <span data-ttu-id="51fb6-491">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-491">**Comments**</span></span> | <span data-ttu-id="51fb6-492">Tillgängligt i Microsoft Defender för slutpunkt version 101.19.61 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="51fb6-493">Inställningar för identifiering av slutpunkter och svar</span><span class="sxs-lookup"><span data-stu-id="51fb6-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="51fb6-494">Hantera inställningarna för den identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt) av Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="51fb6-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="51fb6-495">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-495">Section</span></span>|<span data-ttu-id="51fb6-496">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-497">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-498">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-498">**Key**</span></span> | <span data-ttu-id="51fb6-499">edr</span><span class="sxs-lookup"><span data-stu-id="51fb6-499">edr</span></span> |
| <span data-ttu-id="51fb6-500">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-500">**Data type**</span></span> | <span data-ttu-id="51fb6-501">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-502">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-502">**Comments**</span></span> | <span data-ttu-id="51fb6-503">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="51fb6-504">Enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="51fb6-504">Device tags</span></span>

<span data-ttu-id="51fb6-505">Ange ett taggnamn och dess värde.</span><span class="sxs-lookup"><span data-stu-id="51fb6-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="51fb6-506">GROUP-taggen taggar enheten med det angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="51fb6-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="51fb6-507">Taggen återspeglas i portalen under enhetssidan och kan användas för filtrering och gruppering av enheter.</span><span class="sxs-lookup"><span data-stu-id="51fb6-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="51fb6-508">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-508">Section</span></span>|<span data-ttu-id="51fb6-509">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-510">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-511">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-511">**Key**</span></span> | <span data-ttu-id="51fb6-512">taggar</span><span class="sxs-lookup"><span data-stu-id="51fb6-512">tags</span></span> |
| <span data-ttu-id="51fb6-513">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-513">**Data type**</span></span> | <span data-ttu-id="51fb6-514">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="51fb6-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="51fb6-515">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="51fb6-515">**Comments**</span></span> | <span data-ttu-id="51fb6-516">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="51fb6-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="51fb6-517">Typ av tagg</span><span class="sxs-lookup"><span data-stu-id="51fb6-517">Type of tag</span></span>

<span data-ttu-id="51fb6-518">Anger typ av tagg</span><span class="sxs-lookup"><span data-stu-id="51fb6-518">Specifies the type of tag</span></span>

|<span data-ttu-id="51fb6-519">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-519">Section</span></span>|<span data-ttu-id="51fb6-520">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-521">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-522">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-522">**Key**</span></span> | <span data-ttu-id="51fb6-523">tangent</span><span class="sxs-lookup"><span data-stu-id="51fb6-523">key</span></span> |
| <span data-ttu-id="51fb6-524">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-524">**Data type**</span></span> | <span data-ttu-id="51fb6-525">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-525">String</span></span> |
| <span data-ttu-id="51fb6-526">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="51fb6-527">Värdet på taggen</span><span class="sxs-lookup"><span data-stu-id="51fb6-527">Value of tag</span></span>

<span data-ttu-id="51fb6-528">Anger värdet för taggen</span><span class="sxs-lookup"><span data-stu-id="51fb6-528">Specifies the value of tag</span></span>

|<span data-ttu-id="51fb6-529">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="51fb6-529">Section</span></span>|<span data-ttu-id="51fb6-530">Värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="51fb6-531">**Domän**</span><span class="sxs-lookup"><span data-stu-id="51fb6-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="51fb6-532">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="51fb6-532">**Key**</span></span> | <span data-ttu-id="51fb6-533">värde</span><span class="sxs-lookup"><span data-stu-id="51fb6-533">value</span></span> |
| <span data-ttu-id="51fb6-534">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="51fb6-534">**Data type**</span></span> | <span data-ttu-id="51fb6-535">Sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-535">String</span></span> |
| <span data-ttu-id="51fb6-536">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="51fb6-536">**Possible values**</span></span> | <span data-ttu-id="51fb6-537">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="51fb6-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="51fb6-538">Du kan bara ange ett värde per taggtyp.</span><span class="sxs-lookup"><span data-stu-id="51fb6-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="51fb6-539">Typ av taggar är unika och bör inte upprepas i samma konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="51fb6-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="51fb6-540">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="51fb6-540">Recommended configuration profile</span></span>

<span data-ttu-id="51fb6-541">För att komma igång rekommenderar vi följande konfiguration för ditt företag för att dra nytta av alla skyddsfunktioner som Microsoft Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="51fb6-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="51fb6-542">Följande konfigurationsprofil (eller, vid JAMF, en egenskapslista som kan laddas upp till profilen för anpassade inställningar) kommer att:</span><span class="sxs-lookup"><span data-stu-id="51fb6-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="51fb6-543">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="51fb6-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="51fb6-544">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="51fb6-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="51fb6-545">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="51fb6-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="51fb6-546">**Arkiveringsskyddet** (en fil med hög komprimeringshastighet) granskas i Microsoft Defender för Slutpunktsloggar</span><span class="sxs-lookup"><span data-stu-id="51fb6-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="51fb6-547">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="51fb6-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="51fb6-548">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="51fb6-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="51fb6-549">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="51fb6-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="51fb6-550">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="51fb6-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="51fb6-551">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="51fb6-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="51fb6-552">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="51fb6-552">Full configuration profile example</span></span>

<span data-ttu-id="51fb6-553">Följande mallar innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över Microsoft Defender för slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="51fb6-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="51fb6-554">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="51fb6-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="51fb6-555">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="51fb6-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="51fb6-556">Egenskapslistverifiering</span><span class="sxs-lookup"><span data-stu-id="51fb6-556">Property list validation</span></span>

<span data-ttu-id="51fb6-557">Egenskapslistan måste vara en giltig *.plist-fil.*</span><span class="sxs-lookup"><span data-stu-id="51fb6-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="51fb6-558">Det här kan kontrolleras genom att köra:</span><span class="sxs-lookup"><span data-stu-id="51fb6-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="51fb6-559">Om filen är rätt utformad returnerar kommandot ovan en utgångskod `OK` för `0` .</span><span class="sxs-lookup"><span data-stu-id="51fb6-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="51fb6-560">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="51fb6-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="51fb6-561">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="51fb6-561">Configuration profile deployment</span></span>

<span data-ttu-id="51fb6-562">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via hanteringskonsolen som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="51fb6-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="51fb6-563">I följande avsnitt finns instruktioner om hur du distribuerar den här profilen med HJÄLP av JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="51fb6-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="51fb6-564">JAMF-distribution</span><span class="sxs-lookup"><span data-stu-id="51fb6-564">JAMF deployment</span></span>

<span data-ttu-id="51fb6-565">Från JAMF-konsolen öppnar du Datorkonfigurationsprofiler , navigerar till den konfigurationsprofil du vill använda och väljer  >  sedan Custom **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="51fb6-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="51fb6-566">Skapa en post med `com.microsoft.wdav` som inställningsdomän och ladda upp den *.plist som produceras* tidigare.</span><span class="sxs-lookup"><span data-stu-id="51fb6-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="51fb6-567">Du måste ange rätt inställningsdomän ( ). Annars kan inte inställningarna identifieras av `com.microsoft.wdav` Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="51fb6-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="51fb6-568">Intune-distribution</span><span class="sxs-lookup"><span data-stu-id="51fb6-568">Intune deployment</span></span>

1. <span data-ttu-id="51fb6-569">Öppna **Hantera**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51fb6-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="51fb6-570">Välj **Hantera**  >  **profiler**  >  **skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="51fb6-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="51fb6-571">Välj ett namn för profilen.</span><span class="sxs-lookup"><span data-stu-id="51fb6-571">Choose a name for the profile.</span></span> <span data-ttu-id="51fb6-572">Ändra **Platform=macOS** till **Profiltyp=Anpassad**.</span><span class="sxs-lookup"><span data-stu-id="51fb6-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="51fb6-573">Välj Konfigurera.</span><span class="sxs-lookup"><span data-stu-id="51fb6-573">Select Configure.</span></span>

3. <span data-ttu-id="51fb6-574">Spara den .plist som produceras tidigare som `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="51fb6-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="51fb6-575">Ange `com.microsoft.wdav` namnet på den anpassade **konfigurationsprofilen.**</span><span class="sxs-lookup"><span data-stu-id="51fb6-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="51fb6-576">Öppna konfigurationsprofilen och ladda upp `com.microsoft.wdav.xml` filen.</span><span class="sxs-lookup"><span data-stu-id="51fb6-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="51fb6-577">(Den här filen skapades i steg 3.)</span><span class="sxs-lookup"><span data-stu-id="51fb6-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="51fb6-578">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="51fb6-578">Select **OK**.</span></span>

7. <span data-ttu-id="51fb6-579">Välj   >  **Hantera uppgifter.**</span><span class="sxs-lookup"><span data-stu-id="51fb6-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="51fb6-580">På fliken **Inkludera** väljer du **Tilldela till alla användare & alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="51fb6-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="51fb6-581">Du måste ange rätt namn på den anpassade konfigurationsprofilen. Annars identifieras inte de här inställningarna av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="51fb6-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="51fb6-582">Resurser</span><span class="sxs-lookup"><span data-stu-id="51fb6-582">Resources</span></span>

- [<span data-ttu-id="51fb6-583">Referens för konfigurationsprofil (Utvecklardokumentation för Apple)</span><span class="sxs-lookup"><span data-stu-id="51fb6-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
