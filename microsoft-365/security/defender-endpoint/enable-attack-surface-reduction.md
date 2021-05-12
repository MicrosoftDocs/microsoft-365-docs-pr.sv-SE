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
ms.openlocfilehash: fc04db0c9fe8ee6d09efc9802ab4a747af0b3e9c
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326703"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="576cd-104">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="576cd-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="576cd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="576cd-105">**Applies to:**</span></span>

- [<span data-ttu-id="576cd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="576cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="576cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="576cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="576cd-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="576cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="576cd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="576cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="576cd-110">[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk.</span><span class="sxs-lookup"><span data-stu-id="576cd-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="576cd-111">**Krav** Du kan ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="576cd-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="576cd-112">Windows 10 Pro, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="576cd-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="576cd-113">Windows 10 Enterprise, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="576cd-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="576cd-114">Windows Server, [version 1803 (Halvårskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="576cd-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="576cd-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="576cd-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="576cd-116">Även om minskningsregler för attackytan inte kräver en [E5 Windows-licens,](/windows/deployment/deploy-enterprise-licenses)får du avancerade hanteringsfunktioner om du har Windows E5.</span><span class="sxs-lookup"><span data-stu-id="576cd-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="576cd-117">De här funktionerna är endast tillgängliga i Windows E5: övervakning, analys och arbetsflöden som är tillgängliga i Defender för [slutpunkt,](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)samt rapporterings- och konfigurationsfunktioner [i Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="576cd-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="576cd-118">Dessa avancerade funktioner är inte tillgängliga med en licens från Windows Professional eller Windows E3. Men om du har dessa licenser kan du använda Loggboken och Microsoft Defender Antivirus för att granska dina attack surface-minskningsregelhändelser.</span><span class="sxs-lookup"><span data-stu-id="576cd-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="576cd-119">Varje ASR-regel innehåller en av fyra inställningar:</span><span class="sxs-lookup"><span data-stu-id="576cd-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="576cd-120">**Inte konfigurerad:** Inaktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="576cd-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="576cd-121">**Block:** Aktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="576cd-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="576cd-122">**Granskning:** Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras</span><span class="sxs-lookup"><span data-stu-id="576cd-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="576cd-123">**Varna**: Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket</span><span class="sxs-lookup"><span data-stu-id="576cd-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="576cd-124">För närvarande stöds inte varningsläge för tre ASR-regler när du konfigurerar ASR-regler i Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="576cd-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="576cd-125">Mer information finns i [Fall där varningsläge inte stöds.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="576cd-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="576cd-126">Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktioner för övervakning och rapportering som finns tillgängliga i [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="576cd-126">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="576cd-127">Men för andra licenser som Windows Professional eller E3 som inte har tillgång till avancerade funktioner för övervakning och rapportering kan du utveckla dina egna övervakning- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (t.ex. vidarebefordran av händelse).</span><span class="sxs-lookup"><span data-stu-id="576cd-127">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="576cd-128">Mer information om Windows finns i [Windows 10 licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och få [volymlicensieringsguiden för Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="576cd-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="576cd-129">Du kan aktivera minskningsregler för attackytan med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="576cd-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="576cd-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="576cd-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="576cd-131">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="576cd-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="576cd-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="576cd-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="576cd-133">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="576cd-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="576cd-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="576cd-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="576cd-135">Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="576cd-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="576cd-136">Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="576cd-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="576cd-137">Undanta filer och mappar från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="576cd-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="576cd-138">Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="576cd-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="576cd-139">Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="576cd-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="576cd-140">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="576cd-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="576cd-141">Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer.</span><span class="sxs-lookup"><span data-stu-id="576cd-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="576cd-142">(Se [Hantera indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="576cd-142">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="576cd-143">Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="576cd-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="576cd-144">Undantagna filer tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="576cd-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="576cd-145">Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="576cd-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="576cd-146">Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="576cd-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="576cd-147">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="576cd-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="576cd-148">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="576cd-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="576cd-149">ASR-regler stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="576cd-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="576cd-150">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="576cd-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="576cd-151">Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="576cd-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="576cd-152">Intune</span><span class="sxs-lookup"><span data-stu-id="576cd-152">Intune</span></span>

1. <span data-ttu-id="576cd-153">Välj **Profiler för**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="576cd-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="576cd-154">Välj en befintlig profil för slutpunktsskydd eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="576cd-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="576cd-155">Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen.</span><span class="sxs-lookup"><span data-stu-id="576cd-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="576cd-156">För **Profiltyp** väljer du **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="576cd-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="576cd-157">Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="576cd-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="576cd-158">I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard** och sedan Attack Surface **Reduction.**</span><span class="sxs-lookup"><span data-stu-id="576cd-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="576cd-159">Välj önskad inställning för varje ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="576cd-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="576cd-160">Ange **enskilda filer och mappar** under Undantag för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="576cd-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="576cd-161">Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="576cd-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="576cd-162">Varje rad i CSV-filen ska vara formaterad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="576cd-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="576cd-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="576cd-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="576cd-164">Välj **OK** i de tre konfigurationsrutorna.</span><span class="sxs-lookup"><span data-stu-id="576cd-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="576cd-165">Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.</span><span class="sxs-lookup"><span data-stu-id="576cd-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="576cd-166">MDM</span><span class="sxs-lookup"><span data-stu-id="576cd-166">MDM</span></span>

<span data-ttu-id="576cd-167">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.</span><span class="sxs-lookup"><span data-stu-id="576cd-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="576cd-168">Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="576cd-168">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="576cd-169">Värdena som du aktiverar (blockera), inaktiverar, varnar eller aktiverar i granskningsläge är:</span><span class="sxs-lookup"><span data-stu-id="576cd-169">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="576cd-170">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="576cd-170">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="576cd-171">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="576cd-171">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="576cd-172">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="576cd-172">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="576cd-173">6: Varna (aktivera ASR-regeln men tillåt slutanvändaren att kringgå blocket).</span><span class="sxs-lookup"><span data-stu-id="576cd-173">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="576cd-174">Varningsläge är nu tillgängligt för de flesta ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="576cd-174">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="576cd-175">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="576cd-175">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="576cd-176">Exempel:</span><span class="sxs-lookup"><span data-stu-id="576cd-176">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="576cd-177">Se till att ange OMA-URI-värden utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="576cd-177">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="576cd-178">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="576cd-178">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="576cd-179">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Endpoint Protection** Windows Defender Exploit  >    >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="576cd-179">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="576cd-180">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="576cd-180">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="576cd-181">Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="576cd-181">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="576cd-182">Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="576cd-182">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="576cd-183">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="576cd-183">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="576cd-184">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="576cd-184">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="576cd-185">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="576cd-185">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="576cd-186">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="576cd-186">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="576cd-187">På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](https://technet.microsoft.com/library/cc731212.aspx), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="576cd-187">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="576cd-188">I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="576cd-188">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="576cd-189">Expandera trädet för att **Windows komponenter Microsoft Defender Antivirus**  >    >  **Microsoft Defender Exploit Guard**  >  **minska attackytan.**</span><span class="sxs-lookup"><span data-stu-id="576cd-189">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="576cd-190">Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="576cd-190">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="576cd-191">Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.</span><span class="sxs-lookup"><span data-stu-id="576cd-191">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="576cd-192">Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="576cd-192">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="576cd-193">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="576cd-193">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="576cd-194">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="576cd-194">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="576cd-195">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="576cd-195">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="576cd-196">6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)</span><span class="sxs-lookup"><span data-stu-id="576cd-196">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regler i grupprincip":::

5. <span data-ttu-id="576cd-198">Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="576cd-198">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="576cd-199">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="576cd-199">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="576cd-200">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="576cd-200">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="576cd-201">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="576cd-201">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="microsoft-endpoint-manager-custom-procedure"></a><span data-ttu-id="576cd-202">Microsoft Endpoint Manager anpassad procedur</span><span class="sxs-lookup"><span data-stu-id="576cd-202">Microsoft Endpoint Manager custom procedure</span></span>

<span data-ttu-id="576cd-203">Du kan använda ett Microsoft Endpoint Manager (MEM) för att konfigurera anpassade ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="576cd-203">You can use a Microsoft Endpoint Manager (MEM) admin center to configure custom ASR rules.</span></span>

1. <span data-ttu-id="576cd-204">Öppna administrationscentret Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="576cd-204">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="576cd-205">På **Start-menyn** klickar du  **på Enheter**, väljer **Konfigurationsprofil** och klickar sedan **på Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="576cd-205">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   ![MEM– Skapa profil](images/mem01-create-profile.png)

2. <span data-ttu-id="576cd-207">Välj **följande i** följande två listlistor i Skapa en profil:</span><span class="sxs-lookup"><span data-stu-id="576cd-207">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="576cd-208">I **Plattform** väljer du **Windows 10 och senare**</span><span class="sxs-lookup"><span data-stu-id="576cd-208">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="576cd-209">I **Profiltyp** väljer du **Mallar**</span><span class="sxs-lookup"><span data-stu-id="576cd-209">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="576cd-210">Välj **Anpassad** och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="576cd-210">Select **Custom**, and then click **Create**.</span></span>

   ![MeM-regelprofilattribut](images/mem02-profile-attributes.png)

3. <span data-ttu-id="576cd-212">Verktyget Anpassad mall öppnas och visar grunderna **i steg 1.**</span><span class="sxs-lookup"><span data-stu-id="576cd-212">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="576cd-213">I **1 Basics**, i **Name** skriver du ett namn på mallen och i **Beskrivning kan** du skriva en valfri beskrivning.</span><span class="sxs-lookup"><span data-stu-id="576cd-213">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type an optional description.</span></span>

   ![Grundläggande MEM-attribut](images/mem03-1-basics.png)

4. <span data-ttu-id="576cd-215">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="576cd-215">Click **Next**.</span></span> <span data-ttu-id="576cd-216">Steg **2 Konfigurationsinställningar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="576cd-216">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="576cd-217">Om du vill använda OMA-URI Inställningar du på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="576cd-217">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="576cd-218">Nu visas två alternativ: **Lägg till** och **Exportera.**</span><span class="sxs-lookup"><span data-stu-id="576cd-218">Two options now appear: **Add** and **Export**.</span></span>

   ![Inställningar för MEM-konfiguration](images/mem04-2-configuration-settings.png)

5. <span data-ttu-id="576cd-220">Klicka **på Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="576cd-220">Click **Add** again.</span></span> <span data-ttu-id="576cd-221">Lägg **till rad OMA-URI Inställningar** rad.</span><span class="sxs-lookup"><span data-stu-id="576cd-221">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="576cd-222">Gör **följande i** Lägg till rad:</span><span class="sxs-lookup"><span data-stu-id="576cd-222">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="576cd-223">Ange **ett** namn för regeln i Namn.</span><span class="sxs-lookup"><span data-stu-id="576cd-223">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="576cd-224">Skriv **en** kort beskrivning i Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="576cd-224">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="576cd-225">I **OMA-URI** skriver eller klistrar du in den specifika OMA-URI-länken för regeln som du lägger till.</span><span class="sxs-lookup"><span data-stu-id="576cd-225">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="576cd-226">I **Datatyp** väljer du **Sträng**.</span><span class="sxs-lookup"><span data-stu-id="576cd-226">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="576cd-227">I **Värde** skriver eller klistrar du in GUID-värdet, tecknet och värdet Tillstånd utan \= blanksteg _(GUID=StateValue)._</span><span class="sxs-lookup"><span data-stu-id="576cd-227">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="576cd-228">Var: {0: Inaktivera (inaktivera ASR-regeln)}, {1 : Blockera (aktivera ASR-regeln)}, {2: Granska (Utvärdera hur ASR-regeln skulle påverka din organisation om den skulle aktiveras)}, {6: Varna (Aktivera ASR-regeln men tillåta slutanvändare att kringgå blockeringen)}</span><span class="sxs-lookup"><span data-stu-id="576cd-228">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   ![MEM OMA-URI-konfiguration](images/mem05-add-row-oma-uri.png)

6. <span data-ttu-id="576cd-230">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="576cd-230">Click **Save**.</span></span> <span data-ttu-id="576cd-231">**Lägg till rad** stängs.</span><span class="sxs-lookup"><span data-stu-id="576cd-231">**Add Row** closes.</span></span> <span data-ttu-id="576cd-232">Klicka **på** Nästa i **Anpassad.**</span><span class="sxs-lookup"><span data-stu-id="576cd-232">In **Custom**, click **Next**.</span></span> <span data-ttu-id="576cd-233">I steg **3 Omfattningstaggar** är omfattningstaggar valfria.</span><span class="sxs-lookup"><span data-stu-id="576cd-233">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="576cd-234">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="576cd-234">Do one of the following:</span></span>

   - <span data-ttu-id="576cd-235">Klicka **på Välj omfattningstaggar**, välj omfattningstaggen (valfritt) och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="576cd-235">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="576cd-236">Eller klicka på **Nästa**</span><span class="sxs-lookup"><span data-stu-id="576cd-236">Or click **Next**</span></span>

7. <span data-ttu-id="576cd-237">I steg **4 Tilldelningar**, i Inkluderade **grupper** - för de grupper som du vill att regeln ska gälla - välj bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="576cd-237">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="576cd-238">**Lägga till grupper**</span><span class="sxs-lookup"><span data-stu-id="576cd-238">**Add groups**</span></span>
   - <span data-ttu-id="576cd-239">**Lägga till alla användare**</span><span class="sxs-lookup"><span data-stu-id="576cd-239">**Add all users**</span></span>
   - <span data-ttu-id="576cd-240">**Lägg till alla enheter**</span><span class="sxs-lookup"><span data-stu-id="576cd-240">**Add all devices**</span></span>

   ![MEM-uppgifter](images/mem06-4-assignments.png)

8. <span data-ttu-id="576cd-242">Markera **de grupper** som du vill utesluta från regeln i Undantagna grupper och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="576cd-242">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="576cd-243">I steg **5 Tillämplighetsregler** för följande inställningar gör du följande:</span><span class="sxs-lookup"><span data-stu-id="576cd-243">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="576cd-244">I **Regel** väljer du **antingen Tilldela profil** om , eller Tilldela inte profil **om**</span><span class="sxs-lookup"><span data-stu-id="576cd-244">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="576cd-245">I **Egenskap** väljer du den egenskap som du vill att regeln ska gälla för</span><span class="sxs-lookup"><span data-stu-id="576cd-245">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="576cd-246">I **Värde** anger du tillämplig värde eller värdeintervall</span><span class="sxs-lookup"><span data-stu-id="576cd-246">In **Value**, enter the applicable value or value range</span></span>

   ![Tillämplighetsregler för MEM](images/mem07-5-applicability -rules.png)

10. <span data-ttu-id="576cd-248">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="576cd-248">Click **Next**.</span></span> <span data-ttu-id="576cd-249">I steg **6 Granska + skapa** granskar du de inställningar och den information du har valt och angett och klickar sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="576cd-249">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

   ![MEM – granska och skapa](images/mem08-6-review-create.png)

>[!NOTE]
> <span data-ttu-id="576cd-251">Reglerna är aktiva och finns inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="576cd-251">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="576cd-252">Konflikthantering: Om du tilldelar en enhet två olika ASR-principer hanteras regler som har tilldelats olika tillstånd, det finns ingen hantering av konflikter och resultatet blir ett fel.</span><span class="sxs-lookup"><span data-stu-id="576cd-252">Conflict handling: If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
> <span data-ttu-id="576cd-253">Regler som inte är i konflikt resulterar inte i fel och regeln tillämpas korrekt.</span><span class="sxs-lookup"><span data-stu-id="576cd-253">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="576cd-254">Resultatet är att den första regeln tillämpas och efterföljande regler som inte är i konflikt slås ihop med principen.</span><span class="sxs-lookup"><span data-stu-id="576cd-254">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="powershell"></a><span data-ttu-id="576cd-255">PowerShell</span><span class="sxs-lookup"><span data-stu-id="576cd-255">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="576cd-256">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start.</span><span class="sxs-lookup"><span data-stu-id="576cd-256">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="576cd-257">Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.</span><span class="sxs-lookup"><span data-stu-id="576cd-257">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="576cd-258">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**.</span><span class="sxs-lookup"><span data-stu-id="576cd-258">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="576cd-259">Skriv in följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="576cd-259">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="576cd-260">Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="576cd-260">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="576cd-261">Om du vill aktivera ASR-regler i varningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="576cd-261">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="576cd-262">Om du vill inaktivera ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="576cd-262">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="576cd-263">Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.</span><span class="sxs-lookup"><span data-stu-id="576cd-263">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="576cd-264">I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="576cd-264">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="576cd-265">Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="576cd-265">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="576cd-266">`Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler.</span><span class="sxs-lookup"><span data-stu-id="576cd-266">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="576cd-267">Om du vill lägga till i den befintliga uppsättningen använder du `Add-MpPreference` istället.</span><span class="sxs-lookup"><span data-stu-id="576cd-267">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="576cd-268">Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="576cd-268">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="576cd-269">Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="576cd-269">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="576cd-270">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="576cd-270">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="576cd-271">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="576cd-271">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="576cd-272">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="576cd-272">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="576cd-273">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="576cd-273">Related articles</span></span>

- [<span data-ttu-id="576cd-274">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="576cd-274">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="576cd-275">Utvärdera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="576cd-275">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="576cd-276">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="576cd-276">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
