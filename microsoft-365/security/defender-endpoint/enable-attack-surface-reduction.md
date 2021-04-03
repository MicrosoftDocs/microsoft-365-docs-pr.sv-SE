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
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570954"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="bb508-104">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="bb508-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bb508-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bb508-105">**Applies to:**</span></span>
- [<span data-ttu-id="bb508-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bb508-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bb508-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb508-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bb508-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bb508-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bb508-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bb508-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bb508-110">[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk.</span><span class="sxs-lookup"><span data-stu-id="bb508-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="bb508-111">Du kan ange ASR-regler för enheter med någon av följande versioner och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="bb508-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="bb508-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="bb508-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="bb508-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="bb508-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="bb508-114">Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="bb508-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="bb508-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="bb508-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="bb508-116">Varje ASR-regel innehåller en av tre inställningar:</span><span class="sxs-lookup"><span data-stu-id="bb508-116">Each ASR rule contains one of three settings:</span></span>

- <span data-ttu-id="bb508-117">Inte konfigurerad: Inaktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="bb508-117">Not configured: Disable the ASR rule</span></span>
- <span data-ttu-id="bb508-118">Blockera: Aktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="bb508-118">Block: Enable the ASR rule</span></span>
- <span data-ttu-id="bb508-119">Granskning: Utvärdera hur ASR-regeln skulle påverka organisationen om den är aktiverad</span><span class="sxs-lookup"><span data-stu-id="bb508-119">Audit: Evaluate how the ASR rule would impact your organization if enabled</span></span>

<span data-ttu-id="bb508-120">Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktionerna för övervakning och rapportering i [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="bb508-120">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="bb508-121">Men för andra licenser som Windows Professional eller E3 som inte har tillgång till avancerade funktioner för övervakning och rapportering kan du utveckla dina egna övervaknings- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (t.ex. vidarebefordran av händelse).</span><span class="sxs-lookup"><span data-stu-id="bb508-121">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="bb508-122">Mer information om Windows-licensiering finns i [Windows 10-licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och volymlicensieringsguiden [för Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="bb508-122">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="bb508-123">Du kan aktivera minskningsregler för attackytan med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="bb508-123">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="bb508-124">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bb508-124">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="bb508-125">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="bb508-125">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="bb508-126">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bb508-126">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="bb508-127">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="bb508-127">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="bb508-128">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb508-128">PowerShell</span></span>](#powershell)

<span data-ttu-id="bb508-129">Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="bb508-129">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="bb508-130">Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="bb508-130">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="bb508-131">Undanta filer och mappar från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="bb508-131">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="bb508-132">Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="bb508-132">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="bb508-133">Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="bb508-133">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="bb508-134">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="bb508-134">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="bb508-135">Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer.</span><span class="sxs-lookup"><span data-stu-id="bb508-135">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="bb508-136">(Se [Hantera indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="bb508-136">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb508-137">Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="bb508-137">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="bb508-138">Undantagna filer tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="bb508-138">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="bb508-139">Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="bb508-139">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="bb508-140">Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="bb508-140">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="bb508-141">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="bb508-141">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="bb508-142">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="bb508-142">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="bb508-143">ASR-regler stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="bb508-143">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="bb508-144">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="bb508-144">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="bb508-145">Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="bb508-145">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="bb508-146">Intune</span><span class="sxs-lookup"><span data-stu-id="bb508-146">Intune</span></span>

1. <span data-ttu-id="bb508-147">Välj **Profiler för**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="bb508-147">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="bb508-148">Välj en befintlig profil för slutpunktsskydd eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="bb508-148">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="bb508-149">Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen.</span><span class="sxs-lookup"><span data-stu-id="bb508-149">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="bb508-150">För **Profiltyp** väljer du **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="bb508-150">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="bb508-151">Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="bb508-151">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="bb508-152">I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard och** sedan Attack Surface **Reduction**.</span><span class="sxs-lookup"><span data-stu-id="bb508-152">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="bb508-153">Välj önskad inställning för varje ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="bb508-153">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="bb508-154">Ange **enskilda filer och mappar** under Undantag för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="bb508-154">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="bb508-155">Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="bb508-155">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="bb508-156">Varje rad i CSV-filen ska vara formaterad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="bb508-156">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="bb508-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="bb508-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="bb508-158">Välj **OK** i de tre konfigurationsrutorna.</span><span class="sxs-lookup"><span data-stu-id="bb508-158">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="bb508-159">Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.</span><span class="sxs-lookup"><span data-stu-id="bb508-159">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="bb508-160">MDM</span><span class="sxs-lookup"><span data-stu-id="bb508-160">MDM</span></span>

<span data-ttu-id="bb508-161">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.</span><span class="sxs-lookup"><span data-stu-id="bb508-161">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="bb508-162">Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="bb508-162">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="bb508-163">Värdena som du aktiverar, inaktiverar eller aktiverar i granskningsläge är:</span><span class="sxs-lookup"><span data-stu-id="bb508-163">The values to enable, disable, or enable in audit mode are:</span></span>

- <span data-ttu-id="bb508-164">Inaktivera = 0</span><span class="sxs-lookup"><span data-stu-id="bb508-164">Disable = 0</span></span>
- <span data-ttu-id="bb508-165">Block (aktivera ASR-regel) = 1</span><span class="sxs-lookup"><span data-stu-id="bb508-165">Block (enable ASR rule) = 1</span></span>
- <span data-ttu-id="bb508-166">Granskning = 2</span><span class="sxs-lookup"><span data-stu-id="bb508-166">Audit = 2</span></span>

<span data-ttu-id="bb508-167">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="bb508-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="bb508-168">Exempel:</span><span class="sxs-lookup"><span data-stu-id="bb508-168">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="bb508-169">Se till att ange OMA-URI-värden utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="bb508-169">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="bb508-170">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bb508-170">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="bb508-171">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Slutpunktsskydd för**  >  **efterlevnad** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="bb508-171">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="bb508-172">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="bb508-172">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="bb508-173">Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="bb508-173">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="bb508-174">Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="bb508-174">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="bb508-175">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="bb508-175">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="bb508-176">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="bb508-176">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="bb508-177">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="bb508-177">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="bb508-178">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="bb508-178">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="bb508-179">Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="bb508-179">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="bb508-180">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="bb508-180">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="bb508-181">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Microsoft Defender  >  **Sårbarhetsskydd-** minskning av  >  **attackytan**.</span><span class="sxs-lookup"><span data-stu-id="bb508-181">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="bb508-182">Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="bb508-182">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="bb508-183">Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.</span><span class="sxs-lookup"><span data-stu-id="bb508-183">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="bb508-184">Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="bb508-184">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="bb508-185">Inaktivera = 0</span><span class="sxs-lookup"><span data-stu-id="bb508-185">Disable = 0</span></span>
   - <span data-ttu-id="bb508-186">Block (aktivera ASR-regel) = 1</span><span class="sxs-lookup"><span data-stu-id="bb508-186">Block (enable ASR rule) = 1</span></span>
   - <span data-ttu-id="bb508-187">Granskning = 2</span><span class="sxs-lookup"><span data-stu-id="bb508-187">Audit = 2</span></span>

   ![Grupprincipinställning som visar ett tomt ID och värde för 1 för att minska attackytan](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. <span data-ttu-id="bb508-189">Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="bb508-189">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="bb508-190">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="bb508-190">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="bb508-191">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="bb508-191">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="bb508-192">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="bb508-192">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="bb508-193">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb508-193">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="bb508-194">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start.</span><span class="sxs-lookup"><span data-stu-id="bb508-194">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="bb508-195">Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.</span><span class="sxs-lookup"><span data-stu-id="bb508-195">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="bb508-196">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör.**</span><span class="sxs-lookup"><span data-stu-id="bb508-196">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="bb508-197">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bb508-197">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="bb508-198">Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bb508-198">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="bb508-199">Om du vill inaktivera ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bb508-199">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="bb508-200">Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.</span><span class="sxs-lookup"><span data-stu-id="bb508-200">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="bb508-201">I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="bb508-201">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="bb508-202">Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="bb508-202">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="bb508-203">`Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler.</span><span class="sxs-lookup"><span data-stu-id="bb508-203">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="bb508-204">Om du vill lägga till i den befintliga uppsättningen ska du använda `Add-MpPreference` den i stället.</span><span class="sxs-lookup"><span data-stu-id="bb508-204">If you want to add to the existing set, you should use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="bb508-205">Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="bb508-205">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="bb508-206">Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bb508-206">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="bb508-207">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="bb508-207">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bb508-208">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="bb508-208">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="bb508-209">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="bb508-209">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bb508-210">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="bb508-210">Related articles</span></span>

- [<span data-ttu-id="bb508-211">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="bb508-211">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="bb508-212">Utvärdera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="bb508-212">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="bb508-213">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="bb508-213">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
