---
title: Resurser för Microsoft Defender för Slutpunkt på Mac
description: Resurser för Microsoft Defender för slutpunkt på Mac, inklusive hur du avinstallerar det, hur du samlar in diagnostikloggar, CLI-kommandon och kända problem med produkten.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: fa5d5b4470644e1ff50af46a8dd3f035cd9b3184
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842872"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="54f91-104">Resurser för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="54f91-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54f91-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="54f91-105">**Applies to:**</span></span>

- [<span data-ttu-id="54f91-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="54f91-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54f91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54f91-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="54f91-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="54f91-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54f91-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="54f91-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="54f91-110">Samla in diagnostikinformation</span><span class="sxs-lookup"><span data-stu-id="54f91-110">Collecting diagnostic information</span></span>

<span data-ttu-id="54f91-111">Om du kan återskapa ett problem ökar du loggningsnivån, kör systemet ett tag och återställer loggningsnivån till standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="54f91-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="54f91-112">Öka loggningsnivån:</span><span class="sxs-lookup"><span data-stu-id="54f91-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="54f91-113">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="54f91-113">Reproduce the problem</span></span>

3. <span data-ttu-id="54f91-114">Kör `sudo mdatp diagnostic create` för att backa Microsoft Defender för slutpunktsloggar.</span><span class="sxs-lookup"><span data-stu-id="54f91-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="54f91-115">Filerna lagras i ett .zip arkiv.</span><span class="sxs-lookup"><span data-stu-id="54f91-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="54f91-116">Det här kommandot skriver också ut filsökvägen till säkerhetskopian när åtgärden har lyckats.</span><span class="sxs-lookup"><span data-stu-id="54f91-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="54f91-117">Som standard sparas diagnostikloggar i `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="54f91-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="54f91-118">Om du vill ändra katalogen där diagnostikloggar sparas skickar du `--path [directory]` till kommandot nedan och `[directory]` ersätter med önskad katalog.</span><span class="sxs-lookup"><span data-stu-id="54f91-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="54f91-119">Återställa loggningsnivån:</span><span class="sxs-lookup"><span data-stu-id="54f91-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="54f91-120">Loggningsinstallationsproblem</span><span class="sxs-lookup"><span data-stu-id="54f91-120">Logging installation issues</span></span>

<span data-ttu-id="54f91-121">Om ett fel uppstår under installationen rapporterar installationsprogrammet bara ett allmänt fel.</span><span class="sxs-lookup"><span data-stu-id="54f91-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="54f91-122">Den detaljerade loggen sparas i `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="54f91-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="54f91-123">Om du upplever problem under installationen kan du skicka den här filen till oss så att vi kan hjälpa till att diagnostisera orsaken.</span><span class="sxs-lookup"><span data-stu-id="54f91-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="54f91-124">Avinstallera</span><span class="sxs-lookup"><span data-stu-id="54f91-124">Uninstalling</span></span>

<span data-ttu-id="54f91-125">Det finns flera sätt att avinstallera Microsoft Defender för slutpunkt i macOS.</span><span class="sxs-lookup"><span data-stu-id="54f91-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="54f91-126">Observera att även om det finns centralt hanterad avinstallation på JAMF är det ännu inte tillgängligt för Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="54f91-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="54f91-127">Interaktiv avinstallation</span><span class="sxs-lookup"><span data-stu-id="54f91-127">Interactive uninstallation</span></span>

- <span data-ttu-id="54f91-128">Öppna **Finder > Program**.</span><span class="sxs-lookup"><span data-stu-id="54f91-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="54f91-129">Högerklicka på **Microsoft Defender för slutpunkts-> flytta till papperskorgen**.</span><span class="sxs-lookup"><span data-stu-id="54f91-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="54f91-130">Från kommandoraden</span><span class="sxs-lookup"><span data-stu-id="54f91-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="54f91-131">Konfigurera från kommandoraden</span><span class="sxs-lookup"><span data-stu-id="54f91-131">Configuring from the command line</span></span>

<span data-ttu-id="54f91-132">Viktiga uppgifter, som att kontrollera produktinställningar och utlösa skanningar på begäran, kan utföras från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="54f91-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="54f91-133">Grupp</span><span class="sxs-lookup"><span data-stu-id="54f91-133">Group</span></span>        |<span data-ttu-id="54f91-134">Scenario</span><span class="sxs-lookup"><span data-stu-id="54f91-134">Scenario</span></span>                                   |<span data-ttu-id="54f91-135">Kommando</span><span class="sxs-lookup"><span data-stu-id="54f91-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="54f91-136">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-136">Configuration</span></span>|<span data-ttu-id="54f91-137">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="54f91-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="54f91-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-138">Configuration</span></span>|<span data-ttu-id="54f91-139">Aktivera/inaktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="54f91-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="54f91-140">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-140">Configuration</span></span>|<span data-ttu-id="54f91-141">Aktivera/inaktivera produktdiagnostik</span><span class="sxs-lookup"><span data-stu-id="54f91-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="54f91-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-142">Configuration</span></span>|<span data-ttu-id="54f91-143">Aktivera/inaktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="54f91-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="54f91-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-144">Configuration</span></span>|<span data-ttu-id="54f91-145">Lägga till ett namn på ett hot i listan över tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="54f91-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="54f91-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-146">Configuration</span></span>|<span data-ttu-id="54f91-147">Ta bort ett namn på ett hot från listan över tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="54f91-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="54f91-148">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-148">Configuration</span></span>|<span data-ttu-id="54f91-149">Lista alla tillåtna hotnamn</span><span class="sxs-lookup"><span data-stu-id="54f91-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="54f91-150">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-150">Configuration</span></span>|<span data-ttu-id="54f91-151">Aktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="54f91-152">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-152">Configuration</span></span>|<span data-ttu-id="54f91-153">Inaktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="54f91-154">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-154">Configuration</span></span>|<span data-ttu-id="54f91-155">Aktivera granskningsläge för PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="54f91-156">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="54f91-156">Configuration</span></span>|<span data-ttu-id="54f91-157">Aktivera/inaktivera passivläge</span><span class="sxs-lookup"><span data-stu-id="54f91-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="54f91-158">Diagnostik</span><span class="sxs-lookup"><span data-stu-id="54f91-158">Diagnostics</span></span>  |<span data-ttu-id="54f91-159">Ändra loggnivån</span><span class="sxs-lookup"><span data-stu-id="54f91-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="54f91-160">Diagnostik</span><span class="sxs-lookup"><span data-stu-id="54f91-160">Diagnostics</span></span>  |<span data-ttu-id="54f91-161">Generera diagnostikloggar</span><span class="sxs-lookup"><span data-stu-id="54f91-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="54f91-162">Hälsa</span><span class="sxs-lookup"><span data-stu-id="54f91-162">Health</span></span>       |<span data-ttu-id="54f91-163">Kontrollera produktens hälsa</span><span class="sxs-lookup"><span data-stu-id="54f91-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="54f91-164">Hälsa</span><span class="sxs-lookup"><span data-stu-id="54f91-164">Health</span></span>       |<span data-ttu-id="54f91-165">Söka efter ett spefic produktattribut</span><span class="sxs-lookup"><span data-stu-id="54f91-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="54f91-166">Skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-166">Protection</span></span>   |<span data-ttu-id="54f91-167">Genomsöka en sökväg</span><span class="sxs-lookup"><span data-stu-id="54f91-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="54f91-168">Skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-168">Protection</span></span>   |<span data-ttu-id="54f91-169">Gör en snabbsökning</span><span class="sxs-lookup"><span data-stu-id="54f91-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="54f91-170">Skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-170">Protection</span></span>   |<span data-ttu-id="54f91-171">Gör en fullständig genomsökning</span><span class="sxs-lookup"><span data-stu-id="54f91-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="54f91-172">Skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-172">Protection</span></span>   |<span data-ttu-id="54f91-173">Avbryta en pågående sökning på begäran</span><span class="sxs-lookup"><span data-stu-id="54f91-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="54f91-174">Skydd</span><span class="sxs-lookup"><span data-stu-id="54f91-174">Protection</span></span>   |<span data-ttu-id="54f91-175">Begära en säkerhetsintelligensuppdatering</span><span class="sxs-lookup"><span data-stu-id="54f91-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="54f91-176">Identifiering och åtgärd på slutpunkt</span><span class="sxs-lookup"><span data-stu-id="54f91-176">EDR</span></span>          |<span data-ttu-id="54f91-177">Lägg till grupptagg till enhet.</span><span class="sxs-lookup"><span data-stu-id="54f91-177">Add group tag to device.</span></span> <span data-ttu-id="54f91-178">Identifiering och åtgärd på slutpunkt-taggar används för att hantera enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="54f91-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="54f91-179">Mer information finns på /microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="54f91-179">For more information, please visit /microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="54f91-180">Identifiering och åtgärd på slutpunkt</span><span class="sxs-lookup"><span data-stu-id="54f91-180">EDR</span></span>          |<span data-ttu-id="54f91-181">Ta bort grupptagg från enhet</span><span class="sxs-lookup"><span data-stu-id="54f91-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="54f91-182">Identifiering och åtgärd på slutpunkt</span><span class="sxs-lookup"><span data-stu-id="54f91-182">EDR</span></span>          |<span data-ttu-id="54f91-183">Lägg till grupp-ID</span><span class="sxs-lookup"><span data-stu-id="54f91-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="54f91-184">Så här aktiverar du Komplettera automatiskt</span><span class="sxs-lookup"><span data-stu-id="54f91-184">How to enable autocompletion</span></span>

<span data-ttu-id="54f91-185">Du aktiverar Komplettera automatiskt i bash genom att köra följande kommando och starta om Terminal-sessionen:</span><span class="sxs-lookup"><span data-stu-id="54f91-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="54f91-186">Så här aktiverar du Komplettera automatiskt i zsh:</span><span class="sxs-lookup"><span data-stu-id="54f91-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="54f91-187">Kontrollera om Komplettera automatiskt är aktiverat på enheten:</span><span class="sxs-lookup"><span data-stu-id="54f91-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="54f91-188">Om föregående kommando inte ger några utdata kan du aktivera Komplettera automatiskt med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="54f91-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="54f91-189">Kör följande kommandon för att aktivera automatisk komplettering för Microsoft Defender för slutpunkt på macOS och starta om terminalsessionen:</span><span class="sxs-lookup"><span data-stu-id="54f91-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="54f91-190">Klientkatalogen Microsoft Defender för karantän för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="54f91-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="54f91-191">`/Library/Application Support/Microsoft/Defender/quarantine/` innehåller de filer som har satts i karantän av `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="54f91-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="54f91-192">Filerna namnges efter hotspårnings-ID:t.</span><span class="sxs-lookup"><span data-stu-id="54f91-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="54f91-193">De aktuella uppföljningsid:erna visas med `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="54f91-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="54f91-194">Information om Microsoft Defender för slutpunktsportalen</span><span class="sxs-lookup"><span data-stu-id="54f91-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="54f91-195">[Identifiering och åtgärd på slutpunkt för macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)har nu kommit – på Microsoft Defender för Endpoint-bloggen får du detaljerad vägledning om vad du kan förvänta dig i Microsoft Defender för Endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="54f91-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
