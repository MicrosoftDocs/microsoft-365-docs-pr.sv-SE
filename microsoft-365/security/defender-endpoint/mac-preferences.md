---
title: Ange inställningar för Microsoft Defender ATP för Mac
description: Konfigurera Microsoft Defender ATP för Mac i företagsorganisationer.
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076930"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="71a84-104">Ange inställningar för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="71a84-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71a84-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="71a84-105">**Applies to:**</span></span>

- [<span data-ttu-id="71a84-106">Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="71a84-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="71a84-107">Den här artikeln innehåller instruktioner för hur du anger inställningar för Microsoft Defender för Slutpunkt för Mac i företagsorganisationer.</span><span class="sxs-lookup"><span data-stu-id="71a84-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="71a84-108">Information om hur du konfigurerar Microsoft Defender för Slutpunkt för Mac med kommandoradsgränssnittet finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="71a84-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="71a84-109">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="71a84-109">Summary</span></span>

<span data-ttu-id="71a84-110">I företagsorganisationer kan Microsoft Defender för Endpoint för Mac hanteras via en konfigurationsprofil som distribueras med ett av flera hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="71a84-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="71a84-111">De inställningar som hanteras av ditt säkerhetsteam har företräde framför inställningar som anges lokalt på enheten.</span><span class="sxs-lookup"><span data-stu-id="71a84-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="71a84-112">Om du vill ändra inställningar som ställts in via konfigurationsprofilen krävs eskalerade behörigheter och är inte tillgängligt för användare utan administrativ behörighet.</span><span class="sxs-lookup"><span data-stu-id="71a84-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="71a84-113">I den här artikeln beskrivs konfigurationsprofilens struktur, en rekommenderad profil som du kan använda för att komma igång och instruktioner om hur du distribuerar profilen.</span><span class="sxs-lookup"><span data-stu-id="71a84-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="71a84-114">Konfigurationsprofilstruktur</span><span class="sxs-lookup"><span data-stu-id="71a84-114">Configuration profile structure</span></span>

<span data-ttu-id="71a84-115">Konfigurationsprofilen är en *PLIST-fil* som består av poster som identifieras med en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är.</span><span class="sxs-lookup"><span data-stu-id="71a84-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="71a84-116">Värdena kan antingen vara enkla (till exempel ett numeriskt värde) eller komplexa, till exempel en kapslad lista med inställningar.</span><span class="sxs-lookup"><span data-stu-id="71a84-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="71a84-117">Konfigurationsprofilens layout beror på vilken hanteringskonsol du använder.</span><span class="sxs-lookup"><span data-stu-id="71a84-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="71a84-118">Följande avsnitt innehåller exempel på konfigurationsprofiler för JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="71a84-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="71a84-119">Den översta nivån i konfigurationsprofilen innehåller produktomfattande inställningar och poster för underavsnitt av Microsoft Defender för slutpunkt, som förklaras mer ingående i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="71a84-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="71a84-120">Inställningar för antivirusmotor</span><span class="sxs-lookup"><span data-stu-id="71a84-120">Antivirus engine preferences</span></span>

<span data-ttu-id="71a84-121">Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="71a84-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-122">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-123">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-123">**Key**</span></span> | <span data-ttu-id="71a84-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="71a84-124">antivirusEngine</span></span> |
| <span data-ttu-id="71a84-125">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-125">**Data type**</span></span> | <span data-ttu-id="71a84-126">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-127">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-127">**Comments**</span></span> | <span data-ttu-id="71a84-128">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="71a84-129">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="71a84-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="71a84-130">Ange om du vill aktivera realtidsskydd som genomsöker filer när de används.</span><span class="sxs-lookup"><span data-stu-id="71a84-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-131">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-132">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-132">**Key**</span></span> | <span data-ttu-id="71a84-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="71a84-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="71a84-134">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-134">**Data type**</span></span> | <span data-ttu-id="71a84-135">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-135">Boolean</span></span> |
| <span data-ttu-id="71a84-136">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-136">**Possible values**</span></span> | <span data-ttu-id="71a84-137">true (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-137">true (default)</span></span> <br/> <span data-ttu-id="71a84-138">false</span><span class="sxs-lookup"><span data-stu-id="71a84-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="71a84-139">Aktivera/inaktivera passivt läge</span><span class="sxs-lookup"><span data-stu-id="71a84-139">Enable / disable passive mode</span></span>

<span data-ttu-id="71a84-140">Ange om antivirusmotorn körs i passiv form.</span><span class="sxs-lookup"><span data-stu-id="71a84-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="71a84-141">Passivt läge har följande konsekvenser:</span><span class="sxs-lookup"><span data-stu-id="71a84-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="71a84-142">Realtidsskydd är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="71a84-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="71a84-143">Skanning på begäran är aktiverat</span><span class="sxs-lookup"><span data-stu-id="71a84-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="71a84-144">Automatisk åtgärd för hot är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="71a84-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="71a84-145">Säkerhetsintelligensuppdateringar är aktiverat</span><span class="sxs-lookup"><span data-stu-id="71a84-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="71a84-146">Statusmenyikonen är dold</span><span class="sxs-lookup"><span data-stu-id="71a84-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-147">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-148">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-148">**Key**</span></span> | <span data-ttu-id="71a84-149">passivläge</span><span class="sxs-lookup"><span data-stu-id="71a84-149">passiveMode</span></span> |
| <span data-ttu-id="71a84-150">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-150">**Data type**</span></span> | <span data-ttu-id="71a84-151">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-151">Boolean</span></span> |
| <span data-ttu-id="71a84-152">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-152">**Possible values**</span></span> | <span data-ttu-id="71a84-153">false (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-153">false (default)</span></span> <br/> <span data-ttu-id="71a84-154">true</span><span class="sxs-lookup"><span data-stu-id="71a84-154">true</span></span> |
| <span data-ttu-id="71a84-155">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-155">**Comments**</span></span> | <span data-ttu-id="71a84-156">Tillgängligt i Microsoft Defender för slutpunkt version 100.67.60 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="71a84-157">Princip för undantagskoppling</span><span class="sxs-lookup"><span data-stu-id="71a84-157">Exclusion merge policy</span></span>

<span data-ttu-id="71a84-158">Ange kopplingsprincipen för undantag.</span><span class="sxs-lookup"><span data-stu-id="71a84-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="71a84-159">Det här kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="71a84-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="71a84-160">Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.</span><span class="sxs-lookup"><span data-stu-id="71a84-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-161">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-162">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-162">**Key**</span></span> | <span data-ttu-id="71a84-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="71a84-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="71a84-164">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-164">**Data type**</span></span> | <span data-ttu-id="71a84-165">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-165">String</span></span> |
| <span data-ttu-id="71a84-166">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-166">**Possible values**</span></span> | <span data-ttu-id="71a84-167">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-167">merge (default)</span></span> <br/> <span data-ttu-id="71a84-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="71a84-168">admin_only</span></span> |
| <span data-ttu-id="71a84-169">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-169">**Comments**</span></span> | <span data-ttu-id="71a84-170">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="71a84-171">Undantag för skanning</span><span class="sxs-lookup"><span data-stu-id="71a84-171">Scan exclusions</span></span>

<span data-ttu-id="71a84-172">Ange enheter som inte ska genomsökas.</span><span class="sxs-lookup"><span data-stu-id="71a84-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="71a84-173">Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.</span><span class="sxs-lookup"><span data-stu-id="71a84-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-174">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-175">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-175">**Key**</span></span> | <span data-ttu-id="71a84-176">undantag</span><span class="sxs-lookup"><span data-stu-id="71a84-176">exclusions</span></span> |
| <span data-ttu-id="71a84-177">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-177">**Data type**</span></span> | <span data-ttu-id="71a84-178">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-179">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-179">**Comments**</span></span> | <span data-ttu-id="71a84-180">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="71a84-181">Typ av undantag</span><span class="sxs-lookup"><span data-stu-id="71a84-181">Type of exclusion</span></span>

<span data-ttu-id="71a84-182">Ange innehåll som ska undantas från att genomsökas efter typ.</span><span class="sxs-lookup"><span data-stu-id="71a84-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-183">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-184">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-184">**Key**</span></span> | <span data-ttu-id="71a84-185">$type</span><span class="sxs-lookup"><span data-stu-id="71a84-185">$type</span></span> |
| <span data-ttu-id="71a84-186">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-186">**Data type**</span></span> | <span data-ttu-id="71a84-187">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-187">String</span></span> |
| <span data-ttu-id="71a84-188">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-188">**Possible values**</span></span> | <span data-ttu-id="71a84-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="71a84-189">excludedPath</span></span> <br/> <span data-ttu-id="71a84-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="71a84-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="71a84-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="71a84-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="71a84-192">Sökväg till utelämnat innehåll</span><span class="sxs-lookup"><span data-stu-id="71a84-192">Path to excluded content</span></span>

<span data-ttu-id="71a84-193">Ange innehåll som inte ska genomsökas efter fullständig sökväg.</span><span class="sxs-lookup"><span data-stu-id="71a84-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-194">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-195">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-195">**Key**</span></span> | <span data-ttu-id="71a84-196">sökväg</span><span class="sxs-lookup"><span data-stu-id="71a84-196">path</span></span> |
| <span data-ttu-id="71a84-197">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-197">**Data type**</span></span> | <span data-ttu-id="71a84-198">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-198">String</span></span> |
| <span data-ttu-id="71a84-199">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-199">**Possible values**</span></span> | <span data-ttu-id="71a84-200">giltiga sökvägar</span><span class="sxs-lookup"><span data-stu-id="71a84-200">valid paths</span></span> |
| <span data-ttu-id="71a84-201">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-201">**Comments**</span></span> | <span data-ttu-id="71a84-202">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="71a84-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="71a84-203">Sökvägstyp (fil/katalog)</span><span class="sxs-lookup"><span data-stu-id="71a84-203">Path type (file / directory)</span></span>

<span data-ttu-id="71a84-204">Ange om *sökvägsegenskapen* refererar till en fil eller katalog.</span><span class="sxs-lookup"><span data-stu-id="71a84-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="71a84-205">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-206">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-206">**Key**</span></span> | <span data-ttu-id="71a84-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="71a84-207">isDirectory</span></span> |
| <span data-ttu-id="71a84-208">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-208">**Data type**</span></span> | <span data-ttu-id="71a84-209">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-209">Boolean</span></span> |
| <span data-ttu-id="71a84-210">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-210">**Possible values**</span></span> | <span data-ttu-id="71a84-211">false (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-211">false (default)</span></span> <br/> <span data-ttu-id="71a84-212">true</span><span class="sxs-lookup"><span data-stu-id="71a84-212">true</span></span> |
| <span data-ttu-id="71a84-213">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-213">**Comments**</span></span> | <span data-ttu-id="71a84-214">Gäller endast om *$type* *är undantagenPath*</span><span class="sxs-lookup"><span data-stu-id="71a84-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="71a84-215">Filnamnstillägget är undantaget från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="71a84-215">File extension excluded from the scan</span></span>

<span data-ttu-id="71a84-216">Ange innehåll som ska undantas från att genomsökas efter filtillägg.</span><span class="sxs-lookup"><span data-stu-id="71a84-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-217">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-218">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-218">**Key**</span></span> | <span data-ttu-id="71a84-219">tillägg</span><span class="sxs-lookup"><span data-stu-id="71a84-219">extension</span></span> |
| <span data-ttu-id="71a84-220">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-220">**Data type**</span></span> | <span data-ttu-id="71a84-221">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-221">String</span></span> |
| <span data-ttu-id="71a84-222">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-222">**Possible values**</span></span> | <span data-ttu-id="71a84-223">giltiga filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="71a84-223">valid file extensions</span></span> |
| <span data-ttu-id="71a84-224">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-224">**Comments**</span></span> | <span data-ttu-id="71a84-225">Gäller endast om *$type* *är undantagenFileExtension*</span><span class="sxs-lookup"><span data-stu-id="71a84-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="71a84-226">Process som uteslutits från genomsökningen</span><span class="sxs-lookup"><span data-stu-id="71a84-226">Process excluded from the scan</span></span>

<span data-ttu-id="71a84-227">Ange en process där all filaktivitet är undantagen från genomsökning.</span><span class="sxs-lookup"><span data-stu-id="71a84-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="71a84-228">Processen kan antingen anges med sitt namn (t.ex. `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="71a84-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-229">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-230">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-230">**Key**</span></span> | <span data-ttu-id="71a84-231">Namn</span><span class="sxs-lookup"><span data-stu-id="71a84-231">name</span></span> |
| <span data-ttu-id="71a84-232">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-232">**Data type**</span></span> | <span data-ttu-id="71a84-233">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-233">String</span></span> |
| <span data-ttu-id="71a84-234">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-234">**Possible values**</span></span> | <span data-ttu-id="71a84-235">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-235">any string</span></span> |
| <span data-ttu-id="71a84-236">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-236">**Comments**</span></span> | <span data-ttu-id="71a84-237">Gäller endast om *$type* *är undantagenFilnamn*</span><span class="sxs-lookup"><span data-stu-id="71a84-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="71a84-238">Tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="71a84-238">Allowed threats</span></span>

<span data-ttu-id="71a84-239">Ange hot med namn som inte blockeras av Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="71a84-240">Dessa hot kommer att tillåtas att köras.</span><span class="sxs-lookup"><span data-stu-id="71a84-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-241">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-242">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-242">**Key**</span></span> | <span data-ttu-id="71a84-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="71a84-243">allowedThreats</span></span> |
| <span data-ttu-id="71a84-244">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-244">**Data type**</span></span> | <span data-ttu-id="71a84-245">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="71a84-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="71a84-246">Otillåtna hotåtgärder</span><span class="sxs-lookup"><span data-stu-id="71a84-246">Disallowed threat actions</span></span>

<span data-ttu-id="71a84-247">Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks.</span><span class="sxs-lookup"><span data-stu-id="71a84-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="71a84-248">De åtgärder som ingår i den här listan visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="71a84-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-249">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-250">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-250">**Key**</span></span> | <span data-ttu-id="71a84-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="71a84-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="71a84-252">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-252">**Data type**</span></span> | <span data-ttu-id="71a84-253">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="71a84-253">Array of strings</span></span> |
| <span data-ttu-id="71a84-254">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-254">**Possible values**</span></span> | <span data-ttu-id="71a84-255">tillåt (begränsar användare från att tillåta hot)</span><span class="sxs-lookup"><span data-stu-id="71a84-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="71a84-256">återställning (hindrar användare från att återställa hot från karantän)</span><span class="sxs-lookup"><span data-stu-id="71a84-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="71a84-257">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-257">**Comments**</span></span> | <span data-ttu-id="71a84-258">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="71a84-259">Inställningar för hottyp</span><span class="sxs-lookup"><span data-stu-id="71a84-259">Threat type settings</span></span>

<span data-ttu-id="71a84-260">Ange hur vissa hottyper hanteras av Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-261">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-262">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-262">**Key**</span></span> | <span data-ttu-id="71a84-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="71a84-263">threatTypeSettings</span></span> |
| <span data-ttu-id="71a84-264">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-264">**Data type**</span></span> | <span data-ttu-id="71a84-265">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-266">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-266">**Comments**</span></span> | <span data-ttu-id="71a84-267">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="71a84-268">Hottyp</span><span class="sxs-lookup"><span data-stu-id="71a84-268">Threat type</span></span>

<span data-ttu-id="71a84-269">Ange hottyper.</span><span class="sxs-lookup"><span data-stu-id="71a84-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-270">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-271">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-271">**Key**</span></span> | <span data-ttu-id="71a84-272">tangent</span><span class="sxs-lookup"><span data-stu-id="71a84-272">key</span></span> |
| <span data-ttu-id="71a84-273">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-273">**Data type**</span></span> | <span data-ttu-id="71a84-274">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-274">String</span></span> |
| <span data-ttu-id="71a84-275">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-275">**Possible values**</span></span> | <span data-ttu-id="71a84-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="71a84-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="71a84-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="71a84-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="71a84-278">Åtgärd att vidta</span><span class="sxs-lookup"><span data-stu-id="71a84-278">Action to take</span></span>

<span data-ttu-id="71a84-279">Ange vilken åtgärd som ska vidtas när ett hot av den typ som anges i föregående avsnitt identifieras.</span><span class="sxs-lookup"><span data-stu-id="71a84-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="71a84-280">Välj bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="71a84-280">Choose from the following options:</span></span>

- <span data-ttu-id="71a84-281">**Granskning:** din enhet är inte skyddad mot den här typen av hot, men en post om hot loggas.</span><span class="sxs-lookup"><span data-stu-id="71a84-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="71a84-282">**Blockering:** din enhet är skyddad mot den här typen av hot och du meddelas i användargränssnittet och säkerhetskonsolen.</span><span class="sxs-lookup"><span data-stu-id="71a84-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="71a84-283">**Av:** din enhet är inte skyddad mot den här typen av hot och inget loggas.</span><span class="sxs-lookup"><span data-stu-id="71a84-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-284">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-285">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-285">**Key**</span></span> | <span data-ttu-id="71a84-286">värde</span><span class="sxs-lookup"><span data-stu-id="71a84-286">value</span></span> |
| <span data-ttu-id="71a84-287">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-287">**Data type**</span></span> | <span data-ttu-id="71a84-288">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-288">String</span></span> |
| <span data-ttu-id="71a84-289">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-289">**Possible values**</span></span> | <span data-ttu-id="71a84-290">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-290">audit (default)</span></span> <br/> <span data-ttu-id="71a84-291">blockera</span><span class="sxs-lookup"><span data-stu-id="71a84-291">block</span></span> <br/> <span data-ttu-id="71a84-292">av</span><span class="sxs-lookup"><span data-stu-id="71a84-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="71a84-293">Princip för sammanfogning av hottyper</span><span class="sxs-lookup"><span data-stu-id="71a84-293">Threat type settings merge policy</span></span>

<span data-ttu-id="71a84-294">Ange kopplingsprincipen för inställningar av hottyper.</span><span class="sxs-lookup"><span data-stu-id="71a84-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="71a84-295">Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="71a84-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="71a84-296">Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.</span><span class="sxs-lookup"><span data-stu-id="71a84-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-297">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-298">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-298">**Key**</span></span> | <span data-ttu-id="71a84-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="71a84-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="71a84-300">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-300">**Data type**</span></span> | <span data-ttu-id="71a84-301">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-301">String</span></span> |
| <span data-ttu-id="71a84-302">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-302">**Possible values**</span></span> | <span data-ttu-id="71a84-303">koppla (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-303">merge (default)</span></span> <br/> <span data-ttu-id="71a84-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="71a84-304">admin_only</span></span> |
| <span data-ttu-id="71a84-305">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-305">**Comments**</span></span> | <span data-ttu-id="71a84-306">Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="71a84-307">Historik för antivirussökningshistorik kvar (i dagar)</span><span class="sxs-lookup"><span data-stu-id="71a84-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="71a84-308">Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten.</span><span class="sxs-lookup"><span data-stu-id="71a84-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="71a84-309">Gamla genomsökningsresultat tas bort från historiken.</span><span class="sxs-lookup"><span data-stu-id="71a84-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="71a84-310">Gamla filer i karantän som också har tagits bort från disken.</span><span class="sxs-lookup"><span data-stu-id="71a84-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-311">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-312">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-312">**Key**</span></span> | <span data-ttu-id="71a84-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="71a84-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="71a84-314">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-314">**Data type**</span></span> | <span data-ttu-id="71a84-315">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-315">String</span></span> |
| <span data-ttu-id="71a84-316">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-316">**Possible values**</span></span> | <span data-ttu-id="71a84-317">90 (standard).</span><span class="sxs-lookup"><span data-stu-id="71a84-317">90 (default).</span></span> <span data-ttu-id="71a84-318">Tillåtna värden är 1 dag till 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="71a84-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="71a84-319">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-319">**Comments**</span></span> | <span data-ttu-id="71a84-320">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="71a84-321">Maximalt antal objekt i historiken för antivirussökning</span><span class="sxs-lookup"><span data-stu-id="71a84-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="71a84-322">Ange det maximala antalet poster som ska behållas i genomsökningshistoriken.</span><span class="sxs-lookup"><span data-stu-id="71a84-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="71a84-323">Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.</span><span class="sxs-lookup"><span data-stu-id="71a84-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-324">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-325">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-325">**Key**</span></span> | <span data-ttu-id="71a84-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="71a84-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="71a84-327">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-327">**Data type**</span></span> | <span data-ttu-id="71a84-328">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-328">String</span></span> |
| <span data-ttu-id="71a84-329">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-329">**Possible values**</span></span> | <span data-ttu-id="71a84-330">10000 (standard).</span><span class="sxs-lookup"><span data-stu-id="71a84-330">10000 (default).</span></span> <span data-ttu-id="71a84-331">Tillåtna värden är från 5 000 objekt till 1 5 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="71a84-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="71a84-332">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-332">**Comments**</span></span> | <span data-ttu-id="71a84-333">Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="71a84-334">Inställningar för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="71a84-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="71a84-335">Konfigurera de molnbaserade skyddsfunktionerna i Microsoft Defender för Endpoint för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-336">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-337">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-337">**Key**</span></span> | <span data-ttu-id="71a84-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="71a84-338">cloudService</span></span> |
| <span data-ttu-id="71a84-339">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-339">**Data type**</span></span> | <span data-ttu-id="71a84-340">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-341">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-341">**Comments**</span></span> | <span data-ttu-id="71a84-342">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="71a84-343">Aktivera/inaktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="71a84-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="71a84-344">Ange om du vill aktivera moln levererat skydd på enheten eller inte.</span><span class="sxs-lookup"><span data-stu-id="71a84-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="71a84-345">Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="71a84-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-346">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-347">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-347">**Key**</span></span> | <span data-ttu-id="71a84-348">aktiverat</span><span class="sxs-lookup"><span data-stu-id="71a84-348">enabled</span></span> |
| <span data-ttu-id="71a84-349">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-349">**Data type**</span></span> | <span data-ttu-id="71a84-350">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-350">Boolean</span></span> |
| <span data-ttu-id="71a84-351">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-351">**Possible values**</span></span> | <span data-ttu-id="71a84-352">true (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-352">true (default)</span></span> <br/> <span data-ttu-id="71a84-353">false</span><span class="sxs-lookup"><span data-stu-id="71a84-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="71a84-354">Diagnostiksamlingsnivå</span><span class="sxs-lookup"><span data-stu-id="71a84-354">Diagnostic collection level</span></span>

<span data-ttu-id="71a84-355">Diagnostikdata används för att hålla Microsoft Defender för Endpoint säkert och uppdaterat, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar.</span><span class="sxs-lookup"><span data-stu-id="71a84-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="71a84-356">Den här inställningen bestämmer nivån för diagnostik som skickas av Microsoft Defender för Slutpunkt till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71a84-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-357">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-358">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-358">**Key**</span></span> | <span data-ttu-id="71a84-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="71a84-359">diagnosticLevel</span></span> |
| <span data-ttu-id="71a84-360">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-360">**Data type**</span></span> | <span data-ttu-id="71a84-361">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-361">String</span></span> |
| <span data-ttu-id="71a84-362">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-362">**Possible values**</span></span> | <span data-ttu-id="71a84-363">valfritt (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-363">optional (default)</span></span> <br/> <span data-ttu-id="71a84-364">obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="71a84-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="71a84-365">Aktivera/inaktivera automatiska exempelinskick</span><span class="sxs-lookup"><span data-stu-id="71a84-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="71a84-366">Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71a84-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="71a84-367">Du uppmanas att ange om den inskickade filen troligen innehåller personlig information.</span><span class="sxs-lookup"><span data-stu-id="71a84-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-368">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-369">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-369">**Key**</span></span> | <span data-ttu-id="71a84-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="71a84-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="71a84-371">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-371">**Data type**</span></span> | <span data-ttu-id="71a84-372">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-372">Boolean</span></span> |
| <span data-ttu-id="71a84-373">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-373">**Possible values**</span></span> | <span data-ttu-id="71a84-374">true (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-374">true (default)</span></span> <br/> <span data-ttu-id="71a84-375">false</span><span class="sxs-lookup"><span data-stu-id="71a84-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="71a84-376">Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="71a84-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="71a84-377">Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:</span><span class="sxs-lookup"><span data-stu-id="71a84-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-378">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-378">**Key**</span></span> | <span data-ttu-id="71a84-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="71a84-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="71a84-380">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-380">**Data type**</span></span> | <span data-ttu-id="71a84-381">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-381">Boolean</span></span> |
| <span data-ttu-id="71a84-382">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-382">**Possible values**</span></span> | <span data-ttu-id="71a84-383">true (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-383">true (default)</span></span> <br/> <span data-ttu-id="71a84-384">false</span><span class="sxs-lookup"><span data-stu-id="71a84-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="71a84-385">Inställningar för användargränssnitt</span><span class="sxs-lookup"><span data-stu-id="71a84-385">User interface preferences</span></span>

<span data-ttu-id="71a84-386">Hantera inställningar för användargränssnittet i Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-387">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-388">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-388">**Key**</span></span> | <span data-ttu-id="71a84-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="71a84-389">userInterface</span></span> |
| <span data-ttu-id="71a84-390">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-390">**Data type**</span></span> | <span data-ttu-id="71a84-391">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-392">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-392">**Comments**</span></span> | <span data-ttu-id="71a84-393">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="71a84-394">Visa/dölj statusmenyikon</span><span class="sxs-lookup"><span data-stu-id="71a84-394">Show / hide status menu icon</span></span>

<span data-ttu-id="71a84-395">Ange om du vill visa eller dölja statusmenyikonen i det övre högra hörnet av skärmen.</span><span class="sxs-lookup"><span data-stu-id="71a84-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-396">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-397">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-397">**Key**</span></span> | <span data-ttu-id="71a84-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="71a84-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="71a84-399">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-399">**Data type**</span></span> | <span data-ttu-id="71a84-400">Boolesk</span><span class="sxs-lookup"><span data-stu-id="71a84-400">Boolean</span></span> |
| <span data-ttu-id="71a84-401">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-401">**Possible values**</span></span> | <span data-ttu-id="71a84-402">false (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-402">false (default)</span></span> <br/> <span data-ttu-id="71a84-403">true</span><span class="sxs-lookup"><span data-stu-id="71a84-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="71a84-404">Visa/dölj alternativ för att skicka feedback</span><span class="sxs-lookup"><span data-stu-id="71a84-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="71a84-405">Ange om användare kan skicka feedback till Microsoft genom att gå till `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="71a84-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-406">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-407">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-407">**Key**</span></span> | <span data-ttu-id="71a84-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="71a84-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="71a84-409">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-409">**Data type**</span></span> | <span data-ttu-id="71a84-410">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-410">String</span></span> |
| <span data-ttu-id="71a84-411">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-411">**Possible values**</span></span> | <span data-ttu-id="71a84-412">aktiverad (standard)</span><span class="sxs-lookup"><span data-stu-id="71a84-412">enabled (default)</span></span> <br/> <span data-ttu-id="71a84-413">inaktiverad</span><span class="sxs-lookup"><span data-stu-id="71a84-413">disabled</span></span> |
| <span data-ttu-id="71a84-414">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-414">**Comments**</span></span> | <span data-ttu-id="71a84-415">Tillgängligt i Microsoft Defender för slutpunkt version 101.19.61 eller senare.</span><span class="sxs-lookup"><span data-stu-id="71a84-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="71a84-416">Inställningar för identifiering av slutpunkter och svar</span><span class="sxs-lookup"><span data-stu-id="71a84-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="71a84-417">Hantera inställningarna för slutpunktsidentifierings- och svarskomponenten (EDR) i Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-418">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-419">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-419">**Key**</span></span> | <span data-ttu-id="71a84-420">edr</span><span class="sxs-lookup"><span data-stu-id="71a84-420">edr</span></span> |
| <span data-ttu-id="71a84-421">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-421">**Data type**</span></span> | <span data-ttu-id="71a84-422">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-423">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-423">**Comments**</span></span> | <span data-ttu-id="71a84-424">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="71a84-425">Enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="71a84-425">Device tags</span></span>

<span data-ttu-id="71a84-426">Ange ett taggnamn och dess värde.</span><span class="sxs-lookup"><span data-stu-id="71a84-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="71a84-427">GROUP-taggen taggar enheten med det angivna värdet.</span><span class="sxs-lookup"><span data-stu-id="71a84-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="71a84-428">Taggen återspeglas i portalen under enhetssidan och kan användas för filtrering och gruppering av enheter.</span><span class="sxs-lookup"><span data-stu-id="71a84-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-429">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-430">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-430">**Key**</span></span> | <span data-ttu-id="71a84-431">taggar</span><span class="sxs-lookup"><span data-stu-id="71a84-431">tags</span></span> |
| <span data-ttu-id="71a84-432">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-432">**Data type**</span></span> | <span data-ttu-id="71a84-433">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="71a84-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="71a84-434">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="71a84-434">**Comments**</span></span> | <span data-ttu-id="71a84-435">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="71a84-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="71a84-436">Typ av tagg</span><span class="sxs-lookup"><span data-stu-id="71a84-436">Type of tag</span></span>

<span data-ttu-id="71a84-437">Anger typ av tagg</span><span class="sxs-lookup"><span data-stu-id="71a84-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-438">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-439">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-439">**Key**</span></span> | <span data-ttu-id="71a84-440">tangent</span><span class="sxs-lookup"><span data-stu-id="71a84-440">key</span></span> |
| <span data-ttu-id="71a84-441">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-441">**Data type**</span></span> | <span data-ttu-id="71a84-442">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-442">String</span></span> |
| <span data-ttu-id="71a84-443">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="71a84-444">Värdet på taggen</span><span class="sxs-lookup"><span data-stu-id="71a84-444">Value of tag</span></span>

<span data-ttu-id="71a84-445">Anger värdet för taggen</span><span class="sxs-lookup"><span data-stu-id="71a84-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="71a84-446">**Domain**</span><span class="sxs-lookup"><span data-stu-id="71a84-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="71a84-447">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="71a84-447">**Key**</span></span> | <span data-ttu-id="71a84-448">värde</span><span class="sxs-lookup"><span data-stu-id="71a84-448">value</span></span> |
| <span data-ttu-id="71a84-449">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="71a84-449">**Data type**</span></span> | <span data-ttu-id="71a84-450">Sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-450">String</span></span> |
| <span data-ttu-id="71a84-451">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="71a84-451">**Possible values**</span></span> | <span data-ttu-id="71a84-452">valfri sträng</span><span class="sxs-lookup"><span data-stu-id="71a84-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="71a84-453">Du kan bara ange ett värde per taggtyp.</span><span class="sxs-lookup"><span data-stu-id="71a84-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="71a84-454">Typ av taggar är unika och bör inte upprepas i samma konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="71a84-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="71a84-455">Rekommenderad konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="71a84-455">Recommended configuration profile</span></span>

<span data-ttu-id="71a84-456">För att komma igång rekommenderar vi följande konfiguration för ditt företag för att dra nytta av alla skyddsfunktioner som Microsoft Defender för Endpoint tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="71a84-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="71a84-457">Följande konfigurationsprofil (eller, vid JAMF, en egenskapslista som kan laddas upp till profilen för anpassade inställningar) kommer att:</span><span class="sxs-lookup"><span data-stu-id="71a84-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="71a84-458">Aktivera realtidsskydd (RTP)</span><span class="sxs-lookup"><span data-stu-id="71a84-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="71a84-459">Ange hur följande hottyper ska hanteras:</span><span class="sxs-lookup"><span data-stu-id="71a84-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="71a84-460">**Potentiellt oönskade program (PUA)** blockeras</span><span class="sxs-lookup"><span data-stu-id="71a84-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="71a84-461">**Arkiveringsskyddet** (en fil med hög komprimeringshastighet) granskas i Microsoft Defender för Slutpunktsloggar</span><span class="sxs-lookup"><span data-stu-id="71a84-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="71a84-462">Aktivera automatiska säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="71a84-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="71a84-463">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="71a84-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="71a84-464">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="71a84-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="71a84-465">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="71a84-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="71a84-466">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="71a84-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="71a84-467">Exempel på fullständig konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="71a84-467">Full configuration profile example</span></span>

<span data-ttu-id="71a84-468">Följande mallar innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="71a84-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="71a84-469">Egenskapslista för JAMF-konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="71a84-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="71a84-470">Intune-profil</span><span class="sxs-lookup"><span data-stu-id="71a84-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="71a84-471">Egenskapslistverifiering</span><span class="sxs-lookup"><span data-stu-id="71a84-471">Property list validation</span></span>

<span data-ttu-id="71a84-472">Egenskapslistan måste vara en giltig *.plist-fil.*</span><span class="sxs-lookup"><span data-stu-id="71a84-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="71a84-473">Det här kan kontrolleras genom att köra:</span><span class="sxs-lookup"><span data-stu-id="71a84-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="71a84-474">Om filen är rätt utformad returnerar kommandot ovan en utgångskod `OK` för `0` .</span><span class="sxs-lookup"><span data-stu-id="71a84-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="71a84-475">Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .</span><span class="sxs-lookup"><span data-stu-id="71a84-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="71a84-476">Konfigurationsprofildistribution</span><span class="sxs-lookup"><span data-stu-id="71a84-476">Configuration profile deployment</span></span>

<span data-ttu-id="71a84-477">När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via hanteringskonsolen som företaget använder.</span><span class="sxs-lookup"><span data-stu-id="71a84-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="71a84-478">I följande avsnitt finns instruktioner om hur du distribuerar den här profilen med HJÄLP av JAMF och Intune.</span><span class="sxs-lookup"><span data-stu-id="71a84-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="71a84-479">JAMF-distribution</span><span class="sxs-lookup"><span data-stu-id="71a84-479">JAMF deployment</span></span>

<span data-ttu-id="71a84-480">Från JAMF-konsolen öppnar du Datorkonfigurationsprofiler , navigerar till den konfigurationsprofil du vill  >  använda och väljer sedan **Anpassade inställningar.**</span><span class="sxs-lookup"><span data-stu-id="71a84-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="71a84-481">Skapa en post med `com.microsoft.wdav` som inställningsdomän och ladda upp den *.plist som produceras* tidigare.</span><span class="sxs-lookup"><span data-stu-id="71a84-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="71a84-482">Du måste ange rätt inställningsdomän ( ). Annars kan inte inställningarna identifieras av `com.microsoft.wdav` Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="71a84-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="71a84-483">Intune-distribution</span><span class="sxs-lookup"><span data-stu-id="71a84-483">Intune deployment</span></span>

1. <span data-ttu-id="71a84-484">Öppna **Hantera**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="71a84-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="71a84-485">Välj **Hantera**  >  **profiler**  >  **skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="71a84-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="71a84-486">Välj ett namn för profilen.</span><span class="sxs-lookup"><span data-stu-id="71a84-486">Choose a name for the profile.</span></span> <span data-ttu-id="71a84-487">Ändra **Platform=macOS** till **Profiltyp=Anpassad**.</span><span class="sxs-lookup"><span data-stu-id="71a84-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="71a84-488">Välj Konfigurera.</span><span class="sxs-lookup"><span data-stu-id="71a84-488">Select Configure.</span></span>

3. <span data-ttu-id="71a84-489">Spara den .plist som produceras tidigare som `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="71a84-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="71a84-490">Ange `com.microsoft.wdav` namnet på den anpassade **konfigurationsprofilen.**</span><span class="sxs-lookup"><span data-stu-id="71a84-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="71a84-491">Öppna konfigurationsprofilen och ladda upp `com.microsoft.wdav.xml` filen.</span><span class="sxs-lookup"><span data-stu-id="71a84-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="71a84-492">(Den här filen skapades i steg 3.)</span><span class="sxs-lookup"><span data-stu-id="71a84-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="71a84-493">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="71a84-493">Select **OK**.</span></span>

7. <span data-ttu-id="71a84-494">Välj   >  **Hantera uppgifter.**</span><span class="sxs-lookup"><span data-stu-id="71a84-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="71a84-495">På fliken **Inkludera** väljer du **Tilldela till alla användare & alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="71a84-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="71a84-496">Du måste ange rätt namn på den anpassade konfigurationsprofilen. Annars identifieras inte de här inställningarna av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="71a84-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="71a84-497">Resurser</span><span class="sxs-lookup"><span data-stu-id="71a84-497">Resources</span></span>

- [<span data-ttu-id="71a84-498">Referens för konfigurationsprofil (Utvecklardokumentation för Apple)</span><span class="sxs-lookup"><span data-stu-id="71a84-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
