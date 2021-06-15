---
title: Felsök Microsoft Defender Antivirus när du migrerar från en lösning från tredje part
description: Felsöka vanliga fel vid migrering till Microsoft Defender Antivirus
keywords: händelse, felkod, loggning, felsökning, microsoft defender antivirus, windows defender antivirus, migrering
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924389"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="946da-104">Felsök Microsoft Defender Antivirus när du migrerar från en lösning från tredje part</span><span class="sxs-lookup"><span data-stu-id="946da-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="946da-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="946da-105">**Applies to:**</span></span>

- [<span data-ttu-id="946da-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="946da-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="946da-107">Du hittar hjälp här om du stöter på problem när du migrerar från en säkerhetslösning från tredje part till Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="946da-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="946da-108">Granska händelseloggar</span><span class="sxs-lookup"><span data-stu-id="946da-108">Review event logs</span></span>

<span data-ttu-id="946da-109">Öppna appen Loggboken genom att välja **sökikonen** i Aktivitetsfältet och söka efter *loggboken*.</span><span class="sxs-lookup"><span data-stu-id="946da-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="946da-110">Information om Microsoft Defender Antivirus finns under **Program- och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="946da-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="946da-111">Därifrån väljer du **Öppna** under **Drift**.</span><span class="sxs-lookup"><span data-stu-id="946da-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="946da-112">Om du väljer en händelse i informationsfönstret visas mer information om en händelse i det nedre fönstret, under **flikarna Allmänt** **och** Information.</span><span class="sxs-lookup"><span data-stu-id="946da-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="946da-113">Microsoft Defender Antivirus startar inte</span><span class="sxs-lookup"><span data-stu-id="946da-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="946da-114">Det här problemet kan visa sig i form av flera olika händelse-ID, som alla har samma underliggande orsak.</span><span class="sxs-lookup"><span data-stu-id="946da-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="946da-115">Associerade händelse-ID</span><span class="sxs-lookup"><span data-stu-id="946da-115">Associated event IDs</span></span>

 <span data-ttu-id="946da-116">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="946da-116">Event ID</span></span> | <span data-ttu-id="946da-117">Loggnamn</span><span class="sxs-lookup"><span data-stu-id="946da-117">Log name</span></span> | <span data-ttu-id="946da-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="946da-118">Description</span></span> | <span data-ttu-id="946da-119">Source</span><span class="sxs-lookup"><span data-stu-id="946da-119">Source</span></span>
-|-|-|-
<span data-ttu-id="946da-120">15</span><span class="sxs-lookup"><span data-stu-id="946da-120">15</span></span> | <span data-ttu-id="946da-121">Program</span><span class="sxs-lookup"><span data-stu-id="946da-121">Application</span></span> | <span data-ttu-id="946da-122">Uppdaterade Windows Defender statusen för att SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="946da-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="946da-123">Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="946da-123">Security Center</span></span>
<span data-ttu-id="946da-124">5007</span><span class="sxs-lookup"><span data-stu-id="946da-124">5007</span></span> | <span data-ttu-id="946da-125">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="946da-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="946da-126">Windows Defender Antivirus Konfigurationen har ändrats.</span><span class="sxs-lookup"><span data-stu-id="946da-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="946da-127">Om det är en oväntad händelse bör du granska inställningarna eftersom det kan vara resultatet av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="946da-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="946da-128">**Gammalt värde:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="946da-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="946da-129">**Nytt värde:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="946da-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="946da-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="946da-130">Windows Defender</span></span>
<span data-ttu-id="946da-131">5010</span><span class="sxs-lookup"><span data-stu-id="946da-131">5010</span></span> | <span data-ttu-id="946da-132">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="946da-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="946da-133">Windows Defender Antivirus för spionprogram och annan potentiellt oönskad programvara inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="946da-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="946da-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="946da-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="946da-135">Så här ser du Microsoft Defender Antivirus antivirusprogrammet inte startar eftersom ett antivirusprogram från tredje part är installerat</span><span class="sxs-lookup"><span data-stu-id="946da-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="946da-136">Om du Windows 10 Microsoft Defender för Endpoint på en Windows 10 enhet och du har ett antivirus installerat från tredje part inaktiveras Microsoft Defender Antivirus automatiskt.</span><span class="sxs-lookup"><span data-stu-id="946da-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="946da-137">Om du använder Microsoft Defender för Endpoint med ett antivirus installerat från tredje Microsoft Defender Antivirus att starta i passiv form, med nedsatt funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="946da-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="946da-138">Det scenario som beskrivs ovan gäller endast för Windows 10.</span><span class="sxs-lookup"><span data-stu-id="946da-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="946da-139">Andra versioner av Windows har [olika svar på](microsoft-defender-antivirus-compatibility.md) Microsoft Defender Antivirus som körs tillsammans med säkerhetsprogramvara från tredje part.</span><span class="sxs-lookup"><span data-stu-id="946da-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="946da-140">Använda appen Tjänster för att kontrollera Microsoft Defender Antivirus är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="946da-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="946da-141">Öppna appen Tjänster genom att välja **sökikonen** i Aktivitetsfältet och söka efter *tjänster.*</span><span class="sxs-lookup"><span data-stu-id="946da-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="946da-142">Du kan också öppna appen från kommandoraden genom att skriva *services.msc.*</span><span class="sxs-lookup"><span data-stu-id="946da-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="946da-143">Information om Microsoft Defender Antivirus listas i services-appen under **drift Windows Defender**  >  **Drift.**</span><span class="sxs-lookup"><span data-stu-id="946da-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="946da-144">Antivirustjänstens namn är *Windows Defender Antivirus tjänsten.*</span><span class="sxs-lookup"><span data-stu-id="946da-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="946da-145">När du kontrollerar appen kan det hända att *Windows Defender Antivirus-tjänsten* är inställd på manuell , men när du försöker starta den här tjänsten manuellt får du ett varningsmeddelande om att Windows Defender Antivirus-tjänsten på den lokala datorn har startats och *stoppats. Vissa tjänster stoppas automatiskt om de inte används av andra tjänster eller program.*</span><span class="sxs-lookup"><span data-stu-id="946da-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="946da-146">Det innebär att Microsoft Defender Antivirus har inaktiverats automatiskt för att bevara kompatibiliteten med ett antivirusprogram från tredje part.</span><span class="sxs-lookup"><span data-stu-id="946da-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="946da-147">Skapa en detaljerad rapport</span><span class="sxs-lookup"><span data-stu-id="946da-147">Generate a detailed report</span></span>

<span data-ttu-id="946da-148">Du kan generera en detaljerad rapport om för närvarande  aktiva gruppprinciper genom att öppna en kommandotolk i läget Kör som administratör och sedan ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="946da-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="946da-149">En rapport som finns på *./gpresult.html* skapas.</span><span class="sxs-lookup"><span data-stu-id="946da-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="946da-150">Öppna den här filen så kan du se följande resultat, beroende på hur Microsoft Defender Antivirus var inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="946da-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="946da-151">Grupprincipresultat</span><span class="sxs-lookup"><span data-stu-id="946da-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="946da-152">Om säkerhetsinställningarna implementeras via grupprincip (GPO) på domännivå eller lokal nivå, eller via System Center Configuration Manager (SCCM)</span><span class="sxs-lookup"><span data-stu-id="946da-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="946da-153">I gpResults-rapporten, under rubriken *Windows Components/Windows Defender Antivirus,* kanske du ser något i enlighet med följande post, som anger att Microsoft Defender Antivirus är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="946da-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="946da-154">Princip</span><span class="sxs-lookup"><span data-stu-id="946da-154">Policy</span></span> | <span data-ttu-id="946da-155">Inställning</span><span class="sxs-lookup"><span data-stu-id="946da-155">Setting</span></span> | <span data-ttu-id="946da-156">Vinnande GPO</span><span class="sxs-lookup"><span data-stu-id="946da-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="946da-157">Inaktivera Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="946da-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="946da-158">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="946da-158">Enabled</span></span> | <span data-ttu-id="946da-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="946da-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="946da-160">Om säkerhetsinställningarna implementeras via grupprincipinställning (GPP)</span><span class="sxs-lookup"><span data-stu-id="946da-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="946da-161">Under rubriken Registerobjekt *(Nyckelsökväg: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Värdenamn: DisableAntiSpyware)* kan det se ut ungefär så här, som visar att Microsoft Defender Antivirus är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="946da-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="946da-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="946da-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="946da-163">Vinnande GPO</span><span class="sxs-lookup"><span data-stu-id="946da-163">Winning GPO</span></span> | <span data-ttu-id="946da-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="946da-164">Win10-Workstations</span></span>
<span data-ttu-id="946da-165">Resultat: Lyckades</span><span class="sxs-lookup"><span data-stu-id="946da-165">Result: Success</span></span> | 
<span data-ttu-id="946da-166">**Allmänt**</span><span class="sxs-lookup"><span data-stu-id="946da-166">**General**</span></span> | 
<span data-ttu-id="946da-167">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="946da-167">Action</span></span> | <span data-ttu-id="946da-168">Update</span><span class="sxs-lookup"><span data-stu-id="946da-168">Update</span></span>
<span data-ttu-id="946da-169">**Egenskaper**</span><span class="sxs-lookup"><span data-stu-id="946da-169">**Properties**</span></span> | 
<span data-ttu-id="946da-170">Registreringsdatafil</span><span class="sxs-lookup"><span data-stu-id="946da-170">Hive</span></span> | <span data-ttu-id="946da-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="946da-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="946da-172">Nyckelsökväg</span><span class="sxs-lookup"><span data-stu-id="946da-172">Key path</span></span> | <span data-ttu-id="946da-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="946da-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="946da-174">Värdenamn</span><span class="sxs-lookup"><span data-stu-id="946da-174">Value name</span></span> | <span data-ttu-id="946da-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="946da-175">DisableAntiSpyware</span></span>
<span data-ttu-id="946da-176">Värdetyp</span><span class="sxs-lookup"><span data-stu-id="946da-176">Value type</span></span> | <span data-ttu-id="946da-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="946da-177">REG_DWORD</span></span>
<span data-ttu-id="946da-178">Värdedata</span><span class="sxs-lookup"><span data-stu-id="946da-178">Value data</span></span> | <span data-ttu-id="946da-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="946da-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="946da-180">Om säkerhetsinställningarna implementeras via registernyckeln</span><span class="sxs-lookup"><span data-stu-id="946da-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="946da-181">Rapporten kan innehålla följande text, som anger att Microsoft Defender Antivirus är inaktiverat:</span><span class="sxs-lookup"><span data-stu-id="946da-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="946da-182">Register (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="946da-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="946da-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span><span class="sxs-lookup"><span data-stu-id="946da-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="946da-184">Om säkerhetsinställningarna anges i Windows eller i Windows Serveravbildningen</span><span class="sxs-lookup"><span data-stu-id="946da-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="946da-185">Den imaginära administratören kan ha angett säkerhetsprincipen **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, lokalt via *GPEdit.exe*, *LGPO.exe* eller genom att ändra registret i aktivitetssekvensen.</span><span class="sxs-lookup"><span data-stu-id="946da-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="946da-186">Du kan [konfigurera en betrodd bildidentifierare](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="946da-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="946da-187">Aktivera Microsoft Defender Antivirus igen</span><span class="sxs-lookup"><span data-stu-id="946da-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="946da-188">Microsoft Defender Antivirus att aktiveras automatiskt om inget annat antivirusprogram är aktivt.</span><span class="sxs-lookup"><span data-stu-id="946da-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="946da-189">Du måste inaktivera antivirusprogrammet från tredje part helt för att säkerställa att Microsoft Defender Antivirus kan köras med fullständiga funktioner.</span><span class="sxs-lookup"><span data-stu-id="946da-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="946da-190">Lösningar som föreslår  att du redigerar Windows Defender-startvärdena för *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* och *windefend* i HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services stöds inte och kan tvinga dig att avbildninga systemet igen.</span><span class="sxs-lookup"><span data-stu-id="946da-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="946da-191">Passiv form är tillgängligt om du börjar använda Microsoft Defender för Endpoint och ett antivirus från tredje part tillsammans med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="946da-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="946da-192">Med passivt läge kan Microsoft Defender söka igenom filer och uppdatera sig själv, men det åtgärdar inte hot.</span><span class="sxs-lookup"><span data-stu-id="946da-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="946da-193">Dessutom är inte övervakning av beteende via [realtidsskydd](configure-real-time-protection-microsoft-defender-antivirus.md) tillgängligt under passivt läge, om inte [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="946da-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="946da-194">En annan funktion, som [kallas begränsad regelbunden](limited-periodic-scanning-microsoft-defender-antivirus.md)genomsökning, är tillgänglig för slutanvändare när Microsoft Defender Antivirus är inställd på att inaktiveras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="946da-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="946da-195">Med den här Microsoft Defender Antivirus du söka igenom filer regelbundet tillsammans med ett antivirusprogram från tredje part med ett begränsat antal identifieringar.</span><span class="sxs-lookup"><span data-stu-id="946da-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="946da-196">Begränsad regelbunden genomsökning rekommenderas inte i företagsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="946da-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="946da-197">De funktioner för identifiering, hantering och rapportering som är tillgängliga när Microsoft Defender Antivirus i det här läget minskar jämfört med aktivt läge.</span><span class="sxs-lookup"><span data-stu-id="946da-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="946da-198">Se även</span><span class="sxs-lookup"><span data-stu-id="946da-198">See also</span></span>

* [<span data-ttu-id="946da-199">Microsoft Defender Antivirus kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="946da-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="946da-200">Microsoft Defender Antivirus i Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="946da-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)