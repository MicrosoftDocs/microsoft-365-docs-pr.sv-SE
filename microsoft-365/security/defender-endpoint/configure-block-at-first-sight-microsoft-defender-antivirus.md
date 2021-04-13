---
title: Aktivera spärr vid första synen för att upptäcka skadlig programvara efter bara några sekunder
description: Aktivera funktionen för blockering vid första synen för att identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanna, BAFS, skadlig programvara, visas först, första synen, molnet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691568"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="9b306-104">Aktivera block vid första synen</span><span class="sxs-lookup"><span data-stu-id="9b306-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b306-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9b306-105">**Applies to:**</span></span>

- [<span data-ttu-id="9b306-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b306-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9b306-107">Blockering vid första synen är ett sätt att identifiera och blockera ny skadlig programvara inom några sekunder.</span><span class="sxs-lookup"><span data-stu-id="9b306-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="9b306-108">Skyddet aktiveras som standard när vissa nödvändiga inställningar är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="9b306-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="9b306-109">De här inställningarna omfattar moln levererat skydd, en angiven tidsgräns för sändning (t.ex. 50 sekunder) och en nivå av hög filblockering.</span><span class="sxs-lookup"><span data-stu-id="9b306-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="9b306-110">I de flesta företag är de här inställningarna aktiverade som standard med distributioner av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b306-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="9b306-111">Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen.</span><span class="sxs-lookup"><span data-stu-id="9b306-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="9b306-112">Du kan också [anpassa meddelandet som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras.</span><span class="sxs-lookup"><span data-stu-id="9b306-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="9b306-113">Du kan ändra företagets namn, kontaktinformation och meddelande-URL.</span><span class="sxs-lookup"><span data-stu-id="9b306-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="9b306-114">Besök microsoft Defender för slutpunktens demowebbplats på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) bekräfta att funktionerna fungerar och se hur de fungerar.</span><span class="sxs-lookup"><span data-stu-id="9b306-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="9b306-115">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="9b306-115">How it works</span></span>

<span data-ttu-id="9b306-116">När Microsoft Defender Antivirus stöter på en misstänkt men oupptäckta fil, uppstår ett problem i vårt molnskyddsbackend.</span><span class="sxs-lookup"><span data-stu-id="9b306-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="9b306-117">I molnbackend används heuristics, maskininlärning och automatiserad analys av filen för att avgöra om filerna är skadliga eller inte som ett hot.</span><span class="sxs-lookup"><span data-stu-id="9b306-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="9b306-118">Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, intelligent och realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="9b306-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="9b306-119">Mer information finns i den här bloggen: Lär känna den avancerade tekniken som ligger till grund för nästa generations skydd [i Microsoft Defender för Slutpunkt.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="9b306-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="9b306-120">![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="9b306-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="9b306-121">I Windows 10, version 1803 eller senare, kan blockering vid första anblicken blockera icke-bärbara körbara filer (t.ex. JS, VBS eller makron) samt körbara filer.</span><span class="sxs-lookup"><span data-stu-id="9b306-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="9b306-122">Spärr vid första anblicken använder bara molnskyddsbackend för körbara filer och icke-bärbara körbara filer som laddas ned från Internet eller som kommer från Internetzonen.</span><span class="sxs-lookup"><span data-stu-id="9b306-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="9b306-123">Ett hashvärde för EXE-filen kontrolleras via molnbackend för att fastställa om filen är en tidigare oupptäckta fil.</span><span class="sxs-lookup"><span data-stu-id="9b306-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="9b306-124">Om molnbackend inte kan avgöra något låses filen och en kopia laddas upp till molnet av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b306-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="9b306-125">Molnet utför ytterligare analyser för att nå ett avgörande innan det antingen gör det möjligt att köra filen eller blockerar den i alla framtida möten, beroende på om filen är skadlig eller säker.</span><span class="sxs-lookup"><span data-stu-id="9b306-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="9b306-126">I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.</span><span class="sxs-lookup"><span data-stu-id="9b306-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="9b306-127">Aktivera blockera vid första synen med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9b306-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="9b306-128">Microsoft Intune ingår nu i Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9b306-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="9b306-129">Gå till Konfigurationsprofiler för enheter i administrationscentret för Microsoft Endpoint [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  **Manager**( ).</span><span class="sxs-lookup"><span data-stu-id="9b306-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="9b306-130">Välj eller skapa en profil med **profiltypen** Enhetsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="9b306-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="9b306-131">I **konfigurationsinställningarna** för profilen För enhetsbegränsningar anger eller bekräftar du följande inställningar under **Microsoft Defender Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="9b306-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="9b306-132">**Moln levererat skydd**: Aktiverat</span><span class="sxs-lookup"><span data-stu-id="9b306-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="9b306-133">**Blockeringsnivå för filer:** hög</span><span class="sxs-lookup"><span data-stu-id="9b306-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="9b306-134">**Tidstillägg för filsökning i molnet:** 50</span><span class="sxs-lookup"><span data-stu-id="9b306-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="9b306-135">**Fråga användarna innan exempel skickas:** Skicka alla data utan att fråga</span><span class="sxs-lookup"><span data-stu-id="9b306-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune-konfiguration](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="9b306-137">Spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9b306-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="9b306-138">Om du ställer in blockeringsnivån **Hög** tillämpas en stark identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="9b306-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="9b306-139">Om filblockering orsakar en falsk positiv identifiering av legitima filer kan du återställa filer i karantän om så inte är [möjligt.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9b306-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="9b306-140">Mer information om hur du konfigurerar begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Konfigurera inställningar [för enhetsbegränsning i Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="9b306-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="9b306-141">En lista över begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Enhetsbegränsning för [Windows 10-inställningar (och nyare) i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="9b306-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="9b306-142">Aktivera block vid första synen med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9b306-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="9b306-143">Om du letar efter Microsoft Endpoint Configuration Manager är det nu en del av Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9b306-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="9b306-144">Gå till Slutpunktssäkerhetsantivirusprogram i Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  ).</span><span class="sxs-lookup"><span data-stu-id="9b306-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="9b306-145">Välj en befintlig princip eller skapa en ny princip med profiltypen **Microsoft Defender** Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b306-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="9b306-146">Ange eller bekräfta följande konfigurationsinställningar:</span><span class="sxs-lookup"><span data-stu-id="9b306-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="9b306-147">**Aktivera moln levererat skydd**: Ja</span><span class="sxs-lookup"><span data-stu-id="9b306-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="9b306-148">**Moln levererat skyddsnivå**: Hög</span><span class="sxs-lookup"><span data-stu-id="9b306-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="9b306-149">**Utökad tidsgräns för Defender Cloud på några sekunder**: 50</span><span class="sxs-lookup"><span data-stu-id="9b306-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Inställningar för spärr vid första synen i Slutpunktshanteraren":::

4. <span data-ttu-id="9b306-151">Använd Microsoft Defender Antivirus-profilen för en grupp, till exempel **Alla användare,** **Alla enheter** eller Alla användare **och enheter.**</span><span class="sxs-lookup"><span data-stu-id="9b306-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="9b306-152">Aktivera blockera vid första synen med Grupprincip</span><span class="sxs-lookup"><span data-stu-id="9b306-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="9b306-153">Vi rekommenderar att du använder Intune eller Microsoft Endpoint Manager för att aktivera block vid första synen.</span><span class="sxs-lookup"><span data-stu-id="9b306-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="9b306-154">Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="9b306-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="9b306-155">Med **redigeraren för hantering av grupprinciper** går du **till Administrativa mallar** för  >    >  **datorkonfiguration Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="9b306-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="9b306-156">I avsnittet KARTOR dubbelklickar du på Konfigurera funktionen "Blockera vid första **synen"** och ställer in den på **Aktiverad**. Välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="9b306-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9b306-157">Om du **ställer in på Fråga alltid (0)** sänks enhetens skyddstillstånd.</span><span class="sxs-lookup"><span data-stu-id="9b306-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="9b306-158">Inställning till **Skicka aldrig (2) innebär** att blocket vid första synen inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="9b306-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="9b306-159">I avsnittet KARTOR dubbelklickar du på **Skicka filexempel när vidare analys krävs** och ställer in det på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="9b306-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="9b306-160">Under **Skicka filexempel när ytterligare analys krävs väljer** du Skicka alla **exempel** och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="9b306-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="9b306-161">Om du har ändrat några inställningar distribuerar du grupprincipobjektet igen över nätverket för att säkerställa att alla slutpunkter täcks.</span><span class="sxs-lookup"><span data-stu-id="9b306-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="9b306-162">Bekräfta att blocket vid första synen är aktiverat för enskilda klienter</span><span class="sxs-lookup"><span data-stu-id="9b306-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="9b306-163">Du kan kontrollera att blocket vid första synen är aktiverat för enskilda klienter med windows säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="9b306-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="9b306-164">Spärr vid första synen aktiveras automatiskt så länge som **moln levererat skydd och** automatisk **sändning** av stickprov är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="9b306-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="9b306-165">Öppna Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="9b306-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="9b306-166">Välj **Virus & skydd mot hot** och välj sedan Hantera & inställningar för skydd mot **&** **virushot**.</span><span class="sxs-lookup"><span data-stu-id="9b306-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="9b306-168">Bekräfta att **skydd mot moln levererat och** automatisk **exempelinskickning** båda är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9b306-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="9b306-169">Om de nödvändiga inställningarna konfigureras och distribueras med grupprincip kommer inställningarna som beskrivs i det här avsnittet att vara nedtonade och inte tillgängliga för användning i enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="9b306-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="9b306-170">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningar.</span><span class="sxs-lookup"><span data-stu-id="9b306-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="9b306-171">Verifiera att blocket vid första synen fungerar</span><span class="sxs-lookup"><span data-stu-id="9b306-171">Validate block at first sight is working</span></span>

<span data-ttu-id="9b306-172">Verifiera att funktionen fungerar genom att följa instruktionerna i [Verifiera anslutningar mellan nätverket och molnet.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="9b306-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="9b306-173">Inaktivera block vid första synen</span><span class="sxs-lookup"><span data-stu-id="9b306-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="9b306-174">Om du stänger av block vid första synen sänks skyddstillståndet för dina enheter och ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="9b306-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="9b306-175">Du kan välja att inaktivera blocket vid första synen om du vill behålla de nödvändiga inställningarna utan att använda skydd vid första synen.</span><span class="sxs-lookup"><span data-stu-id="9b306-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="9b306-176">Du kan tillfälligt stänga av blocket vid första synen om du har problem med svarstiden eller om du vill testa funktionens påverkan på nätverket.</span><span class="sxs-lookup"><span data-stu-id="9b306-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="9b306-177">Vi rekommenderar dock inte att spärrskyddet för första synen inaktiveras permanent.</span><span class="sxs-lookup"><span data-stu-id="9b306-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="9b306-178">Inaktivera blocket vid första synen med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9b306-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="9b306-179">Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="9b306-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="9b306-180">Gå till **Endpoint Security**  >  **Antivirus** och välj sedan din Microsoft Defender Antivirus-policy.</span><span class="sxs-lookup"><span data-stu-id="9b306-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="9b306-181">Välj **Egenskaper** under **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="9b306-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="9b306-182">Välj **Redigera bredvid** **Konfigurationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="9b306-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="9b306-183">Ändra en eller flera av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9b306-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="9b306-184">Ställ **in Aktivera moln levererat skydd till** **Nej** eller **Inte konfigurerat.**</span><span class="sxs-lookup"><span data-stu-id="9b306-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="9b306-185">Ställ **in skyddsnivån Moln levererat till** Ej **konfigurerad**.</span><span class="sxs-lookup"><span data-stu-id="9b306-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="9b306-186">Avmarkera kryssrutan **Utökad tidsgräns för Defender Cloud på några** sekunder.</span><span class="sxs-lookup"><span data-stu-id="9b306-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="9b306-187">Granska och spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9b306-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="9b306-188">Inaktivera blocket vid första synen med Grupprincip</span><span class="sxs-lookup"><span data-stu-id="9b306-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="9b306-189">På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar sedan på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="9b306-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="9b306-190">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="9b306-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9b306-191">Expandera trädet med **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="9b306-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="9b306-192">Dubbelklicka på Konfigurera **funktionen "Spärr vid första synen"** och ställ in alternativet på **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="9b306-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9b306-193">Om du inaktiverar blocket vid första synen inaktiveras inte nödvändiga gruppprinciper.</span><span class="sxs-lookup"><span data-stu-id="9b306-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b306-194">Se även</span><span class="sxs-lookup"><span data-stu-id="9b306-194">See also</span></span>

- [<span data-ttu-id="9b306-195">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="9b306-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="9b306-196">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="9b306-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)