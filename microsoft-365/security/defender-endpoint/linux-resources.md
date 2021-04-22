---
title: Microsoft Defender för Slutpunkt på Linux-resurser
ms.reviewer: ''
description: Här beskrivs resurser för Microsoft Defender för Slutpunkt i Linux, inklusive hur du avinstallerar det, hur du samlar in diagnostikloggar, CLI-kommandon och kända problem med produkten.
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
ms.openlocfilehash: 176ee89c8d60a1515855296e2565f0649f908a33
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933331"
---
# <a name="resources"></a><span data-ttu-id="ef809-104">Resurser</span><span class="sxs-lookup"><span data-stu-id="ef809-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ef809-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ef809-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef809-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef809-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef809-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef809-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef809-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ef809-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ef809-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ef809-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="ef809-110">Samla in diagnostikinformation</span><span class="sxs-lookup"><span data-stu-id="ef809-110">Collect diagnostic information</span></span>

<span data-ttu-id="ef809-111">Om du kan återskapa ett problem ökar du först loggningsnivån, kör systemet ett tag och återställer sedan loggningsnivån till standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="ef809-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="ef809-112">Öka loggningsnivån:</span><span class="sxs-lookup"><span data-stu-id="ef809-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="ef809-113">Återskapa problemet.</span><span class="sxs-lookup"><span data-stu-id="ef809-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="ef809-114">Kör följande kommando för att backa upp Defender för Endpoints loggar.</span><span class="sxs-lookup"><span data-stu-id="ef809-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="ef809-115">Filerna lagras i ett ZIP-arkiv.</span><span class="sxs-lookup"><span data-stu-id="ef809-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="ef809-116">Det här kommandot skriver också ut filsökvägen till säkerhetskopian när åtgärden har lyckats:</span><span class="sxs-lookup"><span data-stu-id="ef809-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="ef809-117">Återställa loggningsnivån:</span><span class="sxs-lookup"><span data-stu-id="ef809-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="ef809-118">Logga installationsproblem</span><span class="sxs-lookup"><span data-stu-id="ef809-118">Log installation issues</span></span>

<span data-ttu-id="ef809-119">Om ett fel uppstår under installationen rapporterar installationsprogrammet bara ett allmänt fel.</span><span class="sxs-lookup"><span data-stu-id="ef809-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="ef809-120">Den detaljerade loggen sparas i `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="ef809-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="ef809-121">Om du upplever problem under installationen kan du skicka den här filen till oss så att vi kan hjälpa till att diagnostisera orsaken.</span><span class="sxs-lookup"><span data-stu-id="ef809-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="ef809-122">Avinstallera</span><span class="sxs-lookup"><span data-stu-id="ef809-122">Uninstall</span></span>

<span data-ttu-id="ef809-123">Det finns flera sätt att avinstallera Defender för Endpoint i Linux.</span><span class="sxs-lookup"><span data-stu-id="ef809-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="ef809-124">Om du använder ett konfigurationsverktyg, till exempel Beser, följer du paketinstallationsanvisningarna för konfigurationsverktyget.</span><span class="sxs-lookup"><span data-stu-id="ef809-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="ef809-125">Manuell avinstallation</span><span class="sxs-lookup"><span data-stu-id="ef809-125">Manual uninstallation</span></span>

- <span data-ttu-id="ef809-126">`sudo yum remove mdatp` för RHEL och varianter(CentOS och Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="ef809-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="ef809-127">`sudo zypper remove mdatp` för SLES och varianter.</span><span class="sxs-lookup"><span data-stu-id="ef809-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="ef809-128">`sudo apt-get purge mdatp` för Ubuntu och Ubuntu systems.</span><span class="sxs-lookup"><span data-stu-id="ef809-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="ef809-129">Konfigurera från kommandoraden</span><span class="sxs-lookup"><span data-stu-id="ef809-129">Configure from the command line</span></span>

<span data-ttu-id="ef809-130">Viktiga uppgifter, som att kontrollera produktinställningar och utlösa skanningar på begäran, kan utföras från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="ef809-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="ef809-131">Globala alternativ</span><span class="sxs-lookup"><span data-stu-id="ef809-131">Global options</span></span>

<span data-ttu-id="ef809-132">Som standard matar kommandoradsverktyget ut resultatet i läsbart format.</span><span class="sxs-lookup"><span data-stu-id="ef809-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="ef809-133">Dessutom har verktyget stöd för att mata ut resultatet som JSON, vilket är användbart för automatiseringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="ef809-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="ef809-134">Om du vill ändra utdata till JSON skickar `--output json` du till något av kommandona nedan.</span><span class="sxs-lookup"><span data-stu-id="ef809-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="ef809-135">Kommandon som stöds</span><span class="sxs-lookup"><span data-stu-id="ef809-135">Supported commands</span></span>

<span data-ttu-id="ef809-136">I följande tabell visas kommandon för några av de vanligaste scenarierna.</span><span class="sxs-lookup"><span data-stu-id="ef809-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="ef809-137">Kör `mdatp help` från Terminalen för att visa en fullständig lista över kommandon som stöds.</span><span class="sxs-lookup"><span data-stu-id="ef809-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="ef809-138">Grupp</span><span class="sxs-lookup"><span data-stu-id="ef809-138">Group</span></span>                 |<span data-ttu-id="ef809-139">Scenario</span><span class="sxs-lookup"><span data-stu-id="ef809-139">Scenario</span></span>                                                |<span data-ttu-id="ef809-140">Kommando</span><span class="sxs-lookup"><span data-stu-id="ef809-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="ef809-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-141">Configuration</span></span>         |<span data-ttu-id="ef809-142">Aktivera/inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="ef809-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="ef809-143">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-143">Configuration</span></span>         |<span data-ttu-id="ef809-144">Aktivera/inaktivera beteendeövervakning</span><span class="sxs-lookup"><span data-stu-id="ef809-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="ef809-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-145">Configuration</span></span>         |<span data-ttu-id="ef809-146">Aktivera/inaktivera molnskydd</span><span class="sxs-lookup"><span data-stu-id="ef809-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="ef809-147">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-147">Configuration</span></span>         |<span data-ttu-id="ef809-148">Aktivera/inaktivera produktdiagnostik</span><span class="sxs-lookup"><span data-stu-id="ef809-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="ef809-149">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-149">Configuration</span></span>         |<span data-ttu-id="ef809-150">Aktivera/inaktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="ef809-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="ef809-151">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-151">Configuration</span></span>         |<span data-ttu-id="ef809-152">Aktivera/inaktivera AV-passivt läge</span><span class="sxs-lookup"><span data-stu-id="ef809-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="ef809-153">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-153">Configuration</span></span>         |<span data-ttu-id="ef809-154">Lägga till/ta bort ett antivirusskydd för ett filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="ef809-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="ef809-155">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-155">Configuration</span></span>         |<span data-ttu-id="ef809-156">Lägga till/ta bort ett antivirusskydd för en fil</span><span class="sxs-lookup"><span data-stu-id="ef809-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="ef809-157">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-157">Configuration</span></span>         |<span data-ttu-id="ef809-158">Lägga till/ta bort ett antivirusskydd för en katalog</span><span class="sxs-lookup"><span data-stu-id="ef809-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="ef809-159">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-159">Configuration</span></span>         |<span data-ttu-id="ef809-160">Lägga till/ta bort ett antivirusskydd för en process</span><span class="sxs-lookup"><span data-stu-id="ef809-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="ef809-161">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-161">Configuration</span></span>         |<span data-ttu-id="ef809-162">Lista alla undantag för antivirus</span><span class="sxs-lookup"><span data-stu-id="ef809-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="ef809-163">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-163">Configuration</span></span>         |<span data-ttu-id="ef809-164">Lägga till ett namn på ett hot i listan över tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="ef809-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="ef809-165">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-165">Configuration</span></span>         |<span data-ttu-id="ef809-166">Ta bort ett namn på ett hot från listan över tillåtna hot</span><span class="sxs-lookup"><span data-stu-id="ef809-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="ef809-167">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-167">Configuration</span></span>         |<span data-ttu-id="ef809-168">Lista alla tillåtna hotnamn</span><span class="sxs-lookup"><span data-stu-id="ef809-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="ef809-169">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-169">Configuration</span></span>         |<span data-ttu-id="ef809-170">Aktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="ef809-171">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-171">Configuration</span></span>         |<span data-ttu-id="ef809-172">Inaktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="ef809-173">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ef809-173">Configuration</span></span>         |<span data-ttu-id="ef809-174">Aktivera granskningsläge för PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="ef809-175">Diagnostik</span><span class="sxs-lookup"><span data-stu-id="ef809-175">Diagnostics</span></span>           |<span data-ttu-id="ef809-176">Ändra loggnivån</span><span class="sxs-lookup"><span data-stu-id="ef809-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="ef809-177">Diagnostik</span><span class="sxs-lookup"><span data-stu-id="ef809-177">Diagnostics</span></span>           |<span data-ttu-id="ef809-178">Generera diagnostikloggar</span><span class="sxs-lookup"><span data-stu-id="ef809-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="ef809-179">Hälsa</span><span class="sxs-lookup"><span data-stu-id="ef809-179">Health</span></span>                |<span data-ttu-id="ef809-180">Kontrollera produktens hälsa</span><span class="sxs-lookup"><span data-stu-id="ef809-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="ef809-181">Skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-181">Protection</span></span>            |<span data-ttu-id="ef809-182">Genomsöka en sökväg</span><span class="sxs-lookup"><span data-stu-id="ef809-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="ef809-183">Skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-183">Protection</span></span>            |<span data-ttu-id="ef809-184">Gör en snabbsökning</span><span class="sxs-lookup"><span data-stu-id="ef809-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="ef809-185">Skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-185">Protection</span></span>            |<span data-ttu-id="ef809-186">Gör en fullständig genomsökning</span><span class="sxs-lookup"><span data-stu-id="ef809-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="ef809-187">Skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-187">Protection</span></span>            |<span data-ttu-id="ef809-188">Avbryta en pågående sökning på begäran</span><span class="sxs-lookup"><span data-stu-id="ef809-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="ef809-189">Skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-189">Protection</span></span>            |<span data-ttu-id="ef809-190">Begära en säkerhetsintelligensuppdatering</span><span class="sxs-lookup"><span data-stu-id="ef809-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="ef809-191">Skyddshistorik</span><span class="sxs-lookup"><span data-stu-id="ef809-191">Protection history</span></span>    |<span data-ttu-id="ef809-192">Skriva ut hela historiken för skydd</span><span class="sxs-lookup"><span data-stu-id="ef809-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="ef809-193">Skyddshistorik</span><span class="sxs-lookup"><span data-stu-id="ef809-193">Protection history</span></span>    |<span data-ttu-id="ef809-194">Hämta information om hot</span><span class="sxs-lookup"><span data-stu-id="ef809-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="ef809-195">Hantering av karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-195">Quarantine management</span></span> |<span data-ttu-id="ef809-196">Lista alla filer i karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="ef809-197">Hantering av karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-197">Quarantine management</span></span> |<span data-ttu-id="ef809-198">Ta bort alla filer från karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="ef809-199">Hantering av karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-199">Quarantine management</span></span> |<span data-ttu-id="ef809-200">Lägga till en fil som upptäckts som ett hot i karantänen</span><span class="sxs-lookup"><span data-stu-id="ef809-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="ef809-201">Hantering av karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-201">Quarantine management</span></span> |<span data-ttu-id="ef809-202">Ta bort en fil som upptäckts som ett hot från karantänen</span><span class="sxs-lookup"><span data-stu-id="ef809-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="ef809-203">Hantering av karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-203">Quarantine management</span></span> |<span data-ttu-id="ef809-204">Återställa en fil från karantän</span><span class="sxs-lookup"><span data-stu-id="ef809-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="ef809-205">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="ef809-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="ef809-206">Ange tidig förhandsgranskning (oanvänd)</span><span class="sxs-lookup"><span data-stu-id="ef809-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="ef809-207">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="ef809-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="ef809-208">Ange grupp-ID</span><span class="sxs-lookup"><span data-stu-id="ef809-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="ef809-209">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="ef809-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="ef809-210">Ange/ta bort tagg, stöds `GROUP` endast</span><span class="sxs-lookup"><span data-stu-id="ef809-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="ef809-211">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="ef809-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="ef809-212">Undantag för listor (rot)</span><span class="sxs-lookup"><span data-stu-id="ef809-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="ef809-213">Information om Microsoft Defender för slutpunktsportalen</span><span class="sxs-lookup"><span data-stu-id="ef809-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="ef809-214">I Defender för slutpunktsportalen visas två kategorier med information:</span><span class="sxs-lookup"><span data-stu-id="ef809-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="ef809-215">Antivirusvarningar, inklusive:</span><span class="sxs-lookup"><span data-stu-id="ef809-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="ef809-216">Allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="ef809-216">Severity</span></span>
  - <span data-ttu-id="ef809-217">Skanningstyp</span><span class="sxs-lookup"><span data-stu-id="ef809-217">Scan type</span></span>
  - <span data-ttu-id="ef809-218">Enhetsinformation (värdnamn, enhetsidentifierare, klientorganisationsidentifierare, appversion och OS-typ)</span><span class="sxs-lookup"><span data-stu-id="ef809-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="ef809-219">Filinformation (namn, sökväg, storlek och hash)</span><span class="sxs-lookup"><span data-stu-id="ef809-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="ef809-220">Hotinformation (namn, typ och delstat)</span><span class="sxs-lookup"><span data-stu-id="ef809-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="ef809-221">Enhetsinformation, inklusive:</span><span class="sxs-lookup"><span data-stu-id="ef809-221">Device information, including:</span></span>
  - <span data-ttu-id="ef809-222">Enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="ef809-222">Device identifier</span></span>
  - <span data-ttu-id="ef809-223">Klientorganisationsidentifierare</span><span class="sxs-lookup"><span data-stu-id="ef809-223">Tenant identifier</span></span>
  - <span data-ttu-id="ef809-224">Appversion</span><span class="sxs-lookup"><span data-stu-id="ef809-224">App version</span></span>
  - <span data-ttu-id="ef809-225">Hostname</span><span class="sxs-lookup"><span data-stu-id="ef809-225">Hostname</span></span>
  - <span data-ttu-id="ef809-226">OS-typ</span><span class="sxs-lookup"><span data-stu-id="ef809-226">OS type</span></span>
  - <span data-ttu-id="ef809-227">OS-version</span><span class="sxs-lookup"><span data-stu-id="ef809-227">OS version</span></span>
  - <span data-ttu-id="ef809-228">Datormodell</span><span class="sxs-lookup"><span data-stu-id="ef809-228">Computer model</span></span>
  - <span data-ttu-id="ef809-229">Processorarkitektur</span><span class="sxs-lookup"><span data-stu-id="ef809-229">Processor architecture</span></span>
  - <span data-ttu-id="ef809-230">Om enheten är en virtuell dator</span><span class="sxs-lookup"><span data-stu-id="ef809-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="ef809-231">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ef809-231">Known issues</span></span>

- <span data-ttu-id="ef809-232">"Inga sensordata, nedsatt kommunikation" visas på sidan med maskininformation på Microsoft Defender Säkerhetscenter-portalen, trots att produkten fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="ef809-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="ef809-233">Vi arbetar med att lösa det här problemet.</span><span class="sxs-lookup"><span data-stu-id="ef809-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="ef809-234">Inloggade användare visas inte i Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="ef809-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="ef809-235">Om installationen av *libmic1* misslyckas i SUSE-distributionsfördelningar bör du kontrollera att operativsystemet är registrerat:</span><span class="sxs-lookup"><span data-stu-id="ef809-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
