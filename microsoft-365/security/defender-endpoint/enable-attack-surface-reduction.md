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
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689173"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="805d9-104">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="805d9-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="805d9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="805d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="805d9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="805d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="805d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="805d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="805d9-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="805d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="805d9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="805d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="805d9-110">[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk.</span><span class="sxs-lookup"><span data-stu-id="805d9-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="805d9-111">Du kan ange ASR-regler för enheter med någon av följande versioner och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="805d9-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="805d9-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="805d9-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="805d9-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="805d9-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="805d9-114">Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="805d9-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="805d9-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="805d9-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="805d9-116">Varje ASR-regel innehåller en av fyra inställningar:</span><span class="sxs-lookup"><span data-stu-id="805d9-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="805d9-117">**Inte konfigurerad:** Inaktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="805d9-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="805d9-118">**Block:** Aktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="805d9-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="805d9-119">**Granskning:** Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras</span><span class="sxs-lookup"><span data-stu-id="805d9-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="805d9-120">**Varna**: Aktivera ASR-regeln men alow slutanvändaren att kringgå blocket</span><span class="sxs-lookup"><span data-stu-id="805d9-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="805d9-121">För närvarande stöds inte varningsläge för tre ASR-regler när du konfigurerar ASR-regler i Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="805d9-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="805d9-122">Mer information finns i [Fall där varningsläge inte stöds.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="805d9-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="805d9-123">Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktionerna för övervakning och rapportering i [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="805d9-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="805d9-124">Men för andra licenser som Windows Professional eller E3 som inte har tillgång till avancerade funktioner för övervakning och rapportering kan du utveckla dina egna övervaknings- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (t.ex. vidarebefordran av händelse).</span><span class="sxs-lookup"><span data-stu-id="805d9-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="805d9-125">Mer information om Windows-licensiering finns i [Windows 10-licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och volymlicensieringsguiden [för Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="805d9-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="805d9-126">Du kan aktivera minskningsregler för attackytan med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="805d9-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="805d9-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="805d9-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="805d9-128">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="805d9-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="805d9-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="805d9-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="805d9-130">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="805d9-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="805d9-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="805d9-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="805d9-132">Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="805d9-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="805d9-133">Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="805d9-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="805d9-134">Undanta filer och mappar från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="805d9-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="805d9-135">Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="805d9-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="805d9-136">Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="805d9-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="805d9-137">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="805d9-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="805d9-138">Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer.</span><span class="sxs-lookup"><span data-stu-id="805d9-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="805d9-139">(Se [Hantera indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="805d9-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="805d9-140">Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="805d9-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="805d9-141">Undantagna filer tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="805d9-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="805d9-142">Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="805d9-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="805d9-143">Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="805d9-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="805d9-144">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="805d9-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="805d9-145">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="805d9-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="805d9-146">ASR-regler stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="805d9-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="805d9-147">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="805d9-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="805d9-148">Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="805d9-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="805d9-149">Intune</span><span class="sxs-lookup"><span data-stu-id="805d9-149">Intune</span></span>

1. <span data-ttu-id="805d9-150">Välj **Profiler för**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="805d9-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="805d9-151">Välj en befintlig profil för slutpunktsskydd eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="805d9-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="805d9-152">Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen.</span><span class="sxs-lookup"><span data-stu-id="805d9-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="805d9-153">För **Profiltyp** väljer du **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="805d9-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="805d9-154">Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="805d9-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="805d9-155">I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard och** sedan Attack Surface **Reduction**.</span><span class="sxs-lookup"><span data-stu-id="805d9-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="805d9-156">Välj önskad inställning för varje ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="805d9-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="805d9-157">Ange **enskilda filer och mappar** under Undantag för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="805d9-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="805d9-158">Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="805d9-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="805d9-159">Varje rad i CSV-filen ska vara formaterad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="805d9-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="805d9-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="805d9-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="805d9-161">Välj **OK** i de tre konfigurationsrutorna.</span><span class="sxs-lookup"><span data-stu-id="805d9-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="805d9-162">Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.</span><span class="sxs-lookup"><span data-stu-id="805d9-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="805d9-163">MDM</span><span class="sxs-lookup"><span data-stu-id="805d9-163">MDM</span></span>

<span data-ttu-id="805d9-164">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.</span><span class="sxs-lookup"><span data-stu-id="805d9-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="805d9-165">Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="805d9-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="805d9-166">Värdena som du aktiverar (blockera), inaktiverar, varnar eller aktiverar i granskningsläge är:</span><span class="sxs-lookup"><span data-stu-id="805d9-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="805d9-167">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="805d9-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="805d9-168">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="805d9-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="805d9-169">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="805d9-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="805d9-170">6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)</span><span class="sxs-lookup"><span data-stu-id="805d9-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="805d9-171">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="805d9-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="805d9-172">Exempel:</span><span class="sxs-lookup"><span data-stu-id="805d9-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="805d9-173">Se till att ange OMA-URI-värden utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="805d9-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="805d9-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="805d9-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="805d9-175">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Slutpunktsskydd för**  >  **efterlevnad** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="805d9-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="805d9-176">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="805d9-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="805d9-177">Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="805d9-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="805d9-178">Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="805d9-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="805d9-179">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="805d9-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="805d9-180">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="805d9-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="805d9-181">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="805d9-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="805d9-182">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="805d9-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="805d9-183">Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="805d9-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="805d9-184">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="805d9-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="805d9-185">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Microsoft Defender  >  **Sårbarhetsskydd-** minskning av  >  **attackytan**.</span><span class="sxs-lookup"><span data-stu-id="805d9-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="805d9-186">Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="805d9-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="805d9-187">Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.</span><span class="sxs-lookup"><span data-stu-id="805d9-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="805d9-188">Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="805d9-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="805d9-189">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="805d9-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="805d9-190">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="805d9-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="805d9-191">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="805d9-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="805d9-192">6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)</span><span class="sxs-lookup"><span data-stu-id="805d9-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regler i grupprincip":::

5. <span data-ttu-id="805d9-194">Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="805d9-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="805d9-195">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="805d9-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="805d9-196">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="805d9-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="805d9-197">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="805d9-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="805d9-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="805d9-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="805d9-199">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start.</span><span class="sxs-lookup"><span data-stu-id="805d9-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="805d9-200">Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.</span><span class="sxs-lookup"><span data-stu-id="805d9-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="805d9-201">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör.**</span><span class="sxs-lookup"><span data-stu-id="805d9-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="805d9-202">Skriv in följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="805d9-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="805d9-203">Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="805d9-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="805d9-204">Om du vill aktivera ASR-regler i varningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="805d9-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="805d9-205">Om du vill inaktivera ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="805d9-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="805d9-206">Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.</span><span class="sxs-lookup"><span data-stu-id="805d9-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="805d9-207">I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="805d9-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="805d9-208">Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="805d9-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="805d9-209">`Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler.</span><span class="sxs-lookup"><span data-stu-id="805d9-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="805d9-210">Om du vill lägga till i den befintliga uppsättningen använder du `Add-MpPreference` istället.</span><span class="sxs-lookup"><span data-stu-id="805d9-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="805d9-211">Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="805d9-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="805d9-212">Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="805d9-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="805d9-213">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="805d9-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="805d9-214">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="805d9-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="805d9-215">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="805d9-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="805d9-216">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="805d9-216">Related articles</span></span>

- [<span data-ttu-id="805d9-217">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="805d9-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="805d9-218">Utvärdera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="805d9-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="805d9-219">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="805d9-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
