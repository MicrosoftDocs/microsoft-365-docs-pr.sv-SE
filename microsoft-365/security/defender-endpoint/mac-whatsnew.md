---
title: Vad är nytt i Microsoft Defender för Slutpunkt för Mac
description: Läs mer om de viktigaste ändringarna för tidigare versioner av Microsoft Defender för Endpoint för Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
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
ms.openlocfilehash: 16d78cf014e775ecb98a59d90b5734836eb3cbf2
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476631"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="dd406-104">Vad är nytt i Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="dd406-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd406-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="dd406-105">**Applies to:**</span></span>
- [<span data-ttu-id="dd406-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd406-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd406-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd406-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd406-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="dd406-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd406-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="dd406-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="dd406-110">På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="dd406-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="dd406-111">Om du är en befintlig kund som uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som listas på [den här sidan.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dd406-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd406-112">Stöd för macOS 10.13 (High Sierra) har upphört den 15 februari 2021.</span><span class="sxs-lookup"><span data-stu-id="dd406-112">Support for macOS 10.13 (High Sierra) has been discontinued on February 15th, 2021.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="dd406-113">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-113">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="dd406-114">Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran.</span><span class="sxs-lookup"><span data-stu-id="dd406-114">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="dd406-115">Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="dd406-115">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="dd406-116">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-116">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="dd406-117">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-117">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="dd406-118">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-118">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="dd406-119">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-119">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="dd406-120">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-120">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="dd406-121">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-121">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="dd406-122">Den gamla kommandoradsverktygets syntax är inaktuell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="dd406-122">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="dd406-123">Mer information om den nya syntaxen finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="dd406-123">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="dd406-124">Lade till en ny kommandoradsväxel för att inaktivera nätverkstillägget: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="dd406-124">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="dd406-125">Det här kommandot kan vara användbart för att felsöka nätverksproblem som kan ha att göra med Microsoft Defender för Endpoint för Mac</span><span class="sxs-lookup"><span data-stu-id="dd406-125">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="dd406-126">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-126">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="dd406-127">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-127">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="dd406-128">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-128">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="dd406-129">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-129">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="dd406-130">Förbättrad tillförlitlighet för agenten när du kör på macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="dd406-130">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="dd406-131">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="dd406-131">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="dd406-132">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-132">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="dd406-133">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="dd406-133">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="dd406-134">Villkor togs bort när Microsoft Defender för Endpoint utlöste ett fel i macOS 11 (Big Sur) som visar sig i en kernel-panik</span><span class="sxs-lookup"><span data-stu-id="dd406-134">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="dd406-135">Åtgärdat en minnesläcka i Endpoint Security-systemtillägget när det kördes på mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="dd406-135">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="dd406-136">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-136">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="dd406-137">101.10.72</span><span class="sxs-lookup"><span data-stu-id="dd406-137">101.10.72</span></span>

- <span data-ttu-id="dd406-138">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-138">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="dd406-139">101.09.61</span><span class="sxs-lookup"><span data-stu-id="dd406-139">101.09.61</span></span>

- <span data-ttu-id="dd406-140">Lade till en ny hanterad inställning [för att inaktivera alternativet att skicka feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="dd406-140">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="dd406-141">Statusmenyikonen visar ett felfritt läge när produktinställningarna hanteras.</span><span class="sxs-lookup"><span data-stu-id="dd406-141">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="dd406-142">Tidigare visade statusmenyikonen ett varningsmeddelande eller felläge, även om produktinställningarna hanterades av administratören</span><span class="sxs-lookup"><span data-stu-id="dd406-142">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="dd406-143">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-143">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="dd406-144">101.09.50</span><span class="sxs-lookup"><span data-stu-id="dd406-144">101.09.50</span></span>

- <span data-ttu-id="dd406-145">Den här produktversionen har validerats på macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="dd406-145">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="dd406-146">Den nya syntaxen `mdatp` för kommandoradsverktyget är nu standard.</span><span class="sxs-lookup"><span data-stu-id="dd406-146">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="dd406-147">Mer information om den nya syntaxen finns i [Resurser för Microsoft Defender för Slutpunkt för Mac](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="dd406-147">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd406-148">Syntaxen för det gamla kommandoradsverktyget tas bort från produkten **den 1 januari 2021.**</span><span class="sxs-lookup"><span data-stu-id="dd406-148">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="dd406-149">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="dd406-149">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="dd406-150">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-150">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="dd406-151">101.09.49</span><span class="sxs-lookup"><span data-stu-id="dd406-151">101.09.49</span></span>

- <span data-ttu-id="dd406-152">Förbättringar av användargränssnittet för att skilja på undantag som hanteras av IT-administratören och undantag som definieras av den lokala användaren</span><span class="sxs-lookup"><span data-stu-id="dd406-152">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="dd406-153">Förbättrad CPU-användning vid genomsökningar på begäran</span><span class="sxs-lookup"><span data-stu-id="dd406-153">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="dd406-154">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-154">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="dd406-155">101.07.23</span><span class="sxs-lookup"><span data-stu-id="dd406-155">101.07.23</span></span>

- <span data-ttu-id="dd406-156">Nya fält har lagts till i utdata `mdatp --health` för kontroll av status för passivt läge och EDR-grupp-ID</span><span class="sxs-lookup"><span data-stu-id="dd406-156">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="dd406-157">`mdatp --health` ersätts med `mdatp health` i en framtida produktuppdatering.</span><span class="sxs-lookup"><span data-stu-id="dd406-157">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="dd406-158">Åtgärdat ett fel där automatisk exempelinskick inte har markerats som hanterat i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="dd406-158">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="dd406-159">Nya inställningar för att kontrollera bevarandet av objekt i historiken för antivirussökning har lagts till.</span><span class="sxs-lookup"><span data-stu-id="dd406-159">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="dd406-160">Du kan nu [ange antalet dagar för att behålla objekt i genomsökningshistoriken](mac-preferences.md#antivirus-scan-history-retention-in-days) och ange det högsta antalet objekt i [genomsökningshistoriken](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="dd406-160">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="dd406-161">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-161">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="dd406-162">101.06.63</span><span class="sxs-lookup"><span data-stu-id="dd406-162">101.06.63</span></span>

- <span data-ttu-id="dd406-163">Åtgärdat en prestanda regression som introducerades i version `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="dd406-163">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="dd406-164">Regressionen infördes med korrigeringen för att eliminera kernel-panik som en del kunder har observerat vid åtkomst till SMB-resurser.</span><span class="sxs-lookup"><span data-stu-id="dd406-164">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="dd406-165">Vi har återställt den här kodändringen och undersöker alternativa sätt att eliminera kernel-panik.</span><span class="sxs-lookup"><span data-stu-id="dd406-165">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="dd406-166">101.05.17</span><span class="sxs-lookup"><span data-stu-id="dd406-166">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd406-167">Vi arbetar med en ny och förbättrad syntax `mdatp` för kommandoradsverktyget.</span><span class="sxs-lookup"><span data-stu-id="dd406-167">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="dd406-168">Den nya syntaxen är för närvarande standard i uppdateringskanalerna Insider – snabbt och Insider – långsamt.</span><span class="sxs-lookup"><span data-stu-id="dd406-168">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="dd406-169">Vi rekommenderar att du använder den nya syntaxen för att använda den här syntaxen.</span><span class="sxs-lookup"><span data-stu-id="dd406-169">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="dd406-170">Vi fortsätter att stödja den gamla syntaxen parallellt med den nya syntaxen och kommer att ge mer kommunikation om utfasningsplanen för den gamla syntaxen under de kommande månaderna.</span><span class="sxs-lookup"><span data-stu-id="dd406-170">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="dd406-171">Åtgärdat en kernel-panik som ibland uppstod när man fick åtkomst till SMB-filresurser</span><span class="sxs-lookup"><span data-stu-id="dd406-171">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="dd406-172">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-172">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="dd406-173">101.05.16</span><span class="sxs-lookup"><span data-stu-id="dd406-173">101.05.16</span></span>

- <span data-ttu-id="dd406-174">Förbättringar av snabbsökningslogik för att avsevärt minska antalet skannade filer</span><span class="sxs-lookup"><span data-stu-id="dd406-174">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="dd406-175">Lade [till stöd för Komplettera](mac-resources.md#how-to-enable-autocompletion) automatiskt för kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="dd406-175">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="dd406-176">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-176">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="dd406-177">101.03.12</span><span class="sxs-lookup"><span data-stu-id="dd406-177">101.03.12</span></span>

- <span data-ttu-id="dd406-178">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-178">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="dd406-179">101.01.54</span><span class="sxs-lookup"><span data-stu-id="dd406-179">101.01.54</span></span>

- <span data-ttu-id="dd406-180">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="dd406-180">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="dd406-181">Förbättrade hjälpmedelsfunktioner</span><span class="sxs-lookup"><span data-stu-id="dd406-181">Accessibility improvements</span></span>
- <span data-ttu-id="dd406-182">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-182">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="dd406-183">101.00.31</span><span class="sxs-lookup"><span data-stu-id="dd406-183">101.00.31</span></span>

- <span data-ttu-id="dd406-184">Förbättrad [produktinitiering för Intune-användare](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="dd406-184">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="dd406-185">Undantag [från antivirus har nu stöd för jokertecken](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="dd406-185">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="dd406-186">Lade till möjligheten att utlösa antivirusskanningar från macOS-snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="dd406-186">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="dd406-187">Nu kan du högerklicka på en fil eller en mapp i Finder och välja **Sök med Microsoft Defender för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="dd406-187">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="dd406-188">Nedgradering av produkter på plats kommer nu uttryckligen inte att tillåtas av installationsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="dd406-188">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="dd406-189">Om du behöver nedgradera måste du först avinstallera den befintliga versionen och konfigurera om enheten</span><span class="sxs-lookup"><span data-stu-id="dd406-189">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="dd406-190">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-190">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="dd406-191">100.90.27</span><span class="sxs-lookup"><span data-stu-id="dd406-191">100.90.27</span></span>

- <span data-ttu-id="dd406-192">Nu kan du [ange en uppdateringskanal](mac-updates.md#set-the-channel-name) för Microsoft Defender för Slutpunkt för Mac som skiljer sig från den systemomfattande uppdateringskanalen</span><span class="sxs-lookup"><span data-stu-id="dd406-192">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="dd406-193">Ny produktikon</span><span class="sxs-lookup"><span data-stu-id="dd406-193">New product icon</span></span>
- <span data-ttu-id="dd406-194">Andra förbättringar av användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="dd406-194">Other user experience improvements</span></span>
- <span data-ttu-id="dd406-195">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-195">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="dd406-196">100.86.92</span><span class="sxs-lookup"><span data-stu-id="dd406-196">100.86.92</span></span>

- <span data-ttu-id="dd406-197">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="dd406-197">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="dd406-198">Åtgärdat ett problem där produkten ibland inte rensade alla filer under `/Library/Application Support/Microsoft/Defender` avinstallationen</span><span class="sxs-lookup"><span data-stu-id="dd406-198">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="dd406-199">Minskad CPU-användning av produkten när Microsoft-produkter uppdateras via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="dd406-199">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="dd406-200">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-200">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="dd406-201">100.86.91</span><span class="sxs-lookup"><span data-stu-id="dd406-201">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="dd406-202">För att säkerställa det mest fullständiga skyddet för dina macOS-enheter och i justeringen med Apple kommer den inbyggda säkerhetsuppdateringen för macOS att stoppas för OS-versioner som är äldre än [nuvarande – 2], MDATP för Mac-distribution och uppdateringar stöds inte längre på macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="dd406-202">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="dd406-203">MDATP för Mac-uppdateringar och förbättringar levereras till enheter med versionerna Catalina [10.15], Mojave [10.14] och High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="dd406-203">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="dd406-204">Om du redan har MDATP för Mac distribuerat till dina Sierra[10.12]-enheter bör du uppgradera till den senaste macOS-versionen för att undvika risken att förlora skydd.</span><span class="sxs-lookup"><span data-stu-id="dd406-204">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="dd406-205">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-205">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="dd406-206">100.83.73</span><span class="sxs-lookup"><span data-stu-id="dd406-206">100.83.73</span></span>

- <span data-ttu-id="dd406-207">Fler kontroller för IT-administratörer har [lagts till för hantering av undantag](mac-preferences.md#exclusion-merge-policy), hantering av [hottypsinställningar](mac-preferences.md#threat-type-settings-merge-policy)och [inte tillagd hotåtgärder](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="dd406-207">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="dd406-208">När Fullständig diskåtkomst inte är aktiverat på enheten visas nu en varning i statusmenyn</span><span class="sxs-lookup"><span data-stu-id="dd406-208">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="dd406-209">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-209">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="dd406-210">100.82.60</span><span class="sxs-lookup"><span data-stu-id="dd406-210">100.82.60</span></span>

- <span data-ttu-id="dd406-211">Vi har åtgärdat ett problem där produkten inte började följa en definitionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="dd406-211">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="dd406-212">100.80.42</span><span class="sxs-lookup"><span data-stu-id="dd406-212">100.80.42</span></span>

- <span data-ttu-id="dd406-213">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-213">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="dd406-214">100.79.42</span><span class="sxs-lookup"><span data-stu-id="dd406-214">100.79.42</span></span>

- <span data-ttu-id="dd406-215">Åtgärdat ett problem där Microsoft Defender för Endpoint för Mac ibland störde Time Machine</span><span class="sxs-lookup"><span data-stu-id="dd406-215">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="dd406-216">Lade till en ny växel till kommandoradsverktyget för att testa anslutningen med backendtjänsten</span><span class="sxs-lookup"><span data-stu-id="dd406-216">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="dd406-217">Lade till möjligheten att visa den fullständiga hothistoriken i användargränssnittet (kan nås från vyn **Skyddhistorik)**</span><span class="sxs-lookup"><span data-stu-id="dd406-217">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="dd406-218">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-218">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="dd406-219">100.72.15</span><span class="sxs-lookup"><span data-stu-id="dd406-219">100.72.15</span></span>

- <span data-ttu-id="dd406-220">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-220">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="dd406-221">100.70.99</span><span class="sxs-lookup"><span data-stu-id="dd406-221">100.70.99</span></span>

- <span data-ttu-id="dd406-222">Åtgärdat ett problem som påverkar möjligheten för vissa användare att uppgradera till macOS Catalina när realtidsskydd har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="dd406-222">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="dd406-223">Det här sporadiska problemet orsakades av Microsoft Defender för att Slutpunktslåsa filer i Catalina-uppgraderingspaket vid genomsökning av dem efter hot, vilket ledde till fel i uppgraderingssekvensen.</span><span class="sxs-lookup"><span data-stu-id="dd406-223">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="dd406-224">100.68.99</span><span class="sxs-lookup"><span data-stu-id="dd406-224">100.68.99</span></span>

- <span data-ttu-id="dd406-225">Lade till möjligheten att konfigurera antivirusfunktionen för att köras i [passiv form](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="dd406-225">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="dd406-226">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-226">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="dd406-227">100.65.28</span><span class="sxs-lookup"><span data-stu-id="dd406-227">100.65.28</span></span>

- <span data-ttu-id="dd406-228">Tillagt stöd för macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="dd406-228">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="dd406-229">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="dd406-229">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="dd406-230">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="dd406-230">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="dd406-231">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="dd406-231">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="dd406-232">Mekanismen för att bevilja detta medgivande beror på hur du har distribuerat Microsoft Defender för Endpoint:</span><span class="sxs-lookup"><span data-stu-id="dd406-232">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="dd406-233">För manuell distribution finns de uppdaterade instruktionerna i [avsnittet Om manuell](mac-install-manually.md#how-to-allow-full-disk-access) distribution.</span><span class="sxs-lookup"><span data-stu-id="dd406-233">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="dd406-234">För hanterade distributioner, se de uppdaterade instruktionerna i [DEN JAMF-baserade distributionen](mac-install-with-jamf.md) och [i avsnitten om Microsoft Intune-baserad](mac-install-with-intune.md#create-system-configuration-profiles) distribution.</span><span class="sxs-lookup"><span data-stu-id="dd406-234">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="dd406-235">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="dd406-235">Performance improvements & bug fixes</span></span>
