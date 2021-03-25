---
title: Utföra svarsåtgärder för en fil i Microsoft Defender för Endpoint
description: Vidta svarsåtgärder för filrelaterade aviseringar genom att stoppa och kvartilera en fil eller blockera en fil och kontrollera aktivitetsinformation.
keywords: svara, stoppa och sätt i karantän, blockera fil, djupanalys
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ba48adcf93c5b768b2280729b33a1a7d361919cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074233"
---
# <a name="take-response-actions-on-a-file"></a><span data-ttu-id="c7f19-104">Utföra svarsåtgärder för en fil</span><span class="sxs-lookup"><span data-stu-id="c7f19-104">Take response actions on a file</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c7f19-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c7f19-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7f19-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7f19-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> <span data-ttu-id="c7f19-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c7f19-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c7f19-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c7f19-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

<span data-ttu-id="c7f19-109">Svara snabbt på identifierade attacker genom att stoppa och kvartilerna på filer eller blockera en fil.</span><span class="sxs-lookup"><span data-stu-id="c7f19-109">Quickly respond to detected attacks by stopping and quarantining files or blocking a file.</span></span> <span data-ttu-id="c7f19-110">När du har agerat på filer kan du kontrollera aktivitetsinformation i Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="c7f19-110">After taking action on files, you can check activity details in the Action center.</span></span>

<span data-ttu-id="c7f19-111">Svarsåtgärder är tillgängliga på en fils detaljerade profilsida.</span><span class="sxs-lookup"><span data-stu-id="c7f19-111">Response actions are available on a file's detailed profile page.</span></span> <span data-ttu-id="c7f19-112">När du är på den här sidan kan du växla mellan den nya och gamla sidlayouten genom att byta **ny Filsida.**</span><span class="sxs-lookup"><span data-stu-id="c7f19-112">Once on this page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="c7f19-113">Resten av den här artikeln beskriver den nyare sidlayouten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-113">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="c7f19-114">Svarsåtgärder går högst upp på filsidan och omfattar:</span><span class="sxs-lookup"><span data-stu-id="c7f19-114">Response actions run along the top of the file page, and include:</span></span>

- <span data-ttu-id="c7f19-115">Stoppa och sätt i karantän</span><span class="sxs-lookup"><span data-stu-id="c7f19-115">Stop and Quarantine File</span></span>
- <span data-ttu-id="c7f19-116">Lägg till indikator</span><span class="sxs-lookup"><span data-stu-id="c7f19-116">Add Indicator</span></span>
- <span data-ttu-id="c7f19-117">Ladda ned fil</span><span class="sxs-lookup"><span data-stu-id="c7f19-117">Download file</span></span>
- <span data-ttu-id="c7f19-118">Kontakta en hotexpert</span><span class="sxs-lookup"><span data-stu-id="c7f19-118">Consult a threat expert</span></span>
- <span data-ttu-id="c7f19-119">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="c7f19-119">Action center</span></span>

<span data-ttu-id="c7f19-120">Du kan också skicka filer för djupanalys för att köra filen i en säker sandbox-miljö i molnet.</span><span class="sxs-lookup"><span data-stu-id="c7f19-120">You can also submit files for deep analysis, to run the file in a secure cloud sandbox.</span></span> <span data-ttu-id="c7f19-121">När analysen är klar får du en detaljerad rapport som innehåller information om filens beteende.</span><span class="sxs-lookup"><span data-stu-id="c7f19-121">When the analysis is complete, you'll get a detailed report that provides information about the behavior of the file.</span></span> <span data-ttu-id="c7f19-122">Du kan skicka filer för djupanalys och läsa tidigare rapporter genom att välja **fliken Djupanalys.** Den finns under filinformationskorten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-122">You can submit files for deep analysis and read past reports by selecting the **Deep analysis** tab. It's located below the file information cards.</span></span>

<span data-ttu-id="c7f19-123">Vissa åtgärder kräver vissa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="c7f19-123">Some actions require certain permissions.</span></span> <span data-ttu-id="c7f19-124">I följande tabell beskrivs vilka åtgärder vissa behörigheter kan vidta för bärbara körbara filer (PE) och icke-PE-filer:</span><span class="sxs-lookup"><span data-stu-id="c7f19-124">The following table describes what action certain permissions can take on portable executable (PE) and non-PE files:</span></span>

