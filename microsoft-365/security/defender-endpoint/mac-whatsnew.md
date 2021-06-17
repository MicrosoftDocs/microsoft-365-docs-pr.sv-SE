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
ms.openlocfilehash: a6415ec7d39bceeb4b68de164bbdcf6ef34755ff
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984778"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="9b4c6-104">Vad är nytt i Microsoft Defender för slutpunkt på Mac</span><span class="sxs-lookup"><span data-stu-id="9b4c6-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b4c6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9b4c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b4c6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b4c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9b4c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b4c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9b4c6-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9b4c6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b4c6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="9b4c6-110">På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="9b4c6-111">Om du är en befintlig kund som uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som listas på [den här sidan.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="9b4c6-112">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-112">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="9b4c6-113">Åtgärdat ett problem där samtidig åtkomst till nyckelringen från Microsoft Defender för Endpoint och andra program kan leda till skadade nyckelringar.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-113">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="9b4c6-114">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-114">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="9b4c6-115">Från och med den här versionen kommer hot som upptäckts under sökning på begäran av antivirus som utlöses via kommandoradsklienten att åtgärdas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-115">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="9b4c6-116">Hot som upptäckts vid genomsökningar som utlösts via användargränssnittet kräver fortfarande manuell åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-116">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="9b4c6-117">`mdatp diagnostic real-time-protection-statistics` stöder nu ytterligare två växlar:</span><span class="sxs-lookup"><span data-stu-id="9b4c6-117">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="9b4c6-118">`--sort`: Sorterar resultatet fallande efter totalt antal genomsökta filer</span><span class="sxs-lookup"><span data-stu-id="9b4c6-118">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="9b4c6-119">`--top N`: visar de översta N-resultaten (fungerar bara om `--sort` anges också)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-119">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="9b4c6-120">Prestandaförbättringar (särskilt för när IST. används) & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-120">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="9b4c6-121">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-121">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="9b4c6-122">Åtgärd för att hantera förfallotiden för Apple-certifikat för macOS Catalina och tidigare.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-122">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="9b4c6-123">Den här korrigeringen återställer & funktioner för sårbarhetshantering (TVM).</span><span class="sxs-lookup"><span data-stu-id="9b4c6-123">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="9b4c6-124">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-124">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="9b4c6-125">Microsoft Defender för Slutpunkt på macOS är nu tillgänglig i förhandsversion för kunder inom myndigheter i USA.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-125">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="9b4c6-126">Mer information finns i [Microsoft Defender för slutpunkt för kunder inom amerikanska myndigheter.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-126">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="9b4c6-127">Prestandaförbättringar (särskilt vid den situation då appen XCode Bugg används) som & programkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-127">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="9b4c6-128">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-128">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="9b4c6-129">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-129">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="9b4c6-130">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="9b4c6-130">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="9b4c6-131">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-131">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="9b4c6-132">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-132">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="9b4c6-133">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-133">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="9b4c6-134">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-134">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="9b4c6-135">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-135">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="9b4c6-136">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-136">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="9b4c6-137">Den gamla kommandoradsverktygets syntax är inaktuell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-137">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="9b4c6-138">Mer information om den nya syntaxen finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="9b4c6-138">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="9b4c6-139">Lade till en ny kommandoradsväxel för att inaktivera nätverkstillägget: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="9b4c6-139">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="9b4c6-140">Det här kommandot kan vara användbart för att felsöka nätverksproblem som kan ha att göra med Microsoft Defender för Slutpunkt på Mac</span><span class="sxs-lookup"><span data-stu-id="9b4c6-140">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="9b4c6-141">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-141">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="9b4c6-142">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-142">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="9b4c6-143">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-143">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="9b4c6-144">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-144">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="9b4c6-145">Förbättrad tillförlitlighet för agenten när du kör på macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="9b4c6-145">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="9b4c6-146">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="9b4c6-146">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="9b4c6-147">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-147">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="9b4c6-148">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-148">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="9b4c6-149">Villkor togs bort när Microsoft Defender för Endpoint utlöste ett fel i macOS 11 (Big Sur) som visar sig i en kernel-panik</span><span class="sxs-lookup"><span data-stu-id="9b4c6-149">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="9b4c6-150">Åtgärdat en minnesläcka i Endpoint Security-systemtillägget när det kördes på mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-150">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="9b4c6-151">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-151">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="9b4c6-152">101.10.72</span><span class="sxs-lookup"><span data-stu-id="9b4c6-152">101.10.72</span></span>

- <span data-ttu-id="9b4c6-153">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-153">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="9b4c6-154">101.09.61</span><span class="sxs-lookup"><span data-stu-id="9b4c6-154">101.09.61</span></span>

- <span data-ttu-id="9b4c6-155">Lade till en ny hanterad inställning [för att inaktivera alternativet att skicka feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-155">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="9b4c6-156">Statusmenyikonen visar ett felfritt läge när produktinställningarna hanteras.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-156">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="9b4c6-157">Tidigare visade statusmenyikonen ett varningsmeddelande eller felläge, även om produktinställningarna hanterades av administratören</span><span class="sxs-lookup"><span data-stu-id="9b4c6-157">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="9b4c6-158">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-158">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="9b4c6-159">101.09.50</span><span class="sxs-lookup"><span data-stu-id="9b4c6-159">101.09.50</span></span>

- <span data-ttu-id="9b4c6-160">Den här produktversionen har validerats på macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="9b4c6-160">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="9b4c6-161">Den nya syntaxen `mdatp` för kommandoradsverktyget är nu standard.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-161">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="9b4c6-162">Mer information om den nya syntaxen finns i [Resurser för Microsoft Defender för Slutpunkt i macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-162">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="9b4c6-163">Syntaxen för det gamla kommandoradsverktyget tas bort från produkten **den 1 januari 2021.**</span><span class="sxs-lookup"><span data-stu-id="9b4c6-163">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="9b4c6-164">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="9b4c6-164">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="9b4c6-165">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-165">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="9b4c6-166">101.09.49</span><span class="sxs-lookup"><span data-stu-id="9b4c6-166">101.09.49</span></span>

- <span data-ttu-id="9b4c6-167">Förbättringar av användargränssnittet för att skilja på undantag som hanteras av IT-administratören och undantag som definieras av den lokala användaren</span><span class="sxs-lookup"><span data-stu-id="9b4c6-167">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="9b4c6-168">Förbättrad CPU-användning vid genomsökningar på begäran</span><span class="sxs-lookup"><span data-stu-id="9b4c6-168">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="9b4c6-169">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-169">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="9b4c6-170">101.07.23</span><span class="sxs-lookup"><span data-stu-id="9b4c6-170">101.07.23</span></span>

- <span data-ttu-id="9b4c6-171">Nya fält har lagts till i utdata `mdatp --health` för att kontrollera status för passivt läge och Identifiering och åtgärd på slutpunkt grupp-ID</span><span class="sxs-lookup"><span data-stu-id="9b4c6-171">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="9b4c6-172">`mdatp --health` ersätts med `mdatp health` i en framtida produktuppdatering.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-172">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="9b4c6-173">Åtgärdat ett fel där automatisk exempelinskick inte har markerats som hanterat i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="9b4c6-173">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="9b4c6-174">Nya inställningar för att kontrollera bevarandet av objekt i historiken för antivirussökning har lagts till.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-174">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="9b4c6-175">Du kan nu [ange antalet dagar för att behålla objekt i genomsökningshistoriken](mac-preferences.md#antivirus-scan-history-retention-in-days) och ange det högsta antalet objekt i [genomsökningshistoriken](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-175">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="9b4c6-176">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-176">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="9b4c6-177">101.06.63</span><span class="sxs-lookup"><span data-stu-id="9b4c6-177">101.06.63</span></span>

- <span data-ttu-id="9b4c6-178">Åtgärdat en prestanda regression som introducerades i version `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="9b4c6-178">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="9b4c6-179">Regressionen infördes med korrigeringen för att eliminera kernel-panik som en del kunder har observerat vid åtkomst till SMB-resurser.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-179">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="9b4c6-180">Vi har återställt den här kodändringen och undersöker alternativa sätt att eliminera kernel-panik.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-180">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="9b4c6-181">101.05.17</span><span class="sxs-lookup"><span data-stu-id="9b4c6-181">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b4c6-182">Vi arbetar med en ny och förbättrad syntax `mdatp` för kommandoradsverktyget.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-182">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="9b4c6-183">Den nya syntaxen är för närvarande standard i uppdateringskanalerna Insider – snabbt och Insider – långsamt.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-183">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="9b4c6-184">Vi rekommenderar att du använder den nya syntaxen för att använda den här syntaxen.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-184">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="9b4c6-185">Vi fortsätter att stödja den gamla syntaxen parallellt med den nya syntaxen och kommer att ge mer kommunikation om utfasningsplanen för den gamla syntaxen under de kommande månaderna.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-185">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="9b4c6-186">Åtgärdat en kernel-panik som ibland uppstod när man fick åtkomst till SMB-filresurser</span><span class="sxs-lookup"><span data-stu-id="9b4c6-186">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="9b4c6-187">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-187">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="9b4c6-188">101.05.16</span><span class="sxs-lookup"><span data-stu-id="9b4c6-188">101.05.16</span></span>

- <span data-ttu-id="9b4c6-189">Förbättringar av snabbsökningslogik för att avsevärt minska antalet skannade filer</span><span class="sxs-lookup"><span data-stu-id="9b4c6-189">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="9b4c6-190">Lade [till stöd för Komplettera](mac-resources.md#how-to-enable-autocompletion) automatiskt för kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="9b4c6-190">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="9b4c6-191">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-191">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="9b4c6-192">101.03.12</span><span class="sxs-lookup"><span data-stu-id="9b4c6-192">101.03.12</span></span>

- <span data-ttu-id="9b4c6-193">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-193">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="9b4c6-194">101.01.54</span><span class="sxs-lookup"><span data-stu-id="9b4c6-194">101.01.54</span></span>

- <span data-ttu-id="9b4c6-195">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="9b4c6-195">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9b4c6-196">Förbättrade hjälpmedelsfunktioner</span><span class="sxs-lookup"><span data-stu-id="9b4c6-196">Accessibility improvements</span></span>
- <span data-ttu-id="9b4c6-197">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-197">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="9b4c6-198">101.00.31</span><span class="sxs-lookup"><span data-stu-id="9b4c6-198">101.00.31</span></span>

- <span data-ttu-id="9b4c6-199">Förbättrad [produktinitiering för Intune-användare](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-199">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="9b4c6-200">Undantag [från antivirus har nu stöd för jokertecken](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-200">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="9b4c6-201">Lade till möjligheten att utlösa antivirusskanningar från macOS-snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-201">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="9b4c6-202">Nu kan du högerklicka på en fil eller en mapp i Finder och välja **Sök med Microsoft Defender för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="9b4c6-202">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="9b4c6-203">Nedgradering av produkter på plats kommer nu uttryckligen inte att tillåtas av installationsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-203">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="9b4c6-204">Om du behöver nedgradera måste du först avinstallera den befintliga versionen och konfigurera om enheten</span><span class="sxs-lookup"><span data-stu-id="9b4c6-204">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="9b4c6-205">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-205">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="9b4c6-206">100.90.27</span><span class="sxs-lookup"><span data-stu-id="9b4c6-206">100.90.27</span></span>

- <span data-ttu-id="9b4c6-207">Nu kan du [ange en uppdateringskanal](mac-updates.md#set-the-channel-name) för Microsoft Defender för Slutpunkt i macOS som skiljer sig från den systemomfattande uppdateringskanalen</span><span class="sxs-lookup"><span data-stu-id="9b4c6-207">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="9b4c6-208">Ny produktikon</span><span class="sxs-lookup"><span data-stu-id="9b4c6-208">New product icon</span></span>
- <span data-ttu-id="9b4c6-209">Andra förbättringar av användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="9b4c6-209">Other user experience improvements</span></span>
- <span data-ttu-id="9b4c6-210">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-210">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="9b4c6-211">100.86.92</span><span class="sxs-lookup"><span data-stu-id="9b4c6-211">100.86.92</span></span>

- <span data-ttu-id="9b4c6-212">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="9b4c6-212">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9b4c6-213">Åtgärdat ett problem där produkten ibland inte rensade alla filer under `/Library/Application Support/Microsoft/Defender` avinstallationen</span><span class="sxs-lookup"><span data-stu-id="9b4c6-213">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="9b4c6-214">Minskad CPU-användning av produkten när Microsoft-produkter uppdateras via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="9b4c6-214">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="9b4c6-215">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-215">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="9b4c6-216">100.86.91</span><span class="sxs-lookup"><span data-stu-id="9b4c6-216">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="9b4c6-217">För att säkerställa det mest fullständiga skyddet för dina macOS-enheter och i justeringen med Apple kommer den inbyggda säkerhetsuppdateringen för macOS att stoppas för OS-versioner som är äldre än [nuvarande – 2], MDATP för Mac-distribution och uppdateringar stöds inte längre på macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="9b4c6-217">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="9b4c6-218">MDATP för Mac-uppdateringar och förbättringar levereras till enheter med versionerna Catalina [10.15], Mojave [10.14] och High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="9b4c6-218">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="9b4c6-219">Om du redan har MDATP för Mac distribuerat till dina Sierra[10.12]-enheter bör du uppgradera till den senaste macOS-versionen för att undvika risken att förlora skydd.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-219">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="9b4c6-220">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-220">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="9b4c6-221">100.83.73</span><span class="sxs-lookup"><span data-stu-id="9b4c6-221">100.83.73</span></span>

- <span data-ttu-id="9b4c6-222">Fler kontroller för IT-administratörer har [lagts till för hantering av undantag](mac-preferences.md#exclusion-merge-policy), hantering av [hottypsinställningar](mac-preferences.md#threat-type-settings-merge-policy)och [inte tillagd hotåtgärder](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-222">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="9b4c6-223">När Fullständig diskåtkomst inte är aktiverat på enheten visas nu en varning i statusmenyn</span><span class="sxs-lookup"><span data-stu-id="9b4c6-223">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="9b4c6-224">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-224">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="9b4c6-225">100.82.60</span><span class="sxs-lookup"><span data-stu-id="9b4c6-225">100.82.60</span></span>

- <span data-ttu-id="9b4c6-226">Vi har åtgärdat ett problem där produkten inte började följa en definitionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-226">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="9b4c6-227">100.80.42</span><span class="sxs-lookup"><span data-stu-id="9b4c6-227">100.80.42</span></span>

- <span data-ttu-id="9b4c6-228">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-228">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="9b4c6-229">100.79.42</span><span class="sxs-lookup"><span data-stu-id="9b4c6-229">100.79.42</span></span>

- <span data-ttu-id="9b4c6-230">Åtgärdat ett problem där Microsoft Defender för Slutpunkt på Mac ibland störde Time Machine</span><span class="sxs-lookup"><span data-stu-id="9b4c6-230">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="9b4c6-231">Lade till en ny växel till kommandoradsverktyget för att testa anslutningen med backendtjänsten</span><span class="sxs-lookup"><span data-stu-id="9b4c6-231">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="9b4c6-232">Lade till möjligheten att visa den fullständiga hothistoriken i användargränssnittet (kan nås från vyn **Skyddhistorik)**</span><span class="sxs-lookup"><span data-stu-id="9b4c6-232">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="9b4c6-233">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-233">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="9b4c6-234">100.72.15</span><span class="sxs-lookup"><span data-stu-id="9b4c6-234">100.72.15</span></span>

- <span data-ttu-id="9b4c6-235">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-235">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="9b4c6-236">100.70.99</span><span class="sxs-lookup"><span data-stu-id="9b4c6-236">100.70.99</span></span>

- <span data-ttu-id="9b4c6-237">Åtgärdat ett problem som påverkar möjligheten för vissa användare att uppgradera till macOS Catalina när realtidsskydd har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-237">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="9b4c6-238">Det här sporadiska problemet orsakades av Microsoft Defender för att Slutpunktslåsa filer i Catalina-uppgraderingspaket vid genomsökning av dem efter hot, vilket ledde till fel i uppgraderingssekvensen.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-238">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="9b4c6-239">100.68.99</span><span class="sxs-lookup"><span data-stu-id="9b4c6-239">100.68.99</span></span>

- <span data-ttu-id="9b4c6-240">Lade till möjligheten att konfigurera antivirusfunktionen för att köras i [passiv form](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-240">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="9b4c6-241">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-241">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="9b4c6-242">100.65.28</span><span class="sxs-lookup"><span data-stu-id="9b4c6-242">100.65.28</span></span>

- <span data-ttu-id="9b4c6-243">Tillagt stöd för macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="9b4c6-243">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="9b4c6-244">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-244">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="9b4c6-245">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-245">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="9b4c6-246">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-246">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="9b4c6-247">Mekanismen för att bevilja detta medgivande beror på hur du har distribuerat Microsoft Defender för Endpoint:</span><span class="sxs-lookup"><span data-stu-id="9b4c6-247">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="9b4c6-248">För manuell distribution finns de uppdaterade instruktionerna i [avsnittet Om manuell](mac-install-manually.md#how-to-allow-full-disk-access) distribution.</span><span class="sxs-lookup"><span data-stu-id="9b4c6-248">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="9b4c6-249">För hanterade distributioner, se de uppdaterade anvisningarna i [JAMF-baserad](mac-install-with-jamf.md) [distribution Microsoft Intune distributionsbaserade ämnen.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="9b4c6-249">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="9b4c6-250">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="9b4c6-250">Performance improvements & bug fixes</span></span>
