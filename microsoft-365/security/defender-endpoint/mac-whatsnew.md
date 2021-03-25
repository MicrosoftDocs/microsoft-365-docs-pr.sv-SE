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
ms.openlocfilehash: 7163220809acbff934a4142ee8f4422ca5b66578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072105"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="c68d0-104">Vad är nytt i Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="c68d0-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c68d0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c68d0-105">**Applies to:**</span></span>
- [<span data-ttu-id="c68d0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c68d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c68d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c68d0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c68d0-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c68d0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c68d0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c68d0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="c68d0-110">På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="c68d0-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="c68d0-111">Om du är en befintlig kund som uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som listas på [den här sidan.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c68d0-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c68d0-112">Stöd för macOS 10.13 (High Sierra) upphör den 15 februari 2021.</span><span class="sxs-lookup"><span data-stu-id="c68d0-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="c68d0-113">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="c68d0-113">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="c68d0-114">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-114">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="c68d0-115">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="c68d0-115">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="c68d0-116">Den gamla kommandoradsverktygets syntax är inaktuell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="c68d0-116">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="c68d0-117">Mer information om den nya syntaxen finns i [Resurser](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c68d0-117">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="c68d0-118">Lade till en ny kommandoradsväxel för att inaktivera nätverkstillägget: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="c68d0-118">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="c68d0-119">Det här kommandot kan vara användbart för att felsöka nätverksproblem som kan ha att göra med Microsoft Defender för Endpoint för Mac</span><span class="sxs-lookup"><span data-stu-id="c68d0-119">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="c68d0-120">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-120">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="c68d0-121">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="c68d0-121">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="c68d0-122">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-122">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="c68d0-123">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="c68d0-123">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="c68d0-124">Förbättrad tillförlitlighet för agenten när du kör på macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="c68d0-124">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="c68d0-125">Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="c68d0-125">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="c68d0-126">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-126">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="c68d0-127">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="c68d0-127">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="c68d0-128">Villkor togs bort när Microsoft Defender för Endpoint utlöste ett fel i macOS 11 (Big Sur) som visar sig i en kernel-panik</span><span class="sxs-lookup"><span data-stu-id="c68d0-128">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="c68d0-129">Åtgärdat en minnesläcka i Endpoint Security-systemtillägget när det kördes på mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="c68d0-129">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="c68d0-130">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-130">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="c68d0-131">101.10.72</span><span class="sxs-lookup"><span data-stu-id="c68d0-131">101.10.72</span></span>

- <span data-ttu-id="c68d0-132">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-132">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="c68d0-133">101.09.61</span><span class="sxs-lookup"><span data-stu-id="c68d0-133">101.09.61</span></span>

- <span data-ttu-id="c68d0-134">Lade till en ny hanterad inställning [för att inaktivera alternativet att skicka feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="c68d0-134">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="c68d0-135">Statusmenyikonen visar ett felfritt läge när produktinställningarna hanteras.</span><span class="sxs-lookup"><span data-stu-id="c68d0-135">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="c68d0-136">Tidigare visade statusmenyikonen ett varningsmeddelande eller felläge, även om produktinställningarna hanterades av administratören</span><span class="sxs-lookup"><span data-stu-id="c68d0-136">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="c68d0-137">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-137">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="c68d0-138">101.09.50</span><span class="sxs-lookup"><span data-stu-id="c68d0-138">101.09.50</span></span>

- <span data-ttu-id="c68d0-139">Den här produktversionen har validerats på macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="c68d0-139">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="c68d0-140">Den nya syntaxen `mdatp` för kommandoradsverktyget är nu standard.</span><span class="sxs-lookup"><span data-stu-id="c68d0-140">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="c68d0-141">Mer information om den nya syntaxen finns i [Resurser för Microsoft Defender för Slutpunkt för Mac](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="c68d0-141">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="c68d0-142">Syntaxen för det gamla kommandoradsverktyget tas bort från produkten **den 1 januari 2021.**</span><span class="sxs-lookup"><span data-stu-id="c68d0-142">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="c68d0-143">Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog</span><span class="sxs-lookup"><span data-stu-id="c68d0-143">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="c68d0-144">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-144">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="c68d0-145">101.09.49</span><span class="sxs-lookup"><span data-stu-id="c68d0-145">101.09.49</span></span>

- <span data-ttu-id="c68d0-146">Förbättringar av användargränssnittet för att skilja på undantag som hanteras av IT-administratören och undantag som definieras av den lokala användaren</span><span class="sxs-lookup"><span data-stu-id="c68d0-146">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="c68d0-147">Förbättrad CPU-användning vid genomsökningar på begäran</span><span class="sxs-lookup"><span data-stu-id="c68d0-147">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="c68d0-148">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-148">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="c68d0-149">101.07.23</span><span class="sxs-lookup"><span data-stu-id="c68d0-149">101.07.23</span></span>

- <span data-ttu-id="c68d0-150">Nya fält har lagts till i utdata `mdatp --health` för kontroll av status för passivt läge och EDR-grupp-ID</span><span class="sxs-lookup"><span data-stu-id="c68d0-150">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="c68d0-151">`mdatp --health` ersätts med `mdatp health` i en framtida produktuppdatering.</span><span class="sxs-lookup"><span data-stu-id="c68d0-151">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="c68d0-152">Åtgärdat ett fel där automatisk exempelinskick inte har markerats som hanterat i användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="c68d0-152">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="c68d0-153">Nya inställningar för att kontrollera bevarandet av objekt i historiken för antivirussökning har lagts till.</span><span class="sxs-lookup"><span data-stu-id="c68d0-153">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="c68d0-154">Du kan nu [ange antalet dagar för att behålla objekt i genomsökningshistoriken](mac-preferences.md#antivirus-scan-history-retention-in-days) och ange det högsta antalet objekt i [genomsökningshistoriken](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="c68d0-154">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="c68d0-155">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-155">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="c68d0-156">101.06.63</span><span class="sxs-lookup"><span data-stu-id="c68d0-156">101.06.63</span></span>

- <span data-ttu-id="c68d0-157">Åtgärdat en prestanda regression som introducerades i version `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="c68d0-157">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="c68d0-158">Regressionen infördes med korrigeringen för att eliminera kernel-panik som en del kunder har observerat vid åtkomst till SMB-resurser.</span><span class="sxs-lookup"><span data-stu-id="c68d0-158">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="c68d0-159">Vi har återställt den här kodändringen och undersöker alternativa sätt att eliminera kernel-panik.</span><span class="sxs-lookup"><span data-stu-id="c68d0-159">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="c68d0-160">101.05.17</span><span class="sxs-lookup"><span data-stu-id="c68d0-160">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c68d0-161">Vi arbetar med en ny och förbättrad syntax `mdatp` för kommandoradsverktyget.</span><span class="sxs-lookup"><span data-stu-id="c68d0-161">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="c68d0-162">Den nya syntaxen är för närvarande standard i uppdateringskanalerna Insider – snabbt och Insider – långsamt.</span><span class="sxs-lookup"><span data-stu-id="c68d0-162">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="c68d0-163">Vi rekommenderar att du använder den nya syntaxen för att använda den här syntaxen.</span><span class="sxs-lookup"><span data-stu-id="c68d0-163">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="c68d0-164">Vi fortsätter att stödja den gamla syntaxen parallellt med den nya syntaxen och kommer att ge mer kommunikation om utfasningsplanen för den gamla syntaxen under de kommande månaderna.</span><span class="sxs-lookup"><span data-stu-id="c68d0-164">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="c68d0-165">Åtgärdat en kernel-panik som ibland uppstod när man fick åtkomst till SMB-filresurser</span><span class="sxs-lookup"><span data-stu-id="c68d0-165">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="c68d0-166">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-166">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="c68d0-167">101.05.16</span><span class="sxs-lookup"><span data-stu-id="c68d0-167">101.05.16</span></span>

- <span data-ttu-id="c68d0-168">Förbättringar av snabbsökningslogik för att avsevärt minska antalet skannade filer</span><span class="sxs-lookup"><span data-stu-id="c68d0-168">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="c68d0-169">Lade [till stöd för Komplettera](mac-resources.md#how-to-enable-autocompletion) automatiskt för kommandoradsverktyget</span><span class="sxs-lookup"><span data-stu-id="c68d0-169">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="c68d0-170">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-170">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="c68d0-171">101.03.12</span><span class="sxs-lookup"><span data-stu-id="c68d0-171">101.03.12</span></span>

- <span data-ttu-id="c68d0-172">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-172">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="c68d0-173">101.01.54</span><span class="sxs-lookup"><span data-stu-id="c68d0-173">101.01.54</span></span>

- <span data-ttu-id="c68d0-174">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="c68d0-174">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c68d0-175">Förbättrade hjälpmedelsfunktioner</span><span class="sxs-lookup"><span data-stu-id="c68d0-175">Accessibility improvements</span></span>
- <span data-ttu-id="c68d0-176">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-176">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="c68d0-177">101.00.31</span><span class="sxs-lookup"><span data-stu-id="c68d0-177">101.00.31</span></span>

- <span data-ttu-id="c68d0-178">Förbättrad [produktinitiering för Intune-användare](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="c68d0-178">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="c68d0-179">Undantag [från antivirus har nu stöd för jokertecken](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="c68d0-179">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="c68d0-180">Lade till möjligheten att utlösa antivirusskanningar från macOS-snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="c68d0-180">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="c68d0-181">Nu kan du högerklicka på en fil eller en mapp i Finder och välja **Sök med Microsoft Defender för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="c68d0-181">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="c68d0-182">Nedgradering av produkter på plats kommer nu uttryckligen inte att tillåtas av installationsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="c68d0-182">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="c68d0-183">Om du behöver nedgradera måste du först avinstallera den befintliga versionen och konfigurera om enheten</span><span class="sxs-lookup"><span data-stu-id="c68d0-183">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="c68d0-184">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-184">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="c68d0-185">100.90.27</span><span class="sxs-lookup"><span data-stu-id="c68d0-185">100.90.27</span></span>

- <span data-ttu-id="c68d0-186">Nu kan du [ange en uppdateringskanal](mac-updates.md#set-the-channel-name) för Microsoft Defender för Slutpunkt för Mac som skiljer sig från den systemomfattande uppdateringskanalen</span><span class="sxs-lookup"><span data-stu-id="c68d0-186">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="c68d0-187">Ny produktikon</span><span class="sxs-lookup"><span data-stu-id="c68d0-187">New product icon</span></span>
- <span data-ttu-id="c68d0-188">Andra förbättringar av användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="c68d0-188">Other user experience improvements</span></span>
- <span data-ttu-id="c68d0-189">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-189">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="c68d0-190">100.86.92</span><span class="sxs-lookup"><span data-stu-id="c68d0-190">100.86.92</span></span>

- <span data-ttu-id="c68d0-191">Förbättringar kring kompatibilitet med Time Machine</span><span class="sxs-lookup"><span data-stu-id="c68d0-191">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c68d0-192">Åtgärdat ett problem där produkten ibland inte rensade alla filer under `/Library/Application Support/Microsoft/Defender` avinstallationen</span><span class="sxs-lookup"><span data-stu-id="c68d0-192">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="c68d0-193">Minskad CPU-användning av produkten när Microsoft-produkter uppdateras via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="c68d0-193">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="c68d0-194">Andra prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-194">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="c68d0-195">100.86.91</span><span class="sxs-lookup"><span data-stu-id="c68d0-195">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="c68d0-196">För att säkerställa det mest fullständiga skyddet för dina macOS-enheter och i justeringen med Apple kommer den inbyggda säkerhetsuppdateringen för macOS att stoppas för OS-versioner som är äldre än [nuvarande – 2], MDATP för Mac-distribution och uppdateringar stöds inte längre på macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="c68d0-196">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="c68d0-197">MDATP för Mac-uppdateringar och förbättringar levereras till enheter med versionerna Catalina [10.15], Mojave [10.14] och High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="c68d0-197">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="c68d0-198">Om du redan har MDATP för Mac distribuerat till dina Sierra[10.12]-enheter bör du uppgradera till den senaste macOS-versionen för att undvika risken att förlora skydd.</span><span class="sxs-lookup"><span data-stu-id="c68d0-198">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="c68d0-199">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-199">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="c68d0-200">100.83.73</span><span class="sxs-lookup"><span data-stu-id="c68d0-200">100.83.73</span></span>

- <span data-ttu-id="c68d0-201">Fler kontroller för IT-administratörer har [lagts till för hantering av undantag](mac-preferences.md#exclusion-merge-policy), hantering av [hottypsinställningar](mac-preferences.md#threat-type-settings-merge-policy)och [inte tillagd hotåtgärder](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="c68d0-201">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="c68d0-202">När Fullständig diskåtkomst inte är aktiverat på enheten visas nu en varning i statusmenyn</span><span class="sxs-lookup"><span data-stu-id="c68d0-202">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="c68d0-203">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-203">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="c68d0-204">100.82.60</span><span class="sxs-lookup"><span data-stu-id="c68d0-204">100.82.60</span></span>

- <span data-ttu-id="c68d0-205">Vi har åtgärdat ett problem där produkten inte började följa en definitionsuppdatering.</span><span class="sxs-lookup"><span data-stu-id="c68d0-205">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="c68d0-206">100.80.42</span><span class="sxs-lookup"><span data-stu-id="c68d0-206">100.80.42</span></span>

- <span data-ttu-id="c68d0-207">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-207">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="c68d0-208">100.79.42</span><span class="sxs-lookup"><span data-stu-id="c68d0-208">100.79.42</span></span>

- <span data-ttu-id="c68d0-209">Åtgärdat ett problem där Microsoft Defender för Endpoint för Mac ibland störde Time Machine</span><span class="sxs-lookup"><span data-stu-id="c68d0-209">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="c68d0-210">Lade till en ny växel till kommandoradsverktyget för att testa anslutningen med backendtjänsten</span><span class="sxs-lookup"><span data-stu-id="c68d0-210">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="c68d0-211">Lade till möjligheten att visa den fullständiga hothistoriken i användargränssnittet (kan nås från vyn **Skyddhistorik)**</span><span class="sxs-lookup"><span data-stu-id="c68d0-211">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="c68d0-212">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-212">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="c68d0-213">100.72.15</span><span class="sxs-lookup"><span data-stu-id="c68d0-213">100.72.15</span></span>

- <span data-ttu-id="c68d0-214">Felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-214">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="c68d0-215">100.70.99</span><span class="sxs-lookup"><span data-stu-id="c68d0-215">100.70.99</span></span>

- <span data-ttu-id="c68d0-216">Åtgärdat ett problem som påverkar möjligheten för vissa användare att uppgradera till macOS Catalina när realtidsskydd har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c68d0-216">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="c68d0-217">Det här sporadiska problemet orsakades av Microsoft Defender för att Slutpunktslåsa filer i Catalina-uppgraderingspaket vid genomsökning av dem efter hot, vilket ledde till fel i uppgraderingssekvensen.</span><span class="sxs-lookup"><span data-stu-id="c68d0-217">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="c68d0-218">100.68.99</span><span class="sxs-lookup"><span data-stu-id="c68d0-218">100.68.99</span></span>

- <span data-ttu-id="c68d0-219">Lade till möjligheten att konfigurera antivirusfunktionen för att köras i [passiv form](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c68d0-219">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="c68d0-220">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-220">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="c68d0-221">100.65.28</span><span class="sxs-lookup"><span data-stu-id="c68d0-221">100.65.28</span></span>

- <span data-ttu-id="c68d0-222">Tillagt stöd för macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="c68d0-222">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c68d0-223">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="c68d0-223">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="c68d0-224">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="c68d0-224">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="c68d0-225">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="c68d0-225">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="c68d0-226">Mekanismen för att bevilja detta medgivande beror på hur du har distribuerat Microsoft Defender för Endpoint:</span><span class="sxs-lookup"><span data-stu-id="c68d0-226">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="c68d0-227">För manuell distribution finns de uppdaterade instruktionerna i [avsnittet Om manuell](mac-install-manually.md#how-to-allow-full-disk-access) distribution.</span><span class="sxs-lookup"><span data-stu-id="c68d0-227">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="c68d0-228">För hanterade distributioner, se de uppdaterade instruktionerna i [DEN JAMF-baserade distributionen](mac-install-with-jamf.md) och [i avsnitten om Microsoft Intune-baserad](mac-install-with-intune.md#create-system-configuration-profiles) distribution.</span><span class="sxs-lookup"><span data-stu-id="c68d0-228">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="c68d0-229">Prestandaförbättringar & felkorrigeringar</span><span class="sxs-lookup"><span data-stu-id="c68d0-229">Performance improvements & bug fixes</span></span>