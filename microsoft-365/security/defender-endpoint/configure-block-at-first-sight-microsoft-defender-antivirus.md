---
title: Aktivera spärr vid första synen för att upptäcka skadlig programvara efter bara några sekunder
description: Aktivera funktionen för blockering vid första synen för att identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanning, blockera vid första synen, skadlig kod, första synen, molnet, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079209"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="ab2a6-104">Aktivera blockera direkt</span><span class="sxs-lookup"><span data-stu-id="ab2a6-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab2a6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab2a6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab2a6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ab2a6-107">I den här artikeln beskrivs en antivirus-/antimalware-funktion som kallas "block vid första synen" och beskriver hur du aktiverar blockering vid första synen för organisationen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="ab2a6-108">Den här artikeln är avsedd för företagsadministratörer och IT-proffs som hanterar säkerhetsinställningar för organisationer.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="ab2a6-109">Om du inte är en enteprise-administratör eller IT-proffs men har frågor om block vid första anblicken, se Inte företagsadministratör eller [IT-proffs?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="ab2a6-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="ab2a6-110">Vad är "block vid första synen"?</span><span class="sxs-lookup"><span data-stu-id="ab2a6-110">What is "block at first sight"?</span></span>

<span data-ttu-id="ab2a6-111">Blockera vid första synen är en skyddfunktion i nästa generations skydd som identifierar ny skadlig programvara och blockerar den inom några sekunder.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="ab2a6-112">Blockera vid första synen är aktiverat när vissa säkerhetsinställningar är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="ab2a6-113">Dessa inställningar omfattar:</span><span class="sxs-lookup"><span data-stu-id="ab2a6-113">These settings include:</span></span>

- <span data-ttu-id="ab2a6-114">Moln levererat skydd;</span><span class="sxs-lookup"><span data-stu-id="ab2a6-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="ab2a6-115">Ett angivet exempel på en tidsgräns för sändning (t.ex. 50 sekunder). och</span><span class="sxs-lookup"><span data-stu-id="ab2a6-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="ab2a6-116">En hög filblockeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="ab2a6-117">I de flesta företag är de inställningar som krävs för att aktivera spärr vid första anblicken konfigurerade med Microsoft Defender Antivirus-distributioner.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="ab2a6-118">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="ab2a6-118">How it works</span></span>

