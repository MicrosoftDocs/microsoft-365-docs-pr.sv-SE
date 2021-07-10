---
title: Vad är nytt i Microsoft Defender för slutpunkt på Mac
description: Läs mer om de viktigaste ändringarna för tidigare versioner av Microsoft Defender för Endpoint på Mac.
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, mac, installation, macos, nyheter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 841f22421ac81ba447dad70a68c4c7bc95605b16
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363901"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c8986-104">Vad är nytt i Microsoft Defender för slutpunkt på Mac</span><span class="sxs-lookup"><span data-stu-id="c8986-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8986-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c8986-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8986-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c8986-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8986-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8986-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c8986-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c8986-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8986-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c8986-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="c8986-110">På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="c8986-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="c8986-111">Om du är en befintlig kund som uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som listas på [den här sidan.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c8986-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013420-20121051134200"></a><span data-ttu-id="c8986-112">101.34.20 (20.121051.13420.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-112">101.34.20 (20.121051.13420.0)</span></span>

- <span data-ttu-id="c8986-113">[Enhetskontrollen för macOS](mac-device-control-overview.md) är nu i allmän tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="c8986-113">[Device control for macOS](mac-device-control-overview.md) is now in general availability</span></span>
- <span data-ttu-id="c8986-114">Åtgärdat ett problem där en snabbsökning inte kunde startas från statusmenyn i macOS 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="c8986-114">Addressed an issue where a quick scan could not be started from the status menu on macOS 11 (Big Sur)</span></span>
- <span data-ttu-id="c8986-115">Andra felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-115">Other bug fixes</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="c8986-116">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-116">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="c8986-117">Åtgärdat ett problem där samtidig åtkomst till nyckelringen från Microsoft Defender för Endpoint och andra program kan leda till skadade nyckelringar.</span><span class="sxs-lookup"><span data-stu-id="c8986-117">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="c8986-118">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-118">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="c8986-119">Från och med den här versionen kommer hot som upptäckts under sökning på begäran av antivirus som utlöses via kommandoradsklienten att åtgärdas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c8986-119">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="c8986-120">Hot som upptäckts vid genomsökningar som utlösts via användargränssnittet kräver fortfarande manuell åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c8986-120">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="c8986-121">`mdatp diagnostic real-time-protection-statistics` stöder nu ytterligare två växlar:</span><span class="sxs-lookup"><span data-stu-id="c8986-121">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="c8986-122">`--sort`: Sorterar resultatet fallande efter totalt antal genomsökta filer</span><span class="sxs-lookup"><span data-stu-id="c8986-122">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="c8986-123">`--top N`: visar de översta N-resultaten (fungerar bara om `--sort` anges också)</span><span class="sxs-lookup"><span data-stu-id="c8986-123">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="c8986-124">Prestandaförbättringar (särskilt för när IST. används) & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-124">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="c8986-125">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-125">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="c8986-126">Åtgärd för att hantera förfallotiden för Apple-certifikat för macOS Catalina och tidigare.</span><span class="sxs-lookup"><span data-stu-id="c8986-126">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="c8986-127">Den här korrigeringen återställer & funktioner för sårbarhetshantering (TVM).</span><span class="sxs-lookup"><span data-stu-id="c8986-127">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="c8986-128">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-128">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="c8986-129">Microsoft Defender för Slutpunkt på macOS är nu tillgänglig i förhandsversion för kunder inom myndigheter i USA.</span><span class="sxs-lookup"><span data-stu-id="c8986-129">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="c8986-130">Mer information finns i [Microsoft Defender för slutpunkt för kunder inom amerikanska myndigheter.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="c8986-130">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="c8986-131">Prestandaförbättringar (särskilt vid den situation då appen XCode Bugg används) som & programkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="c8986-131">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="c8986-132">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-132">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="c8986-133">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="c8986-133">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="c8986-134">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="c8986-134">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="c8986-135">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-135">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="c8986-136">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-136">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="c8986-137">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-137">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="c8986-138">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-138">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="c8986-139">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-139">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="c8986-140">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-140">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="c8986-141">Den gamla kommandoradsverktygets syntax är inaktuell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="c8986-141">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="c8986-142">Mer information om den nya syntaxen finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c8986-142">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="c8986-143">Lade till en ny kommandoradsväxel för att inaktivera nätverkstillägget: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="c8986-143">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="c8986-144">Det här kommandot kan vara användbart för att felsöka nätverksproblem som kan ha att göra med Microsoft Defender för Slutpunkt på Mac</span><span class="sxs-lookup"><span data-stu-id="c8986-144">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="c8986-145">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-145">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="c8986-146">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-146">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="c8986-147">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-147">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="c8986-148">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-148">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="c8986-149">Förbättrad tillförlitlighet för agenten när du kör på macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="c8986-149">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="c8986-150">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="c8986-150">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="c8986-151">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-151">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="c8986-152">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="c8986-152">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="c8986-153">Villkor togs bort när Microsoft Defender för Endpoint utlöste ett fel i macOS 11 (Big Sur) som visar sig i en kernel-panik</span><span class="sxs-lookup"><span data-stu-id="c8986-153">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="c8986-154">Åtgärdat en minnesläcka i Endpoint Security-systemtillägget när det kördes på mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="c8986-154">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="c8986-155">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-155">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="c8986-156">101.10.72</span><span class="sxs-lookup"><span data-stu-id="c8986-156">101.10.72</span></span>

- <span data-ttu-id="c8986-157">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-157">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="c8986-158">101.09.61</span><span class="sxs-lookup"><span data-stu-id="c8986-158">101.09.61</span></span>

- <span data-ttu-id="c8986-159">Lade till en ny hanterad inställning [för att inaktivera alternativet att skicka feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="c8986-159">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="c8986-160">Statusmenyikonen visar ett felfritt läge när produktinställningarna hanteras.</span><span class="sxs-lookup"><span data-stu-id="c8986-160">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="c8986-161">Tidigare visade statusmenyikonen ett varningsmeddelande eller felläge, även om produktinställningarna hanterades av administratören</span><span class="sxs-lookup"><span data-stu-id="c8986-161">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="c8986-162">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-162">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="c8986-163">101.09.50</span><span class="sxs-lookup"><span data-stu-id="c8986-163">101.09.50</span></span>

- <span data-ttu-id="c8986-164">Den här produktversionen har validerats på macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="c8986-164">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="c8986-165">Den nya syntaxen `mdatp` för kommandoradsverktyget är nu standard.</span><span class="sxs-lookup"><span data-stu-id="c8986-165">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="c8986-166">Mer information om den nya syntaxen finns i [Resurser för Microsoft Defender för Slutpunkt i macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="c8986-166">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8986-167">Syntaxen för det gamla kommandoradsverktyget tas bort från produkten **den 1 januari 2021.**</span><span class="sxs-lookup"><span data-stu-id="c8986-167">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="c8986-168">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="c8986-168">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="c8986-169">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-169">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="c8986-170">101.09.49</span><span class="sxs-lookup"><span data-stu-id="c8986-170">101.09.49</span></span>

- <span data-ttu-id="c8986-171">Förbättringar av användargränssnittet för att skilja på undantag som hanteras av IT-administratören och undantag som definieras av den lokala användaren</span><span class="sxs-lookup"><span data-stu-id="c8986-171">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="c8986-172">Förbättrad CPU-användning vid genomsökningar på begäran</span><span class="sxs-lookup"><span data-stu-id="c8986-172">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="c8986-173">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-173">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="c8986-174">101.07.23</span><span class="sxs-lookup"><span data-stu-id="c8986-174">101.07.23</span></span>

- <span data-ttu-id="c8986-175">Nya fält har lagts till i utdata `mdatp --health` för att kontrollera status för passivt läge och Identifiering och åtgärd på slutpunkt grupp-ID</span><span class="sxs-lookup"><span data-stu-id="c8986-175">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8986-176">`mdatp --health` ersätts med `mdatp health` i en framtida produktuppdatering.</span><span class="sxs-lookup"><span data-stu-id="c8986-176">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="c8986-177">Åtgärdat ett fel där automatisk exempelinskick inte har markerats som hanterat i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="c8986-177">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="c8986-178">Nya inställningar för att kontrollera bevarandet av objekt i historiken för antivirussökning har lagts till.</span><span class="sxs-lookup"><span data-stu-id="c8986-178">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="c8986-179">Du kan nu [ange antalet dagar för att behålla objekt i genomsökningshistoriken](mac-preferences.md#antivirus-scan-history-retention-in-days) och ange det högsta antalet objekt i [genomsökningshistoriken](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="c8986-179">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="c8986-180">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-180">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="c8986-181">101.06.63</span><span class="sxs-lookup"><span data-stu-id="c8986-181">101.06.63</span></span>

- <span data-ttu-id="c8986-182">Åtgärdat en prestanda regression som introducerades i version `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="c8986-182">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="c8986-183">Regressionen infördes med korrigeringen för att eliminera kernel-panik som en del kunder har observerat vid åtkomst till SMB-resurser.</span><span class="sxs-lookup"><span data-stu-id="c8986-183">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="c8986-184">Vi har återställt den här kodändringen och undersöker alternativa sätt att eliminera kernel-panik.</span><span class="sxs-lookup"><span data-stu-id="c8986-184">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="c8986-185">101.05.17</span><span class="sxs-lookup"><span data-stu-id="c8986-185">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8986-186">Vi arbetar med en ny och förbättrad syntax `mdatp` för kommandoradsverktyget.</span><span class="sxs-lookup"><span data-stu-id="c8986-186">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="c8986-187">Den nya syntaxen är för närvarande standard i uppdateringskanalerna Insider – snabbt och Insider – långsamt.</span><span class="sxs-lookup"><span data-stu-id="c8986-187">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="c8986-188">Vi rekommenderar att du använder den nya syntaxen för att använda den här syntaxen.</span><span class="sxs-lookup"><span data-stu-id="c8986-188">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="c8986-189">Vi fortsätter att stödja den gamla syntaxen parallellt med den nya syntaxen och kommer att ge mer kommunikation om utfasningsplanen för den gamla syntaxen under de kommande månaderna.</span><span class="sxs-lookup"><span data-stu-id="c8986-189">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="c8986-190">Åtgärdat en kernel-panik som ibland uppstod när man fick åtkomst till SMB-filresurser</span><span class="sxs-lookup"><span data-stu-id="c8986-190">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="c8986-191">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-191">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="c8986-192">101.05.16</span><span class="sxs-lookup"><span data-stu-id="c8986-192">101.05.16</span></span>

- <span data-ttu-id="c8986-193">Förbättringar av snabbsökningslogik för att avsevärt minska antalet skannade filer</span><span class="sxs-lookup"><span data-stu-id="c8986-193">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="c8986-194">Lade [till stöd för Komplettera](mac-resources.md#how-to-enable-autocompletion) automatiskt för kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="c8986-194">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="c8986-195">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-195">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="c8986-196">101.03.12</span><span class="sxs-lookup"><span data-stu-id="c8986-196">101.03.12</span></span>

- <span data-ttu-id="c8986-197">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-197">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="c8986-198">101.01.54</span><span class="sxs-lookup"><span data-stu-id="c8986-198">101.01.54</span></span>

- <span data-ttu-id="c8986-199">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="c8986-199">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c8986-200">Förbättrade hjälpmedelsfunktioner</span><span class="sxs-lookup"><span data-stu-id="c8986-200">Accessibility improvements</span></span>
- <span data-ttu-id="c8986-201">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-201">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="c8986-202">101.00.31</span><span class="sxs-lookup"><span data-stu-id="c8986-202">101.00.31</span></span>

- <span data-ttu-id="c8986-203">Förbättrad [produktinitiering för Intune-användare](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="c8986-203">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="c8986-204">Undantag [från antivirus har nu stöd för jokertecken](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="c8986-204">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="c8986-205">Lade till möjligheten att utlösa antivirusskanningar från macOS-snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="c8986-205">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="c8986-206">Nu kan du högerklicka på en fil eller en mapp i Finder och välja **Sök med Microsoft Defender för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="c8986-206">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="c8986-207">Nedgradering av produkter på plats kommer nu uttryckligen inte att tillåtas av installationsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="c8986-207">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="c8986-208">Om du behöver nedgradera måste du först avinstallera den befintliga versionen och konfigurera om enheten</span><span class="sxs-lookup"><span data-stu-id="c8986-208">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="c8986-209">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-209">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="c8986-210">100.90.27</span><span class="sxs-lookup"><span data-stu-id="c8986-210">100.90.27</span></span>

- <span data-ttu-id="c8986-211">Nu kan du [ange en uppdateringskanal](mac-updates.md#set-the-channel-name) för Microsoft Defender för Slutpunkt i macOS som skiljer sig från den systemomfattande uppdateringskanalen</span><span class="sxs-lookup"><span data-stu-id="c8986-211">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="c8986-212">Ny produktikon</span><span class="sxs-lookup"><span data-stu-id="c8986-212">New product icon</span></span>
- <span data-ttu-id="c8986-213">Andra förbättringar av användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="c8986-213">Other user experience improvements</span></span>
- <span data-ttu-id="c8986-214">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-214">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="c8986-215">100.86.92</span><span class="sxs-lookup"><span data-stu-id="c8986-215">100.86.92</span></span>

- <span data-ttu-id="c8986-216">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="c8986-216">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c8986-217">Åtgärdat ett problem där produkten ibland inte rensade alla filer under `/Library/Application Support/Microsoft/Defender` avinstallationen</span><span class="sxs-lookup"><span data-stu-id="c8986-217">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="c8986-218">Minskad CPU-användning av produkten när Microsoft-produkter uppdateras via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="c8986-218">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="c8986-219">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-219">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="c8986-220">100.86.91</span><span class="sxs-lookup"><span data-stu-id="c8986-220">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="c8986-221">För att säkerställa det mest fullständiga skyddet för dina macOS-enheter och i justeringen med Apple kommer den inbyggda säkerhetsuppdateringen för macOS att stoppas för OS-versioner som är äldre än [nuvarande – 2], MDATP för Mac-distribution och uppdateringar stöds inte längre på macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="c8986-221">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="c8986-222">MDATP för Mac-uppdateringar och förbättringar levereras till enheter med versionerna Catalina [10.15], Mojave [10.14] och High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="c8986-222">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="c8986-223">Om du redan har MDATP för Mac distribuerat till dina Sierra[10.12]-enheter bör du uppgradera till den senaste macOS-versionen för att undvika risken att förlora skydd.</span><span class="sxs-lookup"><span data-stu-id="c8986-223">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="c8986-224">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-224">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="c8986-225">100.83.73</span><span class="sxs-lookup"><span data-stu-id="c8986-225">100.83.73</span></span>

- <span data-ttu-id="c8986-226">Fler kontroller för IT-administratörer har [lagts till för hantering av undantag](mac-preferences.md#exclusion-merge-policy), hantering av [hottypsinställningar](mac-preferences.md#threat-type-settings-merge-policy)och [inte tillagd hotåtgärder](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="c8986-226">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="c8986-227">När Fullständig diskåtkomst inte är aktiverat på enheten visas nu en varning i statusmenyn</span><span class="sxs-lookup"><span data-stu-id="c8986-227">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="c8986-228">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-228">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="c8986-229">100.82.60</span><span class="sxs-lookup"><span data-stu-id="c8986-229">100.82.60</span></span>

- <span data-ttu-id="c8986-230">Vi har åtgärdat ett problem där produkten inte började följa en definitionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="c8986-230">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="c8986-231">100.80.42</span><span class="sxs-lookup"><span data-stu-id="c8986-231">100.80.42</span></span>

- <span data-ttu-id="c8986-232">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-232">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="c8986-233">100.79.42</span><span class="sxs-lookup"><span data-stu-id="c8986-233">100.79.42</span></span>

- <span data-ttu-id="c8986-234">Åtgärdat ett problem där Microsoft Defender för Slutpunkt på Mac ibland störde Time Machine</span><span class="sxs-lookup"><span data-stu-id="c8986-234">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="c8986-235">Lade till en ny växel till kommandoradsverktyget för att testa anslutningen med backendtjänsten</span><span class="sxs-lookup"><span data-stu-id="c8986-235">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="c8986-236">Lade till möjligheten att visa den fullständiga hothistoriken i användargränssnittet (kan nås från vyn **Skyddhistorik)**</span><span class="sxs-lookup"><span data-stu-id="c8986-236">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="c8986-237">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-237">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="c8986-238">100.72.15</span><span class="sxs-lookup"><span data-stu-id="c8986-238">100.72.15</span></span>

- <span data-ttu-id="c8986-239">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-239">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="c8986-240">100.70.99</span><span class="sxs-lookup"><span data-stu-id="c8986-240">100.70.99</span></span>

- <span data-ttu-id="c8986-241">Åtgärdat ett problem som påverkar möjligheten för vissa användare att uppgradera till macOS Catalina när realtidsskydd har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c8986-241">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="c8986-242">Det här sporadiska problemet orsakades av Microsoft Defender för att Slutpunktslåsa filer i Catalina-uppgraderingspaket vid genomsökning av dem efter hot, vilket ledde till fel i uppgraderingssekvensen.</span><span class="sxs-lookup"><span data-stu-id="c8986-242">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="c8986-243">100.68.99</span><span class="sxs-lookup"><span data-stu-id="c8986-243">100.68.99</span></span>

- <span data-ttu-id="c8986-244">Lade till möjligheten att konfigurera antivirusfunktionen för att köras i [passiv form](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c8986-244">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="c8986-245">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-245">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="c8986-246">100.65.28</span><span class="sxs-lookup"><span data-stu-id="c8986-246">100.65.28</span></span>

- <span data-ttu-id="c8986-247">Tillagt stöd för macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="c8986-247">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c8986-248">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="c8986-248">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="c8986-249">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="c8986-249">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="c8986-250">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="c8986-250">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="c8986-251">Mekanismen för att bevilja detta medgivande beror på hur du har distribuerat Microsoft Defender för Endpoint:</span><span class="sxs-lookup"><span data-stu-id="c8986-251">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="c8986-252">För manuell distribution finns de uppdaterade instruktionerna i [avsnittet Om manuell](mac-install-manually.md#how-to-allow-full-disk-access) distribution.</span><span class="sxs-lookup"><span data-stu-id="c8986-252">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="c8986-253">För hanterade distributioner, se de uppdaterade anvisningarna i [JAMF-baserad](mac-install-with-jamf.md) [distribution Microsoft Intune distributionsbaserade ämnen.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="c8986-253">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="c8986-254">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c8986-254">Performance improvements & bug fixes</span></span>