| <span data-ttu-id="c7f19-125">Behörighet</span><span class="sxs-lookup"><span data-stu-id="c7f19-125">Permission</span></span>             | <span data-ttu-id="c7f19-126">PE-filer</span><span class="sxs-lookup"><span data-stu-id="c7f19-126">PE files</span></span> | <span data-ttu-id="c7f19-127">Icke-PE-filer</span><span class="sxs-lookup"><span data-stu-id="c7f19-127">Non-PE files</span></span> |
| :--------------------- | :------: | :----------: |
| <span data-ttu-id="c7f19-128">Visa data</span><span class="sxs-lookup"><span data-stu-id="c7f19-128">View data</span></span>              |     <span data-ttu-id="c7f19-129">X</span><span class="sxs-lookup"><span data-stu-id="c7f19-129">X</span></span>    |       <span data-ttu-id="c7f19-130">X</span><span class="sxs-lookup"><span data-stu-id="c7f19-130">X</span></span>      |
| <span data-ttu-id="c7f19-131">Undersökning av aviseringar</span><span class="sxs-lookup"><span data-stu-id="c7f19-131">Alerts investigation</span></span>   | <span data-ttu-id="c7f19-132">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="c7f19-132">&#x2611;</span></span> |       <span data-ttu-id="c7f19-133">X</span><span class="sxs-lookup"><span data-stu-id="c7f19-133">X</span></span>      |
| <span data-ttu-id="c7f19-134">Grundläggande livesvar</span><span class="sxs-lookup"><span data-stu-id="c7f19-134">Live response basic</span></span>    |     <span data-ttu-id="c7f19-135">X</span><span class="sxs-lookup"><span data-stu-id="c7f19-135">X</span></span>    |       <span data-ttu-id="c7f19-136">X</span><span class="sxs-lookup"><span data-stu-id="c7f19-136">X</span></span>      |
| <span data-ttu-id="c7f19-137">Livesvar avancerat</span><span class="sxs-lookup"><span data-stu-id="c7f19-137">Live response advanced</span></span> | <span data-ttu-id="c7f19-138">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="c7f19-138">&#x2611;</span></span> |   <span data-ttu-id="c7f19-139">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="c7f19-139">&#x2611;</span></span>   |

<span data-ttu-id="c7f19-140">Mer information om roller finns i Skapa [och hantera roller för rollbaserad åtkomstkontroll.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c7f19-140">For more information on roles, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="stop-and-quarantine-files-in-your-network"></a><span data-ttu-id="c7f19-141">Stoppa och sätt filer i nätverket i karantän</span><span class="sxs-lookup"><span data-stu-id="c7f19-141">Stop and quarantine files in your network</span></span>

<span data-ttu-id="c7f19-142">Du kan innehålla en attack i organisationen genom att stoppa den skadliga processen och kvartilen av filen där den observerades.</span><span class="sxs-lookup"><span data-stu-id="c7f19-142">You can contain an attack in your organization by stopping the malicious process and quarantining the file where it was observed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7f19-143">Du kan bara vidta den här åtgärden om:</span><span class="sxs-lookup"><span data-stu-id="c7f19-143">You can only take this action if:</span></span>
>
> - <span data-ttu-id="c7f19-144">Den enhet som du vidtar åtgärden på kör Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="c7f19-144">The device you're taking the action on is running Windows 10, version 1703 or later</span></span>
> - <span data-ttu-id="c7f19-145">Filen tillhör inte betrodda tredjepartsutgivare eller är inte signerad av Microsoft</span><span class="sxs-lookup"><span data-stu-id="c7f19-145">The file does not belong to trusted third-party publishers or not signed by Microsoft</span></span>
> - <span data-ttu-id="c7f19-146">Microsoft Defender Antivirus måste åtminstone köras på passivt läge.</span><span class="sxs-lookup"><span data-stu-id="c7f19-146">Microsoft Defender Antivirus must at least be running on Passive mode.</span></span> <span data-ttu-id="c7f19-147">Mer information finns i Kompatibilitet [för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="c7f19-147">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

<span data-ttu-id="c7f19-148">Åtgärden **Stoppa och sätt i karantän** innehåller att stoppa processer, kvartiler av filerna och ta bort beständiga data, till exempel registernycklar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-148">The **Stop and Quarantine File** action includes stopping running processes, quarantining the files, and deleting persistent data such as registry keys.</span></span>

<span data-ttu-id="c7f19-149">Den här åtgärden gäller på enheter med Windows 10, version 1703 eller senare, där filen har observerats de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c7f19-149">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f19-150">Du kan när som helst återställa filen från karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-150">You’ll be able to restore the file from quarantine at any time.</span></span>

### <a name="stop-and-quarantine-files"></a><span data-ttu-id="c7f19-151">Stoppa och sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="c7f19-151">Stop and quarantine files</span></span>

1. <span data-ttu-id="c7f19-152">Markera den fil som du vill stoppa och sätt i karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-152">Select the file you want to stop and quarantine.</span></span> <span data-ttu-id="c7f19-153">Du kan välja en fil från någon av följande vyer eller använda sökrutan:</span><span class="sxs-lookup"><span data-stu-id="c7f19-153">You can select a file from any of the following views or use the Search box:</span></span>

   - <span data-ttu-id="c7f19-154">**Aviseringar** – klicka på motsvarande länkar från beskrivningen eller informationen i tidslinjen Med Artefakt</span><span class="sxs-lookup"><span data-stu-id="c7f19-154">**Alerts** - click the corresponding links from the Description or Details in the Artifact timeline</span></span>
   - <span data-ttu-id="c7f19-155">**Sökrutan** – **välj** Arkiv i den nedrullningsmenyn och ange filnamnet</span><span class="sxs-lookup"><span data-stu-id="c7f19-155">**Search box** - select **File** from the drop–down menu and enter the file name</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7f19-156">Åtgärden att stoppa och sätta i karantän är begränsad till högst 1 000 enheter.</span><span class="sxs-lookup"><span data-stu-id="c7f19-156">The stop and quarantine file action is limited to a maximum of 1000 devices.</span></span> <span data-ttu-id="c7f19-157">Information om hur du stoppar en fil på ett större antal enheter finns i [Lägga till indikator för att blockera eller tillåta fil](#add-indicator-to-block-or-allow-a-file).</span><span class="sxs-lookup"><span data-stu-id="c7f19-157">To stop a file on a larger number of devices, see [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).</span></span>

2. <span data-ttu-id="c7f19-158">Gå till det översta fältet och välj **Stoppa och sätt i karantän.**</span><span class="sxs-lookup"><span data-stu-id="c7f19-158">Go to the top bar and select **Stop and Quarantine File**.</span></span>

   ![Bild på åtgärd för att stoppa och sätta i karantän](images/atp-stop-quarantine-file.png)

3. <span data-ttu-id="c7f19-160">Ange en orsak och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="c7f19-160">Specify a reason, then select **Confirm**.</span></span>

   ![Bild av modalt fönster för stopp och karantän](images/atp-stop-quarantine.png)

   <span data-ttu-id="c7f19-162">Åtgärdscenter visar information om inskickat material:</span><span class="sxs-lookup"><span data-stu-id="c7f19-162">The Action center shows the submission information:</span></span>
   
   ![Bild av åtgärdscenter för stopp och karantän](images/atp-stopnquarantine-file.png)

   - <span data-ttu-id="c7f19-164">**Inskickningstid** – visar när åtgärden skickades.</span><span class="sxs-lookup"><span data-stu-id="c7f19-164">**Submission time** - Shows when the action was submitted.</span></span>
   - <span data-ttu-id="c7f19-165">**Lyckades** – Visar antalet enheter där filen har stoppats och satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-165">**Success** - Shows the number of devices where the file has been stopped and quarantined.</span></span>
   - <span data-ttu-id="c7f19-166">**Misslyckades** – Visar antalet enheter där åtgärden misslyckades och information om felet.</span><span class="sxs-lookup"><span data-stu-id="c7f19-166">**Failed** - Shows the number of devices where the action failed and details about the failure.</span></span>
   - <span data-ttu-id="c7f19-167">**Väntande** – Visar antalet enheter där filen ännu inte har stoppats och satts i karantän från.</span><span class="sxs-lookup"><span data-stu-id="c7f19-167">**Pending** - Shows the number of devices where the file is yet to be stopped and quarantined from.</span></span> <span data-ttu-id="c7f19-168">Det kan ta tid i fall när enheten är offline eller inte ansluten till nätverket.</span><span class="sxs-lookup"><span data-stu-id="c7f19-168">This can take time for cases when the device is offline or not connected to the network.</span></span>

4. <span data-ttu-id="c7f19-169">Välj någon av statusindikatorerna om du vill visa mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c7f19-169">Select any of the status indicators to view more information about the action.</span></span> <span data-ttu-id="c7f19-170">Välj till exempel **Misslyckades om** du vill se var åtgärden misslyckades.</span><span class="sxs-lookup"><span data-stu-id="c7f19-170">For example, select **Failed** to see where the action failed.</span></span>

<span data-ttu-id="c7f19-171">**Meddelande på enhetens användare:**</span><span class="sxs-lookup"><span data-stu-id="c7f19-171">**Notification on device user**:</span></span></br>
<span data-ttu-id="c7f19-172">När filen tas bort från en enhet visas följande meddelande:</span><span class="sxs-lookup"><span data-stu-id="c7f19-172">When the file is being removed from a device, the following notification is shown:</span></span>

![Bild av meddelande på enhetens användare](images/atp-notification-file.png)

<span data-ttu-id="c7f19-174">På enhetens tidslinje läggs en ny händelse till för varje enhet där en fil har stoppats och satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-174">In the device timeline, a new event is added for each device where a file was stopped and quarantined.</span></span>

<span data-ttu-id="c7f19-175">En varning visas innan åtgärden implementeras för filer som används ofta i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-175">A warning is shown before the action is implemented for files widely used throughout an organization.</span></span> <span data-ttu-id="c7f19-176">Det är för att verifiera att åtgärden är avsedd.</span><span class="sxs-lookup"><span data-stu-id="c7f19-176">It's to validate that the operation is intended.</span></span>

## <a name="restore-file-from-quarantine"></a><span data-ttu-id="c7f19-177">Återställa en fil från karantän</span><span class="sxs-lookup"><span data-stu-id="c7f19-177">Restore file from quarantine</span></span>

<span data-ttu-id="c7f19-178">Du kan återställa och ta bort en fil från karantän om du har fastställt att den är ren efter en undersökning.</span><span class="sxs-lookup"><span data-stu-id="c7f19-178">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="c7f19-179">Kör följande kommando på varje enhet där filen satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-179">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="c7f19-180">Öppna en upphöjd kommandoradsfråga på enheten:</span><span class="sxs-lookup"><span data-stu-id="c7f19-180">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="c7f19-181">Gå till **Start** och skriv _cmd_.</span><span class="sxs-lookup"><span data-stu-id="c7f19-181">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="c7f19-182">Högerklicka på **Kommandotolken** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="c7f19-182">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="c7f19-183">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="c7f19-183">Enter the following command, and press **Enter**:</span></span>

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> <span data-ttu-id="c7f19-184">I vissa fall kan **ThreatName** visas som: EUS:Win32/CustomEnterpriseBlock!cl.</span><span class="sxs-lookup"><span data-stu-id="c7f19-184">In some scenarios, the **ThreatName** may appear as: EUS:Win32/CustomEnterpriseBlock!cl.</span></span>
>
> <span data-ttu-id="c7f19-185">Defender för Endpoint återställer alla egna blockerade filer som har satts i karantän på den här enheten under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c7f19-185">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7f19-186">En fil som har satts i karantän som ett potentiellt nätverkshot kanske inte kan återställas.</span><span class="sxs-lookup"><span data-stu-id="c7f19-186">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="c7f19-187">Om en användare försöker återställa filen efter karantänen är filen kanske inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c7f19-187">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="c7f19-188">Det kan bero på att systemet inte längre har nätverksautentiseringsuppgifter för att få åtkomst till filen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-188">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="c7f19-189">Vanligtvis beror det på en tillfällig inloggning till ett system eller en delad mapp och åtkomsttoken har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="c7f19-189">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="download-or-collect-file"></a><span data-ttu-id="c7f19-190">Ladda ned eller samla in fil</span><span class="sxs-lookup"><span data-stu-id="c7f19-190">Download or collect file</span></span>

<span data-ttu-id="c7f19-191">Om **du väljer Ladda** ned fil från svarsåtgärderna kan du ladda ned ett lokalt, lösenordsskyddat ZIP-arkiv som innehåller filen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-191">Selecting **Download file** from the response actions allows you to download a local, password-protected .zip archive containing your file.</span></span> <span data-ttu-id="c7f19-192">En utfällningsfil visas där du kan ange en orsak till att filen laddas ned och ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="c7f19-192">A flyout will appear where you can record a reason for downloading the file, and set a password.</span></span>

<span data-ttu-id="c7f19-193">Som standard kan du inte ladda ned filer som ligger i karantän.</span><span class="sxs-lookup"><span data-stu-id="c7f19-193">By default, you will not be able to download files that are in quarantine.</span></span>

![Bild på filåtgärd för nedladdning](images/atp-download-file-action.png)

### <a name="collect-files"></a><span data-ttu-id="c7f19-195">Samla in filer</span><span class="sxs-lookup"><span data-stu-id="c7f19-195">Collect files</span></span>

<span data-ttu-id="c7f19-196">Om en fil inte redan lagras av Microsoft Defender för Endpoint kan du inte ladda ned den.</span><span class="sxs-lookup"><span data-stu-id="c7f19-196">If a file is not already stored by Microsoft Defender for Endpoint, you can't download it.</span></span> <span data-ttu-id="c7f19-197">I stället visas knappen Samla **in fil** på samma plats.</span><span class="sxs-lookup"><span data-stu-id="c7f19-197">Instead, you'll see a **Collect file** button in the same location.</span></span> <span data-ttu-id="c7f19-198">Om en fil inte har visats i organisationen under de senaste 30 dagarna **inaktiveras** insamlingsfilen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-198">If a file hasn't been seen in the organization in the past 30 days, **Collect file** will be disabled.</span></span>
> [!Important]
> <span data-ttu-id="c7f19-199">En fil som har satts i karantän som ett potentiellt nätverkshot kanske inte kan återställas.</span><span class="sxs-lookup"><span data-stu-id="c7f19-199">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="c7f19-200">Om en användare försöker återställa filen efter karantänen är filen kanske inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c7f19-200">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="c7f19-201">Det kan bero på att systemet inte längre har nätverksautentiseringsuppgifter för att få åtkomst till filen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-201">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="c7f19-202">Vanligtvis beror det på en tillfällig inloggning till ett system eller en delad mapp och åtkomsttoken har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="c7f19-202">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="add-indicator-to-block-or-allow-a-file"></a><span data-ttu-id="c7f19-203">Lägga till indikator för att blockera eller tillåta en fil</span><span class="sxs-lookup"><span data-stu-id="c7f19-203">Add indicator to block or allow a file</span></span>

<span data-ttu-id="c7f19-204">Förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="c7f19-204">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="c7f19-205">Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den.</span><span class="sxs-lookup"><span data-stu-id="c7f19-205">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="c7f19-206">Den här åtgärden gör att den inte kan läsas, skrivas eller köras på enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-206">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="c7f19-207">Den här funktionen är tillgänglig om din organisation använder Microsoft Defender Antivirus och Moln levererat skydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="c7f19-207">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud–delivered protection is enabled.</span></span> <span data-ttu-id="c7f19-208">Mer information finns i [Hantera moln-leveransskydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="c7f19-208">For more information, see [Manage cloud–delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
>
> - <span data-ttu-id="c7f19-209">Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7f19-209">The Antimalware client version must be 4.18.1901.x or later.</span></span>
> - <span data-ttu-id="c7f19-210">Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben.</span><span class="sxs-lookup"><span data-stu-id="c7f19-210">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="c7f19-211">Den har för närvarande stöd för bärbara körbara (PE) filer, inklusive _.exe-_ _och .dll-filer._</span><span class="sxs-lookup"><span data-stu-id="c7f19-211">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="c7f19-212">Täckningen utökas med tiden.</span><span class="sxs-lookup"><span data-stu-id="c7f19-212">The coverage will be extended over time.</span></span>
> - <span data-ttu-id="c7f19-213">Den här svarsåtgärden är tillgänglig för enheter i Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7f19-213">This response action is available for devices on Windows 10, version 1703 or later.</span></span>
> - <span data-ttu-id="c7f19-214">Funktionen tillåt eller blockera kan inte utföras för filer om filens klassificering finns på enhetens cache innan åtgärden för att tillåta eller blockera.</span><span class="sxs-lookup"><span data-stu-id="c7f19-214">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f19-215">PE-filen måste finnas på enhetens tidslinje för att du ska kunna vidta den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c7f19-215">The PE file needs to be in the device timeline for you to be able to take this action.</span></span>
>
> <span data-ttu-id="c7f19-216">Det kan finnas ett par minuter med fördröjning mellan den tid åtgärden vidtas och den faktiska filen blockeras.</span><span class="sxs-lookup"><span data-stu-id="c7f19-216">There may be a couple of minutes of latency between the time the action is taken and the actual file being blocked.</span></span>

### <a name="enable-the-block-file-feature"></a><span data-ttu-id="c7f19-217">Aktivera blockeringsfilsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c7f19-217">Enable the block file feature</span></span>

<span data-ttu-id="c7f19-218">För att börja blockera filer måste du först [aktivera funktionen Spärra eller **tillåt**](advanced-features.md) i Inställningar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-218">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
### <a name="allow-or-block-file"></a><span data-ttu-id="c7f19-219">Tillåta eller blockera fil</span><span class="sxs-lookup"><span data-stu-id="c7f19-219">Allow or block file</span></span>

<span data-ttu-id="c7f19-220">När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en enhet i organisationen försöker köra den.</span><span class="sxs-lookup"><span data-stu-id="c7f19-220">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="c7f19-221">Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-221">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

<span data-ttu-id="c7f19-222">Mer [information om att](manage-indicators.md) blockera och höja aviseringar om filer finns i Hantera indikatorer.</span><span class="sxs-lookup"><span data-stu-id="c7f19-222">See [manage indicators](manage-indicators.md) for more details on blocking and raising alerts on files.</span></span>

<span data-ttu-id="c7f19-223">Ta bort indikatorn för att sluta blockera en fil.</span><span class="sxs-lookup"><span data-stu-id="c7f19-223">To stop blocking a file, remove the indicator.</span></span> <span data-ttu-id="c7f19-224">Det kan du göra via **åtgärden Redigera** indikator på filens profilsida.</span><span class="sxs-lookup"><span data-stu-id="c7f19-224">You can do so via the **Edit Indicator** action on the file's profile page.</span></span> <span data-ttu-id="c7f19-225">Den här åtgärden visas i samma position som lägg till **indikator,** innan du lagt till indikatorn.</span><span class="sxs-lookup"><span data-stu-id="c7f19-225">This action will be visible in the same position as the **Add Indicator** action, before you added the indicator.</span></span>

<span data-ttu-id="c7f19-226">Du kan också redigera indikatorer från **sidan Inställningar,** under   >  **Regelindikatorer.**</span><span class="sxs-lookup"><span data-stu-id="c7f19-226">You can also edit indicators from  the **Settings** page, under **Rules** > **Indicators**.</span></span> <span data-ttu-id="c7f19-227">Indikatorer visas i det här området efter filens hash-kod.</span><span class="sxs-lookup"><span data-stu-id="c7f19-227">Indicators are listed in this area by their file's hash.</span></span>

## <a name="consult-a-threat-expert"></a><span data-ttu-id="c7f19-228">Kontakta en hotexpert</span><span class="sxs-lookup"><span data-stu-id="c7f19-228">Consult a threat expert</span></span>

<span data-ttu-id="c7f19-229">Kontakta en Microsoft-expert för att få mer information om en potentiellt komprometterad enhet eller redan komprometterade enheter.</span><span class="sxs-lookup"><span data-stu-id="c7f19-229">Consult a Microsoft threat expert for more insights on a potentially compromised device, or already compromised devices.</span></span> <span data-ttu-id="c7f19-230">Microsoft Threat Experts är direkt engagerade i Säkerhetscenter i Microsoft Defender för att få snabba och korrekta svar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-230">Microsoft Threat Experts are engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="c7f19-231">Experter ger insikter på en potentiellt komprometterad enhet och hjälper dig att förstå komplexa hot och riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c7f19-231">Experts provide insights on a potentially compromised device and help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="c7f19-232">De kan också tillhandahålla information om aviseringar eller ett informationssammanhang för hot som visas på din portalinstrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="c7f19-232">They can also provide information about the alerts or a threat intelligence context that you see on your portal dashboard.</span></span>

<span data-ttu-id="c7f19-233">Mer [information finns i Kontakta en Microsoft Threat Expert.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c7f19-233">See [Consult a Microsoft Threat Expert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) for details.</span></span>

## <a name="check-activity-details-in-action-center"></a><span data-ttu-id="c7f19-234">Kontrollera aktivitetsinformation i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="c7f19-234">Check activity details in Action center</span></span>

<span data-ttu-id="c7f19-235">I **Åtgärdscenter** finns information om åtgärder som har vidtagits på en enhet eller en fil.</span><span class="sxs-lookup"><span data-stu-id="c7f19-235">The **Action center** provides information on actions that were taken on a device or file.</span></span> <span data-ttu-id="c7f19-236">Du kan visa följande information:</span><span class="sxs-lookup"><span data-stu-id="c7f19-236">You can view the following details:</span></span>

- <span data-ttu-id="c7f19-237">Samling av undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="c7f19-237">Investigation package collection</span></span>
- <span data-ttu-id="c7f19-238">Antivirussökning</span><span class="sxs-lookup"><span data-stu-id="c7f19-238">Antivirus scan</span></span>
- <span data-ttu-id="c7f19-239">Appbegränsning</span><span class="sxs-lookup"><span data-stu-id="c7f19-239">App restriction</span></span>
- <span data-ttu-id="c7f19-240">Enhetsisolering</span><span class="sxs-lookup"><span data-stu-id="c7f19-240">Device isolation</span></span>

<span data-ttu-id="c7f19-241">All annan relaterad information visas också, till exempel datum/tid för inskickning, skickande av användare och om åtgärden lyckades eller misslyckades.</span><span class="sxs-lookup"><span data-stu-id="c7f19-241">All other related details are also shown, such as submission date/time, submitting user, and if the action succeeded or failed.</span></span>

![Bild på åtgärdscenter med information](images/action-center-details.png)

## <a name="deep-analysis"></a><span data-ttu-id="c7f19-243">Djupanalys</span><span class="sxs-lookup"><span data-stu-id="c7f19-243">Deep analysis</span></span>

<span data-ttu-id="c7f19-244">Cybersäkerhetsundersökningar utlöses vanligtvis av en varning.</span><span class="sxs-lookup"><span data-stu-id="c7f19-244">Cyber security investigations are typically triggered by an alert.</span></span> <span data-ttu-id="c7f19-245">Aviseringar är relaterade till en eller flera observerade filer som ofta är nya eller okända.</span><span class="sxs-lookup"><span data-stu-id="c7f19-245">Alerts are related to one or more observed files that are often new or unknown.</span></span> <span data-ttu-id="c7f19-246">När du markerar en fil kommer du till filvyn där du kan se filens metadata.</span><span class="sxs-lookup"><span data-stu-id="c7f19-246">Selecting a file takes you to the file view where you can see the file's metadata.</span></span> <span data-ttu-id="c7f19-247">Om du vill utöka data som är relaterade till filen kan du skicka filen för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="c7f19-247">To enrich the data related to the file, you can submit the file for deep analysis.</span></span>

<span data-ttu-id="c7f19-248">Djupanalysfunktionen kör en fil i en säker, fullständigt instrumenterad molnmiljö.</span><span class="sxs-lookup"><span data-stu-id="c7f19-248">The Deep analysis feature executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="c7f19-249">Djupanalysresultat visar filens aktiviteter, observerade beteenden och tillhörande artefakter, till exempel neds ignorerade filer, registerändringar och kommunikation med IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7f19-249">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IPs.</span></span>
<span data-ttu-id="c7f19-250">Djupanalys stöder för närvarande omfattande analys av PE-filer (Portable Executable) (inklusive _.exe-_ och _.dll-filer)._</span><span class="sxs-lookup"><span data-stu-id="c7f19-250">Deep analysis currently supports extensive analysis of portable executable (PE) files (including _.exe_ and _.dll_ files).</span></span>

<span data-ttu-id="c7f19-251">Djupanalys av en fil tar flera minuter.</span><span class="sxs-lookup"><span data-stu-id="c7f19-251">Deep analysis of a file takes several minutes.</span></span> <span data-ttu-id="c7f19-252">När filanalysen är klar uppdateras fliken Djupanalys för att visa en sammanfattning och datum och tid för de senaste tillgängliga resultaten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-252">Once the file analysis is complete, the Deep Analysis tab will update to display a summary and the date and time of the latest available results.</span></span>

<span data-ttu-id="c7f19-253">Den djupa analyssammanfattningen innehåller en lista över observerade beteenden *,* en del av dem kan indikera skadlig aktivitet och *observerbara*, inklusive kontaktade IP-adresser och filer som skapats på disken.</span><span class="sxs-lookup"><span data-stu-id="c7f19-253">The deep analysis summary includes a list of observed *behaviors*, some of which can indicate malicious activity, and *observables*, including contacted IPs and files created on the disk.</span></span> <span data-ttu-id="c7f19-254">Om inget hittas visas ett kort meddelande i de här avsnitten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-254">If nothing was found, these sections will display a brief message.</span></span>

<span data-ttu-id="c7f19-255">Resultat av djupanalys matchas mot hotinformation och eventuella matchningar genererar lämpliga varningar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-255">Results of deep analysis are matched against threat intelligence and any matches will generate appropriate alerts.</span></span>

<span data-ttu-id="c7f19-256">Använd funktionen djupanalys för att undersöka information om en fil, vanligtvis under en undersökning av en varning eller av någon annan anledning där du misstänker skadligt beteende.</span><span class="sxs-lookup"><span data-stu-id="c7f19-256">Use the deep analysis feature to investigate the details of any file, usually during an investigation of an alert or for any other reason where you suspect malicious behavior.</span></span> <span data-ttu-id="c7f19-257">Den här funktionen är **tillgänglig på fliken** Djupanalys på filens profilsida.</span><span class="sxs-lookup"><span data-stu-id="c7f19-257">This feature is available within the **Deep analysis** tab, on the file's profile page.</span></span><br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

<span data-ttu-id="c7f19-258">**Skicka för djupanalys** är aktiverat när filen är tillgänglig i Defender för slutpunktsbackend-exempelsamling, eller om den observerades på en Windows 10-enhet som har stöd för att skicka till djupanalys.</span><span class="sxs-lookup"><span data-stu-id="c7f19-258">**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submitting to deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f19-259">Endast filer från Windows 10 kan samlas in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c7f19-259">Only files from Windows 10 can be automatically collected.</span></span>

<span data-ttu-id="c7f19-260">Du kan också skicka ett exempel via [Microsoft Säkerhetscenter-portalen](https://www.microsoft.com/security/portal/submission/submit.aspx) om filen inte observerades på en Windows 10-enhet och vänta på att Skicka för **djupanalysknappen** blir tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c7f19-260">You can also submit a sample through the [Microsoft Security Center Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) if the file wasn't observed on a Windows 10 device, and wait for **Submit for deep analysis** button to become available.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f19-261">På grund av flöden för backend-bearbetning i Microsoft Security Center-portalen kan det finnas upp till 10 minuters fördröjning mellan filinskick och tillgängligheten för den djupanalysfunktion som finns i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="c7f19-261">Due to backend processing flows in the Microsoft Security Center Portal, there could be up to 10 minutes of latency between file submission and availability of the deep analysis feature in Defender for Endpoint.</span></span>

<span data-ttu-id="c7f19-262">När exemplet samlas in kör Defender för Slutpunkt filen i en säker miljö.</span><span class="sxs-lookup"><span data-stu-id="c7f19-262">When the sample is collected, Defender for Endpoint runs the file in a secure environment.</span></span> <span data-ttu-id="c7f19-263">Sedan skapas en detaljerad rapport över observerade beteenden och associerade artefakter, till exempel filer som släppts på enheter, kommunikation till IP-adresser och registerändringar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-263">It then creates a detailed report of observed behaviors and associated artifacts, such as files dropped on devices, communication to IPs, and registry modifications.</span></span>

### <a name="submit-files-for-deep-analysis"></a><span data-ttu-id="c7f19-264">Skicka filer för djupanalys</span><span class="sxs-lookup"><span data-stu-id="c7f19-264">Submit files for deep analysis</span></span>

1. <span data-ttu-id="c7f19-265">Välj den fil som du vill skicka för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="c7f19-265">Select the file that you want to submit for deep analysis.</span></span> <span data-ttu-id="c7f19-266">Du kan välja eller söka i en fil från någon av följande vyer:</span><span class="sxs-lookup"><span data-stu-id="c7f19-266">You can select or search a file from any of the following views:</span></span>

    - <span data-ttu-id="c7f19-267">Aviseringar – välj fillänkarna från **beskrivningen eller** **informationen på** tidslinjen Artefakt</span><span class="sxs-lookup"><span data-stu-id="c7f19-267">Alerts - select the file links from the **Description** or **Details** in the Artifact timeline</span></span>
    - <span data-ttu-id="c7f19-268">**Listan Enheter** – välj fillänkarna i **avsnittet** **Beskrivning eller** Information i avsnittet **Enhet i** organisation</span><span class="sxs-lookup"><span data-stu-id="c7f19-268">**Devices list** - select the file links from the **Description** or **Details** in the **Device in organization** section</span></span>
    - <span data-ttu-id="c7f19-269">Sökrutan – **välj** Arkiv i den nedrullningsmenyn och ange filnamnet</span><span class="sxs-lookup"><span data-stu-id="c7f19-269">Search box - select **File** from the drop–down menu and enter the file name</span></span>

2. <span data-ttu-id="c7f19-270">På fliken **Djupanalys** i filvyn väljer du **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="c7f19-270">In the **Deep analysis** tab of the file view, select **Submit**.</span></span>

   ![Du kan bara skicka PE-filer i avsnittet filinformation](images/submit-file.png)

   > [!NOTE]
   > <span data-ttu-id="c7f19-272">Endast PE-filer stöds, inklusive _.exe-_ och _.dll-filer._</span><span class="sxs-lookup"><span data-stu-id="c7f19-272">Only PE files are supported, including _.exe_ and _.dll_ files.</span></span>

<span data-ttu-id="c7f19-273">En förloppsfält visas med information om de olika stegen i analysen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-273">A progress bar is displayed and provides information on the different stages of the analysis.</span></span> <span data-ttu-id="c7f19-274">Du kan sedan visa rapporten när analysen är klar.</span><span class="sxs-lookup"><span data-stu-id="c7f19-274">You can then view the report when the analysis is done.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f19-275">Exempel på samlingstid kan variera beroende på enhetens tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="c7f19-275">Depending on device availability, sample collection time can vary.</span></span> <span data-ttu-id="c7f19-276">Det finns en tidsgräns på 3 timmar för exempelsamling.</span><span class="sxs-lookup"><span data-stu-id="c7f19-276">There is a 3–hour timeout for sample collection.</span></span> <span data-ttu-id="c7f19-277">Samlingen misslyckas och åtgärden avbryts om det inte finns någon Windows 10-enhetsrapportering online vid den tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-277">The collection will fail and the operation will abort if there is no online Windows 10 device reporting at that time.</span></span> <span data-ttu-id="c7f19-278">Du kan skicka filer igen för djupanalys för att hämta nya data i filen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-278">You can re–submit files for deep analysis to get fresh data on the file.</span></span>

### <a name="view-deep-analysis-reports"></a><span data-ttu-id="c7f19-279">Visa djupanalysrapporter</span><span class="sxs-lookup"><span data-stu-id="c7f19-279">View deep analysis reports</span></span>

<span data-ttu-id="c7f19-280">Visa den angivna djupanalysrapporten för att se mer djupgående information om filen du skickade.</span><span class="sxs-lookup"><span data-stu-id="c7f19-280">View the provided deep analysis report to see more in-depth insights on the file you submitted.</span></span> <span data-ttu-id="c7f19-281">Den här funktionen är tillgänglig i filvykontexten.</span><span class="sxs-lookup"><span data-stu-id="c7f19-281">This feature is available in the file view context.</span></span>

<span data-ttu-id="c7f19-282">Du kan visa den omfattande rapporten som innehåller information om följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="c7f19-282">You can view the comprehensive report that provides details on the following sections:</span></span>

- <span data-ttu-id="c7f19-283">Beteenden</span><span class="sxs-lookup"><span data-stu-id="c7f19-283">Behaviors</span></span>
- <span data-ttu-id="c7f19-284">Observables</span><span class="sxs-lookup"><span data-stu-id="c7f19-284">Observables</span></span>

<span data-ttu-id="c7f19-285">Informationen som ges kan hjälpa dig att undersöka om det finns uppgifter om en potentiell attack.</span><span class="sxs-lookup"><span data-stu-id="c7f19-285">The details provided can help you investigate if there are indications of a potential attack.</span></span>

1. <span data-ttu-id="c7f19-286">Välj filen du skickade för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="c7f19-286">Select the file you submitted for deep analysis.</span></span>
2. <span data-ttu-id="c7f19-287">Välj **fliken Djupanalys.** Om det finns tidigare rapporter visas rapportsammanfattningen på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="c7f19-287">Select the **Deep analysis** tab. If there are any previous reports, the report summary will appear in this tab.</span></span>

    ![Den djupa analysrapporten visar detaljerad information för ett antal kategorier](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a><span data-ttu-id="c7f19-289">Felsöka djupanalys</span><span class="sxs-lookup"><span data-stu-id="c7f19-289">Troubleshoot deep analysis</span></span>

<span data-ttu-id="c7f19-290">Om du får problem när du försöker skicka en fil kan du prova följande felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="c7f19-290">If you come across a problem when trying to submit a file, try each of the following troubleshooting steps.</span></span>

1. <span data-ttu-id="c7f19-291">Kontrollera att filen i fråga är en PE-fil.</span><span class="sxs-lookup"><span data-stu-id="c7f19-291">Ensure that the file in question is a PE file.</span></span> <span data-ttu-id="c7f19-292">PE-filer har vanligtvis _filnamnstilläggen .exe_ eller _.dll_ (körbara program eller program).</span><span class="sxs-lookup"><span data-stu-id="c7f19-292">PE files typically have _.exe_ or _.dll_ extensions (executable programs or applications).</span></span>
2. <span data-ttu-id="c7f19-293">Kontrollera att tjänsten har åtkomst till filen, att den fortfarande finns och inte har skadats eller ändrats.</span><span class="sxs-lookup"><span data-stu-id="c7f19-293">Ensure the service has access to the file, that it still exists, and hasn't been corrupted or modified.</span></span>
3. <span data-ttu-id="c7f19-294">Vänta en stund och försök sedan skicka filen igen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-294">Wait a short while and try to submit the file again.</span></span> <span data-ttu-id="c7f19-295">Kön kan vara full eller det har uppstått ett tillfälligt anslutnings- eller kommunikationsfel.</span><span class="sxs-lookup"><span data-stu-id="c7f19-295">The queue may be full, or there was a temporary connection or communication error.</span></span>
4. <span data-ttu-id="c7f19-296">Om exempelsamlingsprincipen inte är konfigurerad är standardbeteendet att tillåta exempelsamling.</span><span class="sxs-lookup"><span data-stu-id="c7f19-296">If the sample collection policy isn't configured, then the default behavior is to allow sample collection.</span></span> <span data-ttu-id="c7f19-297">Om den är konfigurerad bör du kontrollera att principinställningen tillåter exempelinsamling innan du skickar filen igen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-297">If it's configured, then verify the policy setting allows sample collection before submitting the file again.</span></span> <span data-ttu-id="c7f19-298">När exempelsamlingen är konfigurerad kontrollerar du följande registervärde:</span><span class="sxs-lookup"><span data-stu-id="c7f19-298">When sample collection is configured, then check the following registry value:</span></span>

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. <span data-ttu-id="c7f19-299">Ändra organisationsenheten via grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="c7f19-299">Change the organizational unit through the Group Policy.</span></span> <span data-ttu-id="c7f19-300">Mer information finns i [Konfigurera med grupprincip.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="c7f19-300">For more information, see [Configure with Group Policy](configure-endpoints-gp.md).</span></span>
1. <span data-ttu-id="c7f19-301">Om de här stegen inte löser problemet kontaktar du [winatp@microsoft.com](mailto:winatp@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c7f19-301">If these steps do not resolve the issue, contact [winatp@microsoft.com](mailto:winatp@microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7f19-302">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c7f19-302">Related topics</span></span>

- [<span data-ttu-id="c7f19-303">Vidta svarsåtgärder på en enhet</span><span class="sxs-lookup"><span data-stu-id="c7f19-303">Take response actions on a device</span></span>](respond-machine-alerts.md)
- [<span data-ttu-id="c7f19-304">Undersöka filer</span><span class="sxs-lookup"><span data-stu-id="c7f19-304">Investigate files</span></span>](investigate-files.md)