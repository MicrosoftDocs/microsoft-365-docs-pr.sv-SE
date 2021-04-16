---
title: Ange inställningar för Microsoft Defender för Slutpunkt för Mac
description: Konfigurera Microsoft Defender för Slutpunkt för Mac i företagsorganisationer.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860929"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3bf9d-104">Ange inställningar för Microsoft Defender för Slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="3bf9d-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3bf9d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-105">**Applies to:**</span></span>

- [<span data-ttu-id="3bf9d-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="3bf9d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="3bf9d-107">Den här artikeln innehåller instruktioner för hur du anger inställningar för Microsoft Defender för Slutpunkt på macOS i företagsorganisationer.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="3bf9d-108">Information om hur du konfigurerar Microsoft Defender för slutpunkt i macOS med kommandoradsgränssnittet finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="3bf9d-109">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="3bf9d-109">Summary</span></span>

<span data-ttu-id="3bf9d-110">I företagsorganisationer kan Microsoft Defender för slutpunkt i macOS hanteras via en konfigurationsprofil som distribueras med ett av flera hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="3bf9d-111">De inställningar som hanteras av ditt säkerhetsteam har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="3bf9d-112">Om du vill ändra inställningar som ställts in via konfigurationsprofilen krävs eskalerade behörigheter och är inte tillgängligt för användare utan administrativ behörighet.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="3bf9d-113">I den här artikeln beskrivs konfigurationsprofilens struktur, en rekommenderad profil som du kan använda för att komma igång och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="3bf9d-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="3bf9d-114">Configuration profile structure</span></span>

<span data-ttu-id="3bf9d-115">Konfigurationsprofilen är en *PLIST-fil* som består av poster som identifieras med en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="3bf9d-116">Värdena kan antingen vara enkla (till exempel ett numeriskt värde) eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="3bf9d-117">Konfigurationsprofilens layout beror på vilken hanteringskonsol du använder.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="3bf9d-118">Följande avsnitt innehåller exempel på konfigurationsprofiler för JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="3bf9d-119">Den översta nivån i konfigurationsprofilen innehåller produktomfattande inställningar och poster för underavsnitt av Microsoft Defender för slutpunkt, som förklaras mer ingående i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="3bf9d-120">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="3bf9d-120">Antivirus engine preferences</span></span>

<span data-ttu-id="3bf9d-121">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="3bf9d-122">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-122">Section</span></span>|<span data-ttu-id="3bf9d-123">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-124">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-125">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-125">**Key**</span></span> | <span data-ttu-id="3bf9d-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="3bf9d-126">antivirusEngine</span></span> |
| <span data-ttu-id="3bf9d-127">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-127">**Data type**</span></span> | <span data-ttu-id="3bf9d-128">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-129">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-129">**Comments**</span></span> | <span data-ttu-id="3bf9d-130">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="3bf9d-131">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="3bf9d-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="3bf9d-132">Ange om du vill aktivera realtidsskydd som genomsöker filer när de används.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="3bf9d-133">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-133">Section</span></span>|<span data-ttu-id="3bf9d-134">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-135">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-136">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-136">**Key**</span></span> | <span data-ttu-id="3bf9d-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3bf9d-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="3bf9d-138">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-138">**Data type**</span></span> | <span data-ttu-id="3bf9d-139">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-139">Boolean</span></span> |
| <span data-ttu-id="3bf9d-140">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-140">**Possible values**</span></span> | <span data-ttu-id="3bf9d-141">true (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-141">true (default)</span></span> <br/> <span data-ttu-id="3bf9d-142">false</span><span class="sxs-lookup"><span data-stu-id="3bf9d-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="3bf9d-143">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="3bf9d-143">Enable / disable passive mode</span></span>

<span data-ttu-id="3bf9d-144">Ange om antivirusmotorn körs i passiv form.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="3bf9d-145">Passivt läge har följande konsekvenser:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="3bf9d-146">Realtidsskydd är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="3bf9d-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="3bf9d-147">Skanning på begäran är aktiverat</span><span class="sxs-lookup"><span data-stu-id="3bf9d-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="3bf9d-148">Automatisk åtgärd för hot är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="3bf9d-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="3bf9d-149">Säkerhetsintelligensuppdateringar är aktiverat</span><span class="sxs-lookup"><span data-stu-id="3bf9d-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="3bf9d-150">Statusmenyikonen är dold</span><span class="sxs-lookup"><span data-stu-id="3bf9d-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="3bf9d-151">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-151">Section</span></span>|<span data-ttu-id="3bf9d-152">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-153">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-154">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-154">**Key**</span></span> | <span data-ttu-id="3bf9d-155">passivläge</span><span class="sxs-lookup"><span data-stu-id="3bf9d-155">passiveMode</span></span> |
| <span data-ttu-id="3bf9d-156">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-156">**Data type**</span></span> | <span data-ttu-id="3bf9d-157">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-157">Boolean</span></span> |
| <span data-ttu-id="3bf9d-158">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-158">**Possible values**</span></span> | <span data-ttu-id="3bf9d-159">false (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-159">false (default)</span></span> <br/> <span data-ttu-id="3bf9d-160">true</span><span class="sxs-lookup"><span data-stu-id="3bf9d-160">true</span></span> |
| <span data-ttu-id="3bf9d-161">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-161">**Comments**</span></span> | <span data-ttu-id="3bf9d-162">Tillgängligt i Microsoft Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="3bf9d-163">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="3bf9d-163">Exclusion merge policy</span></span>

<span data-ttu-id="3bf9d-164">Ange kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="3bf9d-165">Det här kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="3bf9d-166">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="3bf9d-167">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-167">Section</span></span>|<span data-ttu-id="3bf9d-168">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-169">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-170">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-170">**Key**</span></span> | <span data-ttu-id="3bf9d-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3bf9d-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="3bf9d-172">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-172">**Data type**</span></span> | <span data-ttu-id="3bf9d-173">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-173">String</span></span> |
| <span data-ttu-id="3bf9d-174">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-174">**Possible values**</span></span> | <span data-ttu-id="3bf9d-175">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-175">merge (default)</span></span> <br/> <span data-ttu-id="3bf9d-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="3bf9d-176">admin_only</span></span> |
| <span data-ttu-id="3bf9d-177">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-177">**Comments**</span></span> | <span data-ttu-id="3bf9d-178">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="3bf9d-179">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="3bf9d-179">Scan exclusions</span></span>

<span data-ttu-id="3bf9d-180">Ange enheter som inte ska genomsökas.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="3bf9d-181">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="3bf9d-182">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-182">Section</span></span>|<span data-ttu-id="3bf9d-183">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-184">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-185">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-185">**Key**</span></span> | <span data-ttu-id="3bf9d-186">undantag</span><span class="sxs-lookup"><span data-stu-id="3bf9d-186">exclusions</span></span> |
| <span data-ttu-id="3bf9d-187">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-187">**Data type**</span></span> | <span data-ttu-id="3bf9d-188">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-189">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-189">**Comments**</span></span> | <span data-ttu-id="3bf9d-190">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="3bf9d-191">Typ av undantag</span><span class="sxs-lookup"><span data-stu-id="3bf9d-191">Type of exclusion</span></span>

<span data-ttu-id="3bf9d-192">Ange innehåll som ska undantas från att genomsökas efter typ.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="3bf9d-193">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-193">Section</span></span>|<span data-ttu-id="3bf9d-194">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-195">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-196">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-196">**Key**</span></span> | <span data-ttu-id="3bf9d-197">$type</span><span class="sxs-lookup"><span data-stu-id="3bf9d-197">$type</span></span> |
| <span data-ttu-id="3bf9d-198">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-198">**Data type**</span></span> | <span data-ttu-id="3bf9d-199">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-199">String</span></span> |
| <span data-ttu-id="3bf9d-200">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-200">**Possible values**</span></span> | <span data-ttu-id="3bf9d-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3bf9d-201">excludedPath</span></span> <br/> <span data-ttu-id="3bf9d-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3bf9d-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="3bf9d-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3bf9d-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="3bf9d-204">Sökväg till utelämnat innehåll</span><span class="sxs-lookup"><span data-stu-id="3bf9d-204">Path to excluded content</span></span>

<span data-ttu-id="3bf9d-205">Ange innehåll som inte ska genomsökas efter fullständig sökväg.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="3bf9d-206">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-206">Section</span></span>|<span data-ttu-id="3bf9d-207">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-208">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-209">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-209">**Key**</span></span> | <span data-ttu-id="3bf9d-210">sökväg</span><span class="sxs-lookup"><span data-stu-id="3bf9d-210">path</span></span> |
| <span data-ttu-id="3bf9d-211">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-211">**Data type**</span></span> | <span data-ttu-id="3bf9d-212">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-212">String</span></span> |
| <span data-ttu-id="3bf9d-213">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-213">**Possible values**</span></span> | <span data-ttu-id="3bf9d-214">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-214">valid paths</span></span> |
| <span data-ttu-id="3bf9d-215">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-215">**Comments**</span></span> | <span data-ttu-id="3bf9d-216">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="3bf9d-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="3bf9d-217">Sökvägstyp (fil/katalog)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-217">Path type (file / directory)</span></span>

<span data-ttu-id="3bf9d-218">Ange om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="3bf9d-219">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-219">Section</span></span>|<span data-ttu-id="3bf9d-220">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-221">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-222">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-222">**Key**</span></span> | <span data-ttu-id="3bf9d-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="3bf9d-223">isDirectory</span></span> |
| <span data-ttu-id="3bf9d-224">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-224">**Data type**</span></span> | <span data-ttu-id="3bf9d-225">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-225">Boolean</span></span> |
| <span data-ttu-id="3bf9d-226">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-226">**Possible values**</span></span> | <span data-ttu-id="3bf9d-227">false (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-227">false (default)</span></span> <br/> <span data-ttu-id="3bf9d-228">true</span><span class="sxs-lookup"><span data-stu-id="3bf9d-228">true</span></span> |
| <span data-ttu-id="3bf9d-229">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-229">**Comments**</span></span> | <span data-ttu-id="3bf9d-230">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="3bf9d-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="3bf9d-231">Filnamnstillägget är undantaget från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="3bf9d-231">File extension excluded from the scan</span></span>

<span data-ttu-id="3bf9d-232">Ange innehåll som ska undantas från att genomsökas efter filtillägg.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="3bf9d-233">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-233">Section</span></span>|<span data-ttu-id="3bf9d-234">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-235">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-236">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-236">**Key**</span></span> | <span data-ttu-id="3bf9d-237">tillägg</span><span class="sxs-lookup"><span data-stu-id="3bf9d-237">extension</span></span> |
| <span data-ttu-id="3bf9d-238">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-238">**Data type**</span></span> | <span data-ttu-id="3bf9d-239">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-239">String</span></span> |
| <span data-ttu-id="3bf9d-240">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-240">**Possible values**</span></span> | <span data-ttu-id="3bf9d-241">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="3bf9d-241">valid file extensions</span></span> |
| <span data-ttu-id="3bf9d-242">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-242">**Comments**</span></span> | <span data-ttu-id="3bf9d-243">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="3bf9d-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="3bf9d-244">Process som uteslutits från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="3bf9d-244">Process excluded from the scan</span></span>

<span data-ttu-id="3bf9d-245">Ange en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="3bf9d-246">Processen kan antingen anges med sitt namn (t.ex. `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="3bf9d-247">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-247">Section</span></span>|<span data-ttu-id="3bf9d-248">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-249">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-250">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-250">**Key**</span></span> | <span data-ttu-id="3bf9d-251">Namn</span><span class="sxs-lookup"><span data-stu-id="3bf9d-251">name</span></span> |
| <span data-ttu-id="3bf9d-252">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-252">**Data type**</span></span> | <span data-ttu-id="3bf9d-253">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-253">String</span></span> |
| <span data-ttu-id="3bf9d-254">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-254">**Possible values**</span></span> | <span data-ttu-id="3bf9d-255">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-255">any string</span></span> |
| <span data-ttu-id="3bf9d-256">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-256">**Comments**</span></span> | <span data-ttu-id="3bf9d-257">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="3bf9d-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="3bf9d-258">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="3bf9d-258">Allowed threats</span></span>

<span data-ttu-id="3bf9d-259">Ange hot med namn som inte blockeras av Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="3bf9d-260">Dessa hot kommer att tillåtas att köras.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="3bf9d-261">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-261">Section</span></span>|<span data-ttu-id="3bf9d-262">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-263">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-264">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-264">**Key**</span></span> | <span data-ttu-id="3bf9d-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3bf9d-265">allowedThreats</span></span> |
| <span data-ttu-id="3bf9d-266">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-266">**Data type**</span></span> | <span data-ttu-id="3bf9d-267">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="3bf9d-268">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="3bf9d-268">Disallowed threat actions</span></span>

<span data-ttu-id="3bf9d-269">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="3bf9d-270">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="3bf9d-271">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-271">Section</span></span>|<span data-ttu-id="3bf9d-272">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-273">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-274">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-274">**Key**</span></span> | <span data-ttu-id="3bf9d-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3bf9d-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="3bf9d-276">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-276">**Data type**</span></span> | <span data-ttu-id="3bf9d-277">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-277">Array of strings</span></span> |
| <span data-ttu-id="3bf9d-278">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-278">**Possible values**</span></span> | <span data-ttu-id="3bf9d-279">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="3bf9d-280">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="3bf9d-281">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-281">**Comments**</span></span> | <span data-ttu-id="3bf9d-282">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="3bf9d-283">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="3bf9d-283">Threat type settings</span></span>

<span data-ttu-id="3bf9d-284">Ange hur vissa hottyper hanteras av Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3bf9d-285">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-285">Section</span></span>|<span data-ttu-id="3bf9d-286">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-287">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-288">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-288">**Key**</span></span> | <span data-ttu-id="3bf9d-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="3bf9d-289">threatTypeSettings</span></span> |
| <span data-ttu-id="3bf9d-290">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-290">**Data type**</span></span> | <span data-ttu-id="3bf9d-291">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-292">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-292">**Comments**</span></span> | <span data-ttu-id="3bf9d-293">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="3bf9d-294">Hottyp</span><span class="sxs-lookup"><span data-stu-id="3bf9d-294">Threat type</span></span>

<span data-ttu-id="3bf9d-295">Ange hottyper.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-295">Specify threat types.</span></span>

|<span data-ttu-id="3bf9d-296">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-296">Section</span></span>|<span data-ttu-id="3bf9d-297">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-298">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-299">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-299">**Key**</span></span> | <span data-ttu-id="3bf9d-300">tangent</span><span class="sxs-lookup"><span data-stu-id="3bf9d-300">key</span></span> |
| <span data-ttu-id="3bf9d-301">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-301">**Data type**</span></span> | <span data-ttu-id="3bf9d-302">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-302">String</span></span> |
| <span data-ttu-id="3bf9d-303">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-303">**Possible values**</span></span> | <span data-ttu-id="3bf9d-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3bf9d-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="3bf9d-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3bf9d-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="3bf9d-306">Åtgärd att vidta</span><span class="sxs-lookup"><span data-stu-id="3bf9d-306">Action to take</span></span>

<span data-ttu-id="3bf9d-307">Ange vilken åtgärd som ska vidtas när ett hot av den typ som anges i föregående avsnitt identifieras.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="3bf9d-308">Välj bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-308">Choose from the following options:</span></span>

- <span data-ttu-id="3bf9d-309">**Granskning:** din enhet är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="3bf9d-310">**Blockering:** din enhet är skyddad mot den här typen av hot och du meddelas i användargränssnittet och säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="3bf9d-311">**Av:** din enhet är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="3bf9d-312">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-312">Section</span></span>|<span data-ttu-id="3bf9d-313">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-314">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-315">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-315">**Key**</span></span> | <span data-ttu-id="3bf9d-316">värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-316">value</span></span> |
| <span data-ttu-id="3bf9d-317">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-317">**Data type**</span></span> | <span data-ttu-id="3bf9d-318">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-318">String</span></span> |
| <span data-ttu-id="3bf9d-319">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-319">**Possible values**</span></span> | <span data-ttu-id="3bf9d-320">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-320">audit (default)</span></span> <br/> <span data-ttu-id="3bf9d-321">blockera</span><span class="sxs-lookup"><span data-stu-id="3bf9d-321">block</span></span> <br/> <span data-ttu-id="3bf9d-322">av</span><span class="sxs-lookup"><span data-stu-id="3bf9d-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="3bf9d-323">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="3bf9d-323">Threat type settings merge policy</span></span>

<span data-ttu-id="3bf9d-324">Ange kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="3bf9d-325">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="3bf9d-326">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="3bf9d-327">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-327">Section</span></span>|<span data-ttu-id="3bf9d-328">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-329">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-330">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-330">**Key**</span></span> | <span data-ttu-id="3bf9d-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3bf9d-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="3bf9d-332">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-332">**Data type**</span></span> | <span data-ttu-id="3bf9d-333">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-333">String</span></span> |
| <span data-ttu-id="3bf9d-334">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-334">**Possible values**</span></span> | <span data-ttu-id="3bf9d-335">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-335">merge (default)</span></span> <br/> <span data-ttu-id="3bf9d-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="3bf9d-336">admin_only</span></span> |
| <span data-ttu-id="3bf9d-337">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-337">**Comments**</span></span> | <span data-ttu-id="3bf9d-338">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="3bf9d-339">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="3bf9d-340">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="3bf9d-341">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="3bf9d-342">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="3bf9d-343">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-343">Section</span></span>|<span data-ttu-id="3bf9d-344">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-345">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-346">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-346">**Key**</span></span> | <span data-ttu-id="3bf9d-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="3bf9d-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="3bf9d-348">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-348">**Data type**</span></span> | <span data-ttu-id="3bf9d-349">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-349">String</span></span> |
| <span data-ttu-id="3bf9d-350">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-350">**Possible values**</span></span> | <span data-ttu-id="3bf9d-351">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-351">90 (default).</span></span> <span data-ttu-id="3bf9d-352">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="3bf9d-353">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-353">**Comments**</span></span> | <span data-ttu-id="3bf9d-354">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="3bf9d-355">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="3bf9d-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="3bf9d-356">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="3bf9d-357">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="3bf9d-358">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-358">Section</span></span>|<span data-ttu-id="3bf9d-359">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-360">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-361">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-361">**Key**</span></span> | <span data-ttu-id="3bf9d-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="3bf9d-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="3bf9d-363">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-363">**Data type**</span></span> | <span data-ttu-id="3bf9d-364">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-364">String</span></span> |
| <span data-ttu-id="3bf9d-365">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-365">**Possible values**</span></span> | <span data-ttu-id="3bf9d-366">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="3bf9d-366">10000 (default).</span></span> <span data-ttu-id="3bf9d-367">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="3bf9d-368">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-368">**Comments**</span></span> | <span data-ttu-id="3bf9d-369">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="3bf9d-370">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="3bf9d-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="3bf9d-371">Konfigurera de molnbaserade skyddsfunktionerna i Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3bf9d-372">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-372">Section</span></span>|<span data-ttu-id="3bf9d-373">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-374">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-375">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-375">**Key**</span></span> | <span data-ttu-id="3bf9d-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="3bf9d-376">cloudService</span></span> |
| <span data-ttu-id="3bf9d-377">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-377">**Data type**</span></span> | <span data-ttu-id="3bf9d-378">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-379">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-379">**Comments**</span></span> | <span data-ttu-id="3bf9d-380">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="3bf9d-381">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="3bf9d-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="3bf9d-382">Ange om du vill aktivera moln levererat skydd på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="3bf9d-383">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="3bf9d-384">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-384">Section</span></span>|<span data-ttu-id="3bf9d-385">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-386">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-387">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-387">**Key**</span></span> | <span data-ttu-id="3bf9d-388">aktiverat</span><span class="sxs-lookup"><span data-stu-id="3bf9d-388">enabled</span></span> |
| <span data-ttu-id="3bf9d-389">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-389">**Data type**</span></span> | <span data-ttu-id="3bf9d-390">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-390">Boolean</span></span> |
| <span data-ttu-id="3bf9d-391">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-391">**Possible values**</span></span> | <span data-ttu-id="3bf9d-392">true (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-392">true (default)</span></span> <br/> <span data-ttu-id="3bf9d-393">false</span><span class="sxs-lookup"><span data-stu-id="3bf9d-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="3bf9d-394">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="3bf9d-394">Diagnostic collection level</span></span>

<span data-ttu-id="3bf9d-395">Diagnostikdata används för att hålla Microsoft Defender för Endpoint säkert och uppdaterat, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="3bf9d-396">Den här inställningen bestämmer nivån för diagnostik som skickas av Microsoft Defender för Slutpunkt till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="3bf9d-397">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-397">Section</span></span>|<span data-ttu-id="3bf9d-398">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-399">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-400">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-400">**Key**</span></span> | <span data-ttu-id="3bf9d-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="3bf9d-401">diagnosticLevel</span></span> |
| <span data-ttu-id="3bf9d-402">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-402">**Data type**</span></span> | <span data-ttu-id="3bf9d-403">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-403">String</span></span> |
| <span data-ttu-id="3bf9d-404">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-404">**Possible values**</span></span> | <span data-ttu-id="3bf9d-405">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-405">optional (default)</span></span> <br/> <span data-ttu-id="3bf9d-406">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="3bf9d-407">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="3bf9d-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="3bf9d-408">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="3bf9d-409">Du uppmanas att ange om den inskickade filen troligen innehåller personlig information.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="3bf9d-410">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-410">Section</span></span>|<span data-ttu-id="3bf9d-411">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-412">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-413">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-413">**Key**</span></span> | <span data-ttu-id="3bf9d-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="3bf9d-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="3bf9d-415">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-415">**Data type**</span></span> | <span data-ttu-id="3bf9d-416">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-416">Boolean</span></span> |
| <span data-ttu-id="3bf9d-417">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-417">**Possible values**</span></span> | <span data-ttu-id="3bf9d-418">true (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-418">true (default)</span></span> <br/> <span data-ttu-id="3bf9d-419">false</span><span class="sxs-lookup"><span data-stu-id="3bf9d-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="3bf9d-420">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="3bf9d-421">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="3bf9d-422">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-422">Section</span></span>|<span data-ttu-id="3bf9d-423">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-424">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-424">**Key**</span></span> | <span data-ttu-id="3bf9d-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="3bf9d-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="3bf9d-426">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-426">**Data type**</span></span> | <span data-ttu-id="3bf9d-427">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-427">Boolean</span></span> |
| <span data-ttu-id="3bf9d-428">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-428">**Possible values**</span></span> | <span data-ttu-id="3bf9d-429">true (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-429">true (default)</span></span> <br/> <span data-ttu-id="3bf9d-430">false</span><span class="sxs-lookup"><span data-stu-id="3bf9d-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="3bf9d-431">Inställningar för användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-431">User interface preferences</span></span>

<span data-ttu-id="3bf9d-432">Hantera inställningar för användargränssnittet i Microsoft Defender för Slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3bf9d-433">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-433">Section</span></span>|<span data-ttu-id="3bf9d-434">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-435">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-436">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-436">**Key**</span></span> | <span data-ttu-id="3bf9d-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="3bf9d-437">userInterface</span></span> |
| <span data-ttu-id="3bf9d-438">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-438">**Data type**</span></span> | <span data-ttu-id="3bf9d-439">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-440">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-440">**Comments**</span></span> | <span data-ttu-id="3bf9d-441">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="3bf9d-442">Visa/dölj statusmenyikon</span><span class="sxs-lookup"><span data-stu-id="3bf9d-442">Show / hide status menu icon</span></span>

<span data-ttu-id="3bf9d-443">Ange om du vill visa eller dölja statusmenyikonen i det övre högra hörnet av skärmen.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="3bf9d-444">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-444">Section</span></span>|<span data-ttu-id="3bf9d-445">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-446">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-447">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-447">**Key**</span></span> | <span data-ttu-id="3bf9d-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="3bf9d-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="3bf9d-449">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-449">**Data type**</span></span> | <span data-ttu-id="3bf9d-450">Boolesk</span><span class="sxs-lookup"><span data-stu-id="3bf9d-450">Boolean</span></span> |
| <span data-ttu-id="3bf9d-451">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-451">**Possible values**</span></span> | <span data-ttu-id="3bf9d-452">false (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-452">false (default)</span></span> <br/> <span data-ttu-id="3bf9d-453">true</span><span class="sxs-lookup"><span data-stu-id="3bf9d-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="3bf9d-454">Visa/dölj alternativ för att skicka feedback</span><span class="sxs-lookup"><span data-stu-id="3bf9d-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="3bf9d-455">Ange om användare kan skicka feedback till Microsoft genom att gå till `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="3bf9d-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="3bf9d-456">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-456">Section</span></span>|<span data-ttu-id="3bf9d-457">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-458">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-459">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-459">**Key**</span></span> | <span data-ttu-id="3bf9d-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="3bf9d-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="3bf9d-461">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-461">**Data type**</span></span> | <span data-ttu-id="3bf9d-462">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-462">String</span></span> |
| <span data-ttu-id="3bf9d-463">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-463">**Possible values**</span></span> | <span data-ttu-id="3bf9d-464">aktiverad (standard)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-464">enabled (default)</span></span> <br/> <span data-ttu-id="3bf9d-465">inaktiverad</span><span class="sxs-lookup"><span data-stu-id="3bf9d-465">disabled</span></span> |
| <span data-ttu-id="3bf9d-466">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-466">**Comments**</span></span> | <span data-ttu-id="3bf9d-467">Tillgängligt i Microsoft Defender för slutpunkt version 101.19.61 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="3bf9d-468">Inställningar för identifiering av slutpunkter och svar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="3bf9d-469">Hantera inställningarna för slutpunktsidentifierings- och svarskomponenten (EDR) i Microsoft Defender för slutpunkten i macOS.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="3bf9d-470">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-470">Section</span></span>|<span data-ttu-id="3bf9d-471">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-472">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-473">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-473">**Key**</span></span> | <span data-ttu-id="3bf9d-474">edr</span><span class="sxs-lookup"><span data-stu-id="3bf9d-474">edr</span></span> |
| <span data-ttu-id="3bf9d-475">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-475">**Data type**</span></span> | <span data-ttu-id="3bf9d-476">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-477">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-477">**Comments**</span></span> | <span data-ttu-id="3bf9d-478">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="3bf9d-479">Enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-479">Device tags</span></span>

<span data-ttu-id="3bf9d-480">Ange ett taggnamn och dess värde.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="3bf9d-481">GROUP-taggen taggar enheten med det angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="3bf9d-482">Taggen återspeglas i portalen under enhetssidan och kan användas för filtrering och gruppering av enheter.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="3bf9d-483">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-483">Section</span></span>|<span data-ttu-id="3bf9d-484">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-485">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-486">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-486">**Key**</span></span> | <span data-ttu-id="3bf9d-487">taggar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-487">tags</span></span> |
| <span data-ttu-id="3bf9d-488">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-488">**Data type**</span></span> | <span data-ttu-id="3bf9d-489">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="3bf9d-490">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-490">**Comments**</span></span> | <span data-ttu-id="3bf9d-491">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="3bf9d-492">Typ av tagg</span><span class="sxs-lookup"><span data-stu-id="3bf9d-492">Type of tag</span></span>

<span data-ttu-id="3bf9d-493">Anger typ av tagg</span><span class="sxs-lookup"><span data-stu-id="3bf9d-493">Specifies the type of tag</span></span>

|<span data-ttu-id="3bf9d-494">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-494">Section</span></span>|<span data-ttu-id="3bf9d-495">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-496">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-497">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-497">**Key**</span></span> | <span data-ttu-id="3bf9d-498">tangent</span><span class="sxs-lookup"><span data-stu-id="3bf9d-498">key</span></span> |
| <span data-ttu-id="3bf9d-499">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-499">**Data type**</span></span> | <span data-ttu-id="3bf9d-500">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-500">String</span></span> |
| <span data-ttu-id="3bf9d-501">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="3bf9d-502">Värdet på taggen</span><span class="sxs-lookup"><span data-stu-id="3bf9d-502">Value of tag</span></span>

<span data-ttu-id="3bf9d-503">Anger värdet för taggen</span><span class="sxs-lookup"><span data-stu-id="3bf9d-503">Specifies the value of tag</span></span>

|<span data-ttu-id="3bf9d-504">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="3bf9d-504">Section</span></span>|<span data-ttu-id="3bf9d-505">Värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="3bf9d-506">**Domän**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="3bf9d-507">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-507">**Key**</span></span> | <span data-ttu-id="3bf9d-508">värde</span><span class="sxs-lookup"><span data-stu-id="3bf9d-508">value</span></span> |
| <span data-ttu-id="3bf9d-509">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-509">**Data type**</span></span> | <span data-ttu-id="3bf9d-510">Sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-510">String</span></span> |
| <span data-ttu-id="3bf9d-511">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-511">**Possible values**</span></span> | <span data-ttu-id="3bf9d-512">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="3bf9d-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="3bf9d-513">Du kan bara ange ett värde per taggtyp.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="3bf9d-514">Typ av taggar är unika och bör inte upprepas i samma konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="3bf9d-515">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-515">Recommended configuration profile</span></span>

<span data-ttu-id="3bf9d-516">För att komma igång rekommenderar vi följande konfiguration för ditt företag för att dra nytta av alla skyddsfunktioner som Microsoft Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="3bf9d-517">Följande konfigurationsprofil (eller, vid JAMF, en egenskapslista som kan laddas upp till profilen för anpassade inställningar) kommer att:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="3bf9d-518">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="3bf9d-519">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="3bf9d-520">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="3bf9d-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="3bf9d-521">**Arkiveringsskyddet** (en fil med hög komprimeringshastighet) granskas i Microsoft Defender för Slutpunktsloggar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="3bf9d-522">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="3bf9d-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="3bf9d-523">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="3bf9d-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="3bf9d-524">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="3bf9d-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="3bf9d-525">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="3bf9d-526">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="3bf9d-527">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-527">Full configuration profile example</span></span>

<span data-ttu-id="3bf9d-528">Följande mallar innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över Microsoft Defender för slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="3bf9d-529">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="3bf9d-530">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="3bf9d-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="3bf9d-531">Egenskapslistverifiering</span><span class="sxs-lookup"><span data-stu-id="3bf9d-531">Property list validation</span></span>

<span data-ttu-id="3bf9d-532">Egenskapslistan måste vara en giltig *.plist-fil.*</span><span class="sxs-lookup"><span data-stu-id="3bf9d-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="3bf9d-533">Det här kan kontrolleras genom att köra:</span><span class="sxs-lookup"><span data-stu-id="3bf9d-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="3bf9d-534">Om filen är rätt utformad returnerar kommandot ovan en utgångskod `OK` för `0` .</span><span class="sxs-lookup"><span data-stu-id="3bf9d-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="3bf9d-535">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="3bf9d-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="3bf9d-536">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="3bf9d-536">Configuration profile deployment</span></span>

<span data-ttu-id="3bf9d-537">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via hanteringskonsolen som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="3bf9d-538">I följande avsnitt finns instruktioner om hur du distribuerar den här profilen med HJÄLP av JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="3bf9d-539">JAMF-distribution</span><span class="sxs-lookup"><span data-stu-id="3bf9d-539">JAMF deployment</span></span>

<span data-ttu-id="3bf9d-540">Från JAMF-konsolen öppnar du Datorkonfigurationsprofiler , navigerar till den konfigurationsprofil du vill  >  använda och väljer sedan **Anpassade inställningar.**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="3bf9d-541">Skapa en post med `com.microsoft.wdav` som inställningsdomän och ladda upp den *.plist som produceras* tidigare.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="3bf9d-542">Du måste ange rätt inställningsdomän ( ). Annars kan inte inställningarna identifieras av `com.microsoft.wdav` Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="3bf9d-543">Intune-distribution</span><span class="sxs-lookup"><span data-stu-id="3bf9d-543">Intune deployment</span></span>

1. <span data-ttu-id="3bf9d-544">Öppna **Hantera**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="3bf9d-545">Välj **Hantera**  >  **profiler**  >  **skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="3bf9d-546">Välj ett namn för profilen.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-546">Choose a name for the profile.</span></span> <span data-ttu-id="3bf9d-547">Ändra **Platform=macOS** till **Profiltyp=Anpassad**.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="3bf9d-548">Välj Konfigurera.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-548">Select Configure.</span></span>

3. <span data-ttu-id="3bf9d-549">Spara den .plist som produceras tidigare som `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="3bf9d-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="3bf9d-550">Ange `com.microsoft.wdav` namnet på den anpassade **konfigurationsprofilen.**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="3bf9d-551">Öppna konfigurationsprofilen och ladda upp `com.microsoft.wdav.xml` filen.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="3bf9d-552">(Den här filen skapades i steg 3.)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="3bf9d-553">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-553">Select **OK**.</span></span>

7. <span data-ttu-id="3bf9d-554">Välj   >  **Hantera uppgifter.**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="3bf9d-555">På fliken **Inkludera** väljer du **Tilldela till alla användare & alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="3bf9d-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="3bf9d-556">Du måste ange rätt namn på den anpassade konfigurationsprofilen. Annars identifieras inte de här inställningarna av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3bf9d-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="3bf9d-557">Resurser</span><span class="sxs-lookup"><span data-stu-id="3bf9d-557">Resources</span></span>

- [<span data-ttu-id="3bf9d-558">Referens för konfigurationsprofil (Utvecklardokumentation för Apple)</span><span class="sxs-lookup"><span data-stu-id="3bf9d-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
