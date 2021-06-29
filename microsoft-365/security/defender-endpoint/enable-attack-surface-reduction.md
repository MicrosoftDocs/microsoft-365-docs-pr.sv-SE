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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: cb56872be3cef2e094583e59a702707f79355743
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177627"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="88d22-104">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="88d22-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="88d22-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88d22-105">**Applies to:**</span></span>

- [<span data-ttu-id="88d22-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="88d22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88d22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88d22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="88d22-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="88d22-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="88d22-109">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="88d22-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="88d22-110">[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk.</span><span class="sxs-lookup"><span data-stu-id="88d22-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="88d22-111">Krav</span><span class="sxs-lookup"><span data-stu-id="88d22-111">Requirements</span></span>

<span data-ttu-id="88d22-112">Funktioner för att minska attackytan i Windows versioner</span><span class="sxs-lookup"><span data-stu-id="88d22-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="88d22-113">Du kan ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:</span><span class="sxs-lookup"><span data-stu-id="88d22-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="88d22-114">Windows 10 Pro, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="88d22-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="88d22-115">Windows 10 Enterprise, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="88d22-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="88d22-116">Windows Server, [version 1803 (Halvårskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="88d22-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="88d22-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="88d22-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="88d22-118">Om du vill använda hela funktionsuppsättningen för minskningsregler för attackytan behöver du:</span><span class="sxs-lookup"><span data-stu-id="88d22-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="88d22-119">Windows Defender Antivirus som primärt AV (realtidsskydd på)</span><span class="sxs-lookup"><span data-stu-id="88d22-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="88d22-120">[Molnleveransskydd på](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) (vissa regler kräver det)</span><span class="sxs-lookup"><span data-stu-id="88d22-120">[Cloud-Delivery Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="88d22-121">Windows 10 Enterprise E5- eller E3-licens Microsoft 365 Företagslicens</span><span class="sxs-lookup"><span data-stu-id="88d22-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="88d22-122">Även om minskningsregler för attackytan inte kräver en [Windows E5-licens](/windows/deployment/deploy-enterprise-licenses), med en Windows E5-licens, får du avancerade hanteringsfunktioner, inklusive övervakning, analys och arbetsflöden som är tillgängliga i Defender för Slutpunkt, samt rapporterings- och konfigurationsfunktioner i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="88d22-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="88d22-123">Dessa avancerade funktioner är inte tillgängliga med en E3-licens, men du kan fortfarande använda Loggboken för att granska händelser för attackytans minskning av regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="88d22-124">Varje ASR-regel innehåller en av fyra inställningar:</span><span class="sxs-lookup"><span data-stu-id="88d22-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="88d22-125">**Inte konfigurerad:** Inaktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="88d22-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="88d22-126">**Block:** Aktivera ASR-regeln</span><span class="sxs-lookup"><span data-stu-id="88d22-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="88d22-127">**Granskning:** Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras</span><span class="sxs-lookup"><span data-stu-id="88d22-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="88d22-128">**Varna**: Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket</span><span class="sxs-lookup"><span data-stu-id="88d22-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d22-129">För närvarande stöds inte varningsläge för tre ASR-regler när du konfigurerar ASR-regler i Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="88d22-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="88d22-130">Mer information finns i [Fall där varningsläge inte stöds.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="88d22-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="88d22-131">Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktioner för övervakning och rapportering som finns tillgängliga i [Microsoft Defender](microsoft-defender-endpoint.md) för slutpunkt (Defender för slutpunkt).</span><span class="sxs-lookup"><span data-stu-id="88d22-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="88d22-132">Men om du har en annan licens, till exempel Windows Professional eller Windows E3 som inte innehåller avancerade funktioner för övervakning och rapportering, kan du utveckla egna övervaknings- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (till exempel Vidarebefordran av händelse).</span><span class="sxs-lookup"><span data-stu-id="88d22-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="88d22-133">Mer information om Windows finns i [Windows 10 licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och få [volymlicensieringsguiden för Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="88d22-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="88d22-134">Du kan aktivera minskningsregler för attackytan med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="88d22-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="88d22-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88d22-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="88d22-136">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="88d22-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="88d22-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="88d22-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="88d22-138">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="88d22-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="88d22-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d22-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="88d22-140">Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="88d22-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="88d22-141">Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="88d22-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="88d22-142">Undanta filer och mappar från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="88d22-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="88d22-143">Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor.</span><span class="sxs-lookup"><span data-stu-id="88d22-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="88d22-144">Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="88d22-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="88d22-145">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="88d22-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="88d22-146">Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer.</span><span class="sxs-lookup"><span data-stu-id="88d22-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="88d22-147">(Se [Hantera indikatorer](manage-indicators.md).)</span><span class="sxs-lookup"><span data-stu-id="88d22-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d22-148">Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="88d22-149">Undantagna filer tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="88d22-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="88d22-150">Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="88d22-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="88d22-151">Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för.</span><span class="sxs-lookup"><span data-stu-id="88d22-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="88d22-152">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="88d22-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="88d22-153">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="88d22-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="88d22-154">ASR-regler stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="88d22-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="88d22-155">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="88d22-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="88d22-156">Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="88d22-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="88d22-157">Intune</span><span class="sxs-lookup"><span data-stu-id="88d22-157">Intune</span></span>

1. <span data-ttu-id="88d22-158">Välj **Profiler för**  >  **enhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="88d22-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="88d22-159">Välj en befintlig profil för slutpunktsskydd eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="88d22-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="88d22-160">Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen.</span><span class="sxs-lookup"><span data-stu-id="88d22-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="88d22-161">För **Profiltyp** väljer du **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="88d22-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="88d22-162">Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="88d22-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="88d22-163">I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard** och sedan Attack Surface **Reduction.**</span><span class="sxs-lookup"><span data-stu-id="88d22-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="88d22-164">Välj önskad inställning för varje ASR-regel.</span><span class="sxs-lookup"><span data-stu-id="88d22-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="88d22-165">Ange **enskilda filer och mappar** under Undantag för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="88d22-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="88d22-166">Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="88d22-167">Varje rad i CSV-filen ska vara formaterad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="88d22-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="88d22-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="88d22-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="88d22-169">Välj **OK** i de tre konfigurationsrutorna.</span><span class="sxs-lookup"><span data-stu-id="88d22-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="88d22-170">Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.</span><span class="sxs-lookup"><span data-stu-id="88d22-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="88d22-171">MEM</span><span class="sxs-lookup"><span data-stu-id="88d22-171">MEM</span></span>

<span data-ttu-id="88d22-172">Du kan använda Microsoft Endpoint Manager (MEM) OMA-URI för att konfigurera anpassade ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="88d22-173">I följande procedur används regeln [Blockera missbruk av utnyttjas sårbara signerade drivrutiner](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) för exemplet.</span><span class="sxs-lookup"><span data-stu-id="88d22-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="88d22-174">Öppna administrationscentret Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="88d22-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="88d22-175">På **Start-menyn** klickar du  **på Enheter**, väljer **Konfigurationsprofil** och klickar sedan **på Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="88d22-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-176">![MEM– Skapa profil](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="88d22-177">Välj **följande i** följande två listlistor i Skapa en profil:</span><span class="sxs-lookup"><span data-stu-id="88d22-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="88d22-178">I **Plattform** väljer du **Windows 10 och senare**</span><span class="sxs-lookup"><span data-stu-id="88d22-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="88d22-179">I **Profiltyp** väljer du **Mallar**</span><span class="sxs-lookup"><span data-stu-id="88d22-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="88d22-180">Välj **Anpassad** och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="88d22-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-181">![MeM-regelprofilattribut](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="88d22-182">Verktyget Anpassad mall öppnas och visar grunderna **i steg 1.**</span><span class="sxs-lookup"><span data-stu-id="88d22-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="88d22-183">I **1 Basics**, i **Name** anger du ett namn på mallen och i **Beskrivning** kan du skriva en beskrivning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="88d22-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-184">![Grundläggande MEM-attribut](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="88d22-185">Klicka **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="88d22-185">Click **Next**.</span></span> <span data-ttu-id="88d22-186">Steg **2 Konfigurationsinställningar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="88d22-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="88d22-187">Om du vill använda OMA-URI Inställningar du på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="88d22-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="88d22-188">Nu visas två alternativ: **Lägg till** och **Exportera.**</span><span class="sxs-lookup"><span data-stu-id="88d22-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-189">![Inställningar för MEM-konfiguration](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="88d22-190">Klicka **på Lägg till** igen.</span><span class="sxs-lookup"><span data-stu-id="88d22-190">Click **Add** again.</span></span> <span data-ttu-id="88d22-191">Lägg **till rad OMA-URI Inställningar** rad.</span><span class="sxs-lookup"><span data-stu-id="88d22-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="88d22-192">Gör **följande i** Lägg till rad:</span><span class="sxs-lookup"><span data-stu-id="88d22-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="88d22-193">Ange **ett** namn för regeln i Namn.</span><span class="sxs-lookup"><span data-stu-id="88d22-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="88d22-194">Skriv **en** kort beskrivning i Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="88d22-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="88d22-195">I **OMA-URI** skriver eller klistrar du in den specifika OMA-URI-länken för regeln som du lägger till.</span><span class="sxs-lookup"><span data-stu-id="88d22-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="88d22-196">I **Datatyp** väljer du **Sträng**.</span><span class="sxs-lookup"><span data-stu-id="88d22-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="88d22-197">I **Värde** skriver eller klistrar du in GUID-värdet, tecknet och värdet Tillstånd utan \= blanksteg _(GUID=StateValue)._</span><span class="sxs-lookup"><span data-stu-id="88d22-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="88d22-198">Var: {0: Inaktivera (inaktivera ASR-regeln)}, {1 : Blockera (aktivera ASR-regeln)}, {2: Granska (Utvärdera hur ASR-regeln skulle påverka din organisation om den skulle aktiveras)}, {6: Varna (Aktivera ASR-regeln men tillåta slutanvändare att kringgå blockeringen)}</span><span class="sxs-lookup"><span data-stu-id="88d22-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-199">![MEM OMA-URI-konfiguration](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="88d22-200">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="88d22-200">Click **Save**.</span></span> <span data-ttu-id="88d22-201">**Lägg till rad** stängs.</span><span class="sxs-lookup"><span data-stu-id="88d22-201">**Add Row** closes.</span></span> <span data-ttu-id="88d22-202">Klicka **på** Nästa i **Anpassad.**</span><span class="sxs-lookup"><span data-stu-id="88d22-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="88d22-203">I steg **3 Omfattningstaggar** är omfattningstaggar valfria.</span><span class="sxs-lookup"><span data-stu-id="88d22-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="88d22-204">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="88d22-204">Do one of the following:</span></span>

   - <span data-ttu-id="88d22-205">Klicka **på Välj omfattningstaggar**, välj omfattningstaggen (valfritt) och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="88d22-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="88d22-206">Eller klicka på **Nästa**</span><span class="sxs-lookup"><span data-stu-id="88d22-206">Or click **Next**</span></span>

7. <span data-ttu-id="88d22-207">I steg **4 Tilldelningar**, i Inkluderade **grupper** - för de grupper som du vill att regeln ska gälla - välj bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="88d22-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="88d22-208">**Lägga till grupper**</span><span class="sxs-lookup"><span data-stu-id="88d22-208">**Add groups**</span></span>
   - <span data-ttu-id="88d22-209">**Lägga till alla användare**</span><span class="sxs-lookup"><span data-stu-id="88d22-209">**Add all users**</span></span>
   - <span data-ttu-id="88d22-210">**Lägg till alla enheter**</span><span class="sxs-lookup"><span data-stu-id="88d22-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-211">![MEM-uppgifter](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="88d22-212">Markera **de grupper** som du vill utesluta från regeln i Undantagna grupper och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="88d22-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="88d22-213">I steg **5 Tillämplighetsregler** för följande inställningar gör du följande:</span><span class="sxs-lookup"><span data-stu-id="88d22-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="88d22-214">I **Regel** väljer du **antingen Tilldela profil** om , eller Tilldela inte profil **om**</span><span class="sxs-lookup"><span data-stu-id="88d22-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="88d22-215">I **Egenskap** väljer du den egenskap som du vill att regeln ska gälla för</span><span class="sxs-lookup"><span data-stu-id="88d22-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="88d22-216">I **Värde** anger du tillämplig värde eller värdeintervall</span><span class="sxs-lookup"><span data-stu-id="88d22-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88d22-217">![Tillämplighetsregler för MEM](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="88d22-218">Klicka **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="88d22-218">Click **Next**.</span></span> <span data-ttu-id="88d22-219">I steg **6 Granska + skapa** granskar du de inställningar och den information du har valt och angett och klickar sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="88d22-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="88d22-220">![MEM – granska och skapa](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="88d22-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="88d22-221">Reglerna är aktiva och finns inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="88d22-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="88d22-222">Konflikthantering:</span><span class="sxs-lookup"><span data-stu-id="88d22-222">Conflict handling:</span></span>
>
> <span data-ttu-id="88d22-223">Om du tilldelar en enhet två olika ASR-principer, hanteras konflikterna på regler som har tilldelats olika tillstånd, det finns ingen hantering av konflikter och resultatet är ett fel.</span><span class="sxs-lookup"><span data-stu-id="88d22-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="88d22-224">Regler som inte är i konflikt resulterar inte i fel och regeln tillämpas korrekt.</span><span class="sxs-lookup"><span data-stu-id="88d22-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="88d22-225">Resultatet är att den första regeln tillämpas och efterföljande regler som inte är i konflikt slås ihop med principen.</span><span class="sxs-lookup"><span data-stu-id="88d22-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="88d22-226">MDM</span><span class="sxs-lookup"><span data-stu-id="88d22-226">MDM</span></span>

<span data-ttu-id="88d22-227">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.</span><span class="sxs-lookup"><span data-stu-id="88d22-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="88d22-228">Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="88d22-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="88d22-229">Värdena som du aktiverar (blockera), inaktiverar, varnar eller aktiverar i granskningsläge är:</span><span class="sxs-lookup"><span data-stu-id="88d22-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="88d22-230">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="88d22-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="88d22-231">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="88d22-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="88d22-232">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="88d22-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="88d22-233">6: Varna (aktivera ASR-regeln men tillåt slutanvändaren att kringgå blocket).</span><span class="sxs-lookup"><span data-stu-id="88d22-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="88d22-234">Varningsläge är nu tillgängligt för de flesta ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="88d22-235">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="88d22-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="88d22-236">Exempel:</span><span class="sxs-lookup"><span data-stu-id="88d22-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="88d22-237">Se till att ange OMA-URI-värden utan blanksteg.</span><span class="sxs-lookup"><span data-stu-id="88d22-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="88d22-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="88d22-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="88d22-239">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Endpoint Protection** Windows Defender Exploit  >    >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="88d22-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="88d22-240">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="88d22-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="88d22-241">Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="88d22-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="88d22-242">Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="88d22-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="88d22-243">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="88d22-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="88d22-244">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="88d22-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="88d22-245">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="88d22-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="88d22-246">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.</span><span class="sxs-lookup"><span data-stu-id="88d22-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="88d22-247">På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](https://technet.microsoft.com/library/cc731212.aspx), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="88d22-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="88d22-248">I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="88d22-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="88d22-249">Expandera trädet för att **Windows komponenter Microsoft Defender Antivirus**  >    >  **Microsoft Defender Exploit Guard**  >  **minska attackytan.**</span><span class="sxs-lookup"><span data-stu-id="88d22-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="88d22-250">Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="88d22-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="88d22-251">Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.</span><span class="sxs-lookup"><span data-stu-id="88d22-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="88d22-252">Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="88d22-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="88d22-253">0: Inaktivera (Inaktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="88d22-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="88d22-254">1: Blockera (aktivera ASR-regeln)</span><span class="sxs-lookup"><span data-stu-id="88d22-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="88d22-255">2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)</span><span class="sxs-lookup"><span data-stu-id="88d22-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="88d22-256">6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)</span><span class="sxs-lookup"><span data-stu-id="88d22-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regler i grupprincip":::

5. <span data-ttu-id="88d22-258">Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="88d22-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="88d22-259">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="88d22-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="88d22-260">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="88d22-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="88d22-261">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="88d22-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="88d22-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d22-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="88d22-263">Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start.</span><span class="sxs-lookup"><span data-stu-id="88d22-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="88d22-264">Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.</span><span class="sxs-lookup"><span data-stu-id="88d22-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="88d22-265">Skriv **powershell** i Start-menyn, högerklicka på **Windows PowerShell** välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="88d22-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="88d22-266">Skriv in följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88d22-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="88d22-267">Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88d22-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="88d22-268">Om du vill aktivera ASR-regler i varningsläge använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88d22-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="88d22-269">Använd följande cmdlet för att aktivera ASR Blockera missbruk av utnyttjas sårbara signerade drivrutiner:</span><span class="sxs-lookup"><span data-stu-id="88d22-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="88d22-270">Om du vill inaktivera ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88d22-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="88d22-271">Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.</span><span class="sxs-lookup"><span data-stu-id="88d22-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="88d22-272">I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="88d22-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="88d22-273">Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="88d22-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="88d22-274">`Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler.</span><span class="sxs-lookup"><span data-stu-id="88d22-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="88d22-275">Om du vill lägga till i den befintliga uppsättningen använder du `Add-MpPreference` istället.</span><span class="sxs-lookup"><span data-stu-id="88d22-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="88d22-276">Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="88d22-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="88d22-277">Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="88d22-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="88d22-278">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="88d22-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="88d22-279">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="88d22-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="88d22-280">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="88d22-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="88d22-281">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="88d22-281">Related articles</span></span>

- [<span data-ttu-id="88d22-282">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="88d22-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="88d22-283">Utvärdera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="88d22-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="88d22-284">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="88d22-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