<span data-ttu-id="ab2a6-119">När Microsoft Defender Antivirus stöter på en misstänkt men oupptäckta fil, uppstår ett problem i vårt molnskyddsbackend.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="ab2a6-120">I molnbackend används heuristics, maskininlärning och automatiserad analys av filen för att avgöra om filerna är skadliga eller inte som ett hot.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="ab2a6-121">Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, intelligent och realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="ab2a6-123">Mer information finns i den här bloggen: Lär känna den avancerade tekniken som ligger till grund för nästa generations skydd [i Microsoft Defender för Slutpunkt.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="ab2a6-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="ab2a6-124">Några saker du bör veta om block vid första synen</span><span class="sxs-lookup"><span data-stu-id="ab2a6-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="ab2a6-125">I Windows 10, version 1803 eller senare, kan block vid första anblicken blockera icke-bärbara körbara filer (t.ex. JS, VBS eller makron) och körbara filer.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="ab2a6-126">Spärr vid första anblicken använder bara molnskyddsbackend för körbara filer och icke-bärbara körbara filer som laddas ned från Internet eller som kommer från Internetzonen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="ab2a6-127">Ett hashvärde för EXE-filen kontrolleras via molnbackend för att fastställa om filen är en tidigare oupptäckta fil.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="ab2a6-128">Om molnbackend inte kan avgöra något låses filen och en kopia laddas upp till molnet av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="ab2a6-129">Molnet utför mer analys för att nå ett avgörande innan det antingen gör det möjligt att köra filen eller blockerar den i alla framtida möten, beroende på om filen är skadlig eller inte som ett hot.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="ab2a6-130">I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="ab2a6-131">Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="ab2a6-132">Du kan också [anpassa meddelandet som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="ab2a6-133">Du kan ändra företagets namn, kontaktinformation och meddelande-URL.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="ab2a6-134">Aktivera blockera vid första synen med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab2a6-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="ab2a6-135">Microsoft Intune ingår nu i Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="ab2a6-136">Gå till Konfigurationsprofiler för enheter i administrationscentret för Microsoft Endpoint [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  **Manager**( ).</span><span class="sxs-lookup"><span data-stu-id="ab2a6-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="ab2a6-137">Välj eller skapa en profil med **profiltypen** Enhetsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="ab2a6-138">I **konfigurationsinställningarna** för profilen För enhetsbegränsningar anger eller bekräftar du följande inställningar under **Microsoft Defender Antivirus:**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="ab2a6-139">**Moln levererat skydd**: Aktiverat</span><span class="sxs-lookup"><span data-stu-id="ab2a6-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="ab2a6-140">**Blockeringsnivå för filer:** hög</span><span class="sxs-lookup"><span data-stu-id="ab2a6-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="ab2a6-141">**Tidstillägg för filsökning i molnet:** 50</span><span class="sxs-lookup"><span data-stu-id="ab2a6-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="ab2a6-142">**Fråga användarna innan exempel skickas:** Skicka alla data utan att fråga</span><span class="sxs-lookup"><span data-stu-id="ab2a6-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune-konfiguration](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="ab2a6-144">Spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="ab2a6-145">Om du ställer in blockeringsnivån **Hög** tillämpas en stark identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="ab2a6-146">Om en filblockering orsakar en falsk positiv identifiering av legitima filer kan ditt säkerhetsteam återställa filer i karantän som då [blockeras.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ab2a6-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="ab2a6-147">Mer information om hur du konfigurerar begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Konfigurera inställningar [för enhetsbegränsning i Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="ab2a6-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="ab2a6-148">En lista över begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Enhetsbegränsning för [Windows 10-inställningar (och nyare) i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="ab2a6-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="ab2a6-149">Aktivera block vid första synen med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ab2a6-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="ab2a6-150">Om du letar efter Microsoft Endpoint Configuration Manager är det nu en del av Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="ab2a6-151">Gå till Slutpunktssäkerhetsantivirusprogram i Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  ).</span><span class="sxs-lookup"><span data-stu-id="ab2a6-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="ab2a6-152">Välj en befintlig princip eller skapa en ny princip med profiltypen **Microsoft Defender** Antivirus.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="ab2a6-153">Ange eller bekräfta följande konfigurationsinställningar:</span><span class="sxs-lookup"><span data-stu-id="ab2a6-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="ab2a6-154">**Aktivera moln levererat skydd**: Ja</span><span class="sxs-lookup"><span data-stu-id="ab2a6-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="ab2a6-155">**Moln levererat skyddsnivå**: Hög</span><span class="sxs-lookup"><span data-stu-id="ab2a6-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="ab2a6-156">**Utökad tidsgräns för Defender Cloud på några sekunder**: 50</span><span class="sxs-lookup"><span data-stu-id="ab2a6-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Inställningar för spärr vid första synen i Slutpunktshanteraren":::

4. <span data-ttu-id="ab2a6-158">Använd Microsoft Defender Antivirus-profilen för en grupp, till exempel **Alla användare,** **Alla enheter** eller Alla användare **och enheter.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="ab2a6-159">Aktivera blockera vid första synen med Grupprincip</span><span class="sxs-lookup"><span data-stu-id="ab2a6-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="ab2a6-160">Vi rekommenderar att du använder Intune eller Microsoft Endpoint Manager för att aktivera block vid första synen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="ab2a6-161">Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="ab2a6-162">Med **redigeraren för hantering av grupprinciper** går du **till Administrativa mallar** för  >    >  **datorkonfiguration Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="ab2a6-163">I avsnittet KARTOR dubbelklickar du på Konfigurera funktionen "Blockera vid första **synen"** och ställer in den på **Aktiverad**. Välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ab2a6-164">Om du **ställer in på Fråga alltid (0)** sänks enhetens skyddstillstånd.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="ab2a6-165">Inställning till **Skicka aldrig (2) innebär** att blocket vid första synen inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="ab2a6-166">I avsnittet KARTOR dubbelklickar du på **Skicka filexempel när vidare analys krävs** och ställer in det på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="ab2a6-167">Under **Skicka filexempel när ytterligare analys krävs** väljer du Skicka alla **exempel** och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="ab2a6-168">Distribuera om grupprincipobjektet i nätverket på det sätt du brukar.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="ab2a6-169">Bekräfta att blocket vid första synen är aktiverat på enskilda klientenheter</span><span class="sxs-lookup"><span data-stu-id="ab2a6-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="ab2a6-170">Du kan bekräfta att blocket vid första synen är aktiverat på enskilda klientenheter med hjälp av Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="ab2a6-171">Spärr vid första synen aktiveras automatiskt så länge som **moln levererat skydd och** automatisk **sändning** av stickprov är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="ab2a6-172">Öppna Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="ab2a6-173">Välj **Virus & skydd mot hot** och välj sedan Hantera & inställningar för skydd mot **&** **virushot**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="ab2a6-175">Bekräfta att **skydd mot moln levererat och** automatisk **exempelinskickning** båda är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="ab2a6-176">Om de nödvändiga inställningarna konfigureras och distribueras med grupprincip kommer inställningarna som beskrivs i det här avsnittet att vara nedtonade och inte tillgängliga för användning i enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="ab2a6-177">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningar.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="ab2a6-178">Verifiera att blocket vid första synen fungerar</span><span class="sxs-lookup"><span data-stu-id="ab2a6-178">Validate block at first sight is working</span></span>

<span data-ttu-id="ab2a6-179">Verifiera att funktionen fungerar genom att följa instruktionerna i [Verifiera anslutningar mellan nätverket och molnet.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="ab2a6-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="ab2a6-180">Inaktivera block vid första synen</span><span class="sxs-lookup"><span data-stu-id="ab2a6-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="ab2a6-181">Om du stänger av block vid första synen sänks skyddstillståndet för dina enheter och ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="ab2a6-182">Du kan välja att inaktivera blocket vid första synen om du vill behålla de nödvändiga inställningarna utan att använda skydd vid första synen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="ab2a6-183">Du kan tillfälligt stänga av spärren vid första synen för att se hur den här funktionen påverkar nätverket.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="ab2a6-184">Vi rekommenderar dock inte att spärrskyddet för första synen inaktiveras permanent.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="ab2a6-185">Inaktivera blocket vid första synen med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ab2a6-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="ab2a6-186">Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="ab2a6-187">Gå till **Endpoint Security**  >  **Antivirus** och välj sedan din Microsoft Defender Antivirus-policy.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="ab2a6-188">Välj **Egenskaper** under **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="ab2a6-189">Välj **Redigera bredvid** **Konfigurationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="ab2a6-190">Ändra en eller flera av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ab2a6-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="ab2a6-191">Ställ **in Aktivera moln levererat skydd till** **Nej** eller **Inte konfigurerat.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="ab2a6-192">Ställ **in skyddsnivån Moln levererat till** Ej **konfigurerad**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="ab2a6-193">Avmarkera kryssrutan för den utökade **tidsgränsen för Defender Cloud efter några sekunder.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="ab2a6-194">Granska och spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="ab2a6-195">Inaktivera blocket vid första synen med Grupprincip</span><span class="sxs-lookup"><span data-stu-id="ab2a6-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="ab2a6-196">På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och väljer **sedan Redigera.**</span><span class="sxs-lookup"><span data-stu-id="ab2a6-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="ab2a6-197">Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="ab2a6-198">Expandera trädet med **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="ab2a6-199">Dubbelklicka på Konfigurera **funktionen "Spärr vid första synen"** och ställ in alternativet på **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab2a6-200">Om du inaktiverar blocket vid första synen inaktiveras inte nödvändiga gruppprinciper.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="ab2a6-201">Är du inte företagsadministratör eller IT-proffs?</span><span class="sxs-lookup"><span data-stu-id="ab2a6-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="ab2a6-202">Om du inte är företagsadministratör eller IT-proffs, men har frågor om block vid första anblicken, är det här avsnittet för dig.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="ab2a6-203">Blockera vid första synen är en skyddfunktion för hot som identifierar och blockerar skadlig programvara inom några sekunder.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="ab2a6-204">Även om det inte finns en viss inställning som kallas "Blockera vid första anblicken" är funktionen aktiverad när vissa inställningar är konfigurerade på enheten.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="ab2a6-205">Hur du hanterar blockering vid första synen på eller av på din egen enhet</span><span class="sxs-lookup"><span data-stu-id="ab2a6-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="ab2a6-206">Om du har en personlig enhet som inte hanteras av en organisation kanske du undrar hur du aktiverar eller inaktiverar blockering vid första anblicken.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="ab2a6-207">Du kan använda Windows-säkerhetsappen för att hantera blocket vid första synen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="ab2a6-208">Öppna appen Windows-säkerhet på din Windows 10-dator.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="ab2a6-209">Välj **Skydd mot & och hot**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="ab2a6-210">Under **Inställningar & skydd mot virus och** hot väljer du Hantera **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="ab2a6-211">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="ab2a6-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="ab2a6-212">För att aktivera spärr vid första synen ska du se till att både **molnskydd och** **automatisk sändning** av stickprov är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="ab2a6-213">Inaktivera blocket vid första synen genom att inaktivera **moln levererat skydd eller** automatisk **exempelindata**.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="ab2a6-214">Om du stänger av block vid första synen sänks skyddsnivån för din enhet.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="ab2a6-215">Vi rekommenderar inte att blocket inaktiveras permanent vid första synen.</span><span class="sxs-lookup"><span data-stu-id="ab2a6-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ab2a6-216">Se även</span><span class="sxs-lookup"><span data-stu-id="ab2a6-216">See also</span></span>

- [<span data-ttu-id="ab2a6-217">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab2a6-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="ab2a6-218">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="ab2a6-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ab2a6-219">Skydda dig med Windows-säkerhet</span><span class="sxs-lookup"><span data-stu-id="ab2a6-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)