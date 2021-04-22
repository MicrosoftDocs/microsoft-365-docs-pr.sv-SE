---
title: Aktivera regler för minskning av attackytan
description: Aktivera ASR-regler (attack surface reduction) för att skydda dina enheter från attacker som använder makron, skript och vanliga lägre tekniker.
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, aktivera, aktivera
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939248"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="cfc1f-104">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="cfc1f-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cfc1f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfc1f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cfc1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cfc1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfc1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="cfc1f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cfc1f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cfc1f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="cfc1f-110">[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="cfc1f-111">Du kan ange ASR-regler för enheter med någon av följande versioner och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="cfc1f-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cfc1f-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="cfc1f-114">Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="cfc1f-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cfc1f-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="cfc1f-116">**Krav** Du kan ange minskningsregler för attackytan för enheter som kör någon av följande versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-116">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="cfc1f-117">Windows 10 Pro, version 1709 eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-117">Windows 10 Pro, version 1709 or later</span></span>
- <span data-ttu-id="cfc1f-118">Windows 10 Enterprise, version 1709 eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-118">Windows 10 Enterprise, version 1709 or later</span></span>
- <span data-ttu-id="cfc1f-119">Windows Server, version 1803 (Halvårskanal) eller senare</span><span class="sxs-lookup"><span data-stu-id="cfc1f-119">Windows Server, version 1803 (Semi-Annual Channel) or later</span></span>
- <span data-ttu-id="cfc1f-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cfc1f-120">Windows Server 2019</span></span>

<span data-ttu-id="cfc1f-121">Även om minskningsregler för attackytor inte kräver en Windows E5-licens, får du avancerade hanteringsfunktioner om du har Windows E5.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-121">Although attack surface reduction rules don't require a Windows E5 license, if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="cfc1f-122">Dessa funktioner är endast tillgängliga i Windows E5: övervakning, analys och arbetsflöden som är tillgängliga i Defender för Slutpunkt, samt rapporterings- och konfigurationsfunktioner i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-122">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="cfc1f-123">Dessa avancerade funktioner är inte tillgängliga med en Windows Professional- eller Windows E3-licens. Men om du har de licenserna kan du använda Loggboken och Microsoft Defender Antivirus-loggarna för att granska dina minskningsregelhändelser för attackytan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-123">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="cfc1f-124">Varje ASR-regel innehåller en av fyra inställningar:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="cfc1f-125">**Inte konfigurerad:** Inaktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="cfc1f-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="cfc1f-126">**Block:** Aktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="cfc1f-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="cfc1f-127">**Granskning:** Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras</span><span class="sxs-lookup"><span data-stu-id="cfc1f-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="cfc1f-128">**Varna**: Aktivera ASR-regeln men alow slutanvändaren att kringgå blocket</span><span class="sxs-lookup"><span data-stu-id="cfc1f-128">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfc1f-129">För närvarande stöds inte varningsläge för tre ASR-regler när du konfigurerar ASR-regler i Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="cfc1f-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="cfc1f-130">Mer information finns i [Fall där varningsläge inte stöds.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="cfc1f-131">Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktionerna för övervakning och rapportering i [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="cfc1f-131">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="cfc1f-132">Men för andra licenser som Windows Professional eller E3 som inte har tillgång till avancerade funktioner för övervakning och rapportering kan du utveckla dina egna övervaknings- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (t.ex. vidarebefordran av händelse).</span><span class="sxs-lookup"><span data-stu-id="cfc1f-132">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="cfc1f-133">Mer information om Windows-licensiering finns i [Windows 10-licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och volymlicensieringsguiden [för Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="cfc1f-134">Du kan aktivera minskningsregler för attackytan med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="cfc1f-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cfc1f-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="cfc1f-136">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="cfc1f-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cfc1f-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="cfc1f-138">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="cfc1f-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="cfc1f-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfc1f-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="cfc1f-140">Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="cfc1f-141">Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="cfc1f-142">Undanta filer och mappar från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="cfc1f-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="cfc1f-143">Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="cfc1f-144">Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="cfc1f-145">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="cfc1f-146">Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="cfc1f-147">(Se [Hantera indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-147">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfc1f-148">Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="cfc1f-149">Undantagna filer tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="cfc1f-150">Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="cfc1f-151">Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="cfc1f-152">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="cfc1f-153">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="cfc1f-154">ASR-regler stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="cfc1f-155">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="cfc1f-156">Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="cfc1f-157">Intune</span><span class="sxs-lookup"><span data-stu-id="cfc1f-157">Intune</span></span>

1. <span data-ttu-id="cfc1f-158">Välj **Profiler för**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="cfc1f-159">Välj en befintlig profil för slutpunktsskydd eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="cfc1f-160">Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="cfc1f-161">För **Profiltyp** väljer du **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="cfc1f-162">Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="cfc1f-163">I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard och** sedan Attack Surface **Reduction**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="cfc1f-164">Välj önskad inställning för varje ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="cfc1f-165">Ange **enskilda filer och mappar** under Undantag för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="cfc1f-166">Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="cfc1f-167">Varje rad i CSV-filen ska vara formaterad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="cfc1f-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="cfc1f-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="cfc1f-169">Välj **OK** i de tre konfigurationsrutorna.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="cfc1f-170">Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="cfc1f-171">MDM</span><span class="sxs-lookup"><span data-stu-id="cfc1f-171">MDM</span></span>

<span data-ttu-id="cfc1f-172">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-172">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="cfc1f-173">Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-173">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="cfc1f-174">Värdena som du aktiverar (blockera), inaktiverar, varnar eller aktiverar i granskningsläge är:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-174">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="cfc1f-175">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-175">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="cfc1f-176">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-176">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="cfc1f-177">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-177">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="cfc1f-178">6: Varna (aktivera ASR-regeln men tillåt slutanvändaren att kringgå blocket).</span><span class="sxs-lookup"><span data-stu-id="cfc1f-178">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="cfc1f-179">Varningsläge är nu tillgängligt för de flesta ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-179">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="cfc1f-180">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-180">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="cfc1f-181">Exempel:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-181">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="cfc1f-182">Se till att ange OMA-URI-värden utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-182">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="cfc1f-183">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cfc1f-183">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="cfc1f-184">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Slutpunktsskydd för**  >  **efterlevnad** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-184">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="cfc1f-185">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-185">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="cfc1f-186">Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-186">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="cfc1f-187">Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-187">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="cfc1f-188">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-188">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="cfc1f-189">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-189">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="cfc1f-190">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="cfc1f-190">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="cfc1f-191">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-191">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="cfc1f-192">Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-192">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="cfc1f-193">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-193">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="cfc1f-194">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Microsoft Defender  >  **Sårbarhetsskydd-** minskning av  >  **attackytan**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-194">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="cfc1f-195">Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-195">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="cfc1f-196">Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-196">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="cfc1f-197">Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-197">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="cfc1f-198">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-198">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="cfc1f-199">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-199">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="cfc1f-200">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-200">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="cfc1f-201">6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)</span><span class="sxs-lookup"><span data-stu-id="cfc1f-201">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regler i grupprincip":::

5. <span data-ttu-id="cfc1f-203">Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-203">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="cfc1f-204">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-204">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="cfc1f-205">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-205">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="cfc1f-206">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-206">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="cfc1f-207">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfc1f-207">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="cfc1f-208">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-208">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="cfc1f-209">Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-209">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="cfc1f-210">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör.**</span><span class="sxs-lookup"><span data-stu-id="cfc1f-210">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="cfc1f-211">Skriv in följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-211">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="cfc1f-212">Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-212">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="cfc1f-213">Om du vill aktivera ASR-regler i varningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-213">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="cfc1f-214">Om du vill inaktivera ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-214">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="cfc1f-215">Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-215">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="cfc1f-216">I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-216">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="cfc1f-217">Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-217">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="cfc1f-218">`Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-218">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="cfc1f-219">Om du vill lägga till i den befintliga uppsättningen använder du `Add-MpPreference` istället.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-219">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="cfc1f-220">Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="cfc1f-220">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="cfc1f-221">Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cfc1f-221">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="cfc1f-222">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-222">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cfc1f-223">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-223">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="cfc1f-224">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="cfc1f-224">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cfc1f-225">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cfc1f-225">Related articles</span></span>

- [<span data-ttu-id="cfc1f-226">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="cfc1f-226">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="cfc1f-227">Utvärdera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="cfc1f-227">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="cfc1f-228">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="cfc1f-228">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
