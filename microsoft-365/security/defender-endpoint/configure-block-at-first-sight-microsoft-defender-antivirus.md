---
title: Aktivera Blockera när det först påträffas när du vill identifiera skadlig programvara på några sekunder
description: Aktivera funktionen Blockera när det först påträffas när du vill identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanna, blockera när det först påträffas, skadlig programvara, påträffas, moln, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007407"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="98740-104">Aktivera Blockera när det först påträffas</span><span class="sxs-lookup"><span data-stu-id="98740-104">Turn on block at first sight</span></span>

<span data-ttu-id="98740-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="98740-105">**Applies to:**</span></span>

- [<span data-ttu-id="98740-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="98740-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="98740-107">I den här artikeln beskrivs antivirus-/antimalware-funktionen som kallas Blockera när det först påträffas och hur du aktiverar Blockera när det först påträffas för din organisation.</span><span class="sxs-lookup"><span data-stu-id="98740-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="98740-108">Den här artikeln är avsedd för företagsadministratörer och IT-tekniker som hanterar säkerhetsinställningar för organisationer.</span><span class="sxs-lookup"><span data-stu-id="98740-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="98740-109">Om du inte är företagsadministratör eller IT-tekniker, men har frågor om Blockera när det först påträffas kan du läsa avsnittet[Är du inte företagsadministratör eller IT-tekniker?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="98740-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="98740-110">Vad är Blockera när det först påträffas?</span><span class="sxs-lookup"><span data-stu-id="98740-110">What is "block at first sight"?</span></span>

<span data-ttu-id="98740-111">Blockera när det först påträffas är en nästa generations funktion som skyddar mot hot genom att identifiera ny skadlig programvara och blockera den på några sekunder.</span><span class="sxs-lookup"><span data-stu-id="98740-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="98740-112">Blockera när det först påträffas aktiveras när vissa säkerhetsinställningar är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="98740-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="98740-113">Inställningarna omfattar:</span><span class="sxs-lookup"><span data-stu-id="98740-113">These settings include:</span></span>

- <span data-ttu-id="98740-114">molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="98740-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="98740-115">en angiven tidsgräns för sändning av exempel (t.ex. 50 sekunder) och</span><span class="sxs-lookup"><span data-stu-id="98740-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="98740-116">en hög filblockeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="98740-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="98740-117">I de flesta företag konfigureras inställningarna som krävs för att aktivera Blockera när det först påträffas i samband med Microsoft Defender Antivirus-distributioner.</span><span class="sxs-lookup"><span data-stu-id="98740-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="98740-118">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="98740-118">How it works</span></span>

<span data-ttu-id="98740-119">När Microsoft Defender Antivirus stöter på en misstänkt men oidentifierad fil, skickas en fråga till serverdelen för molnskydd.</span><span class="sxs-lookup"><span data-stu-id="98740-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="98740-120">I serverdelen för molnskydd tillämpas heuristik, maskininlärning och automatiska analyser på filen för att avgöra om den är skadlig eller inte.</span><span class="sxs-lookup"><span data-stu-id="98740-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="98740-121">Microsoft Defender Antivirus använder flera tekniker för identifiering och skydd för att ge exakt och intelligent skydd i realtid.</span><span class="sxs-lookup"><span data-stu-id="98740-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista över motorer för Microsoft Defender Antivirus](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="98740-123">Mer information finns i [ (Blogg) Lär känna de avancerade teknikerna i Microsoft Defender för Endpoint – nästa generations skydd](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="98740-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="98740-124">Några saker du bör veta om Blockera när det först påträffas</span><span class="sxs-lookup"><span data-stu-id="98740-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="98740-125">I Windows 10, version 1803 och senare, kan Blockera när det först påträffas blockera icke-portabla körbara filer (t.ex. JS, VBS eller makron) och körbara filer.</span><span class="sxs-lookup"><span data-stu-id="98740-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="98740-126">Blockera när det först påträffas använder bara serverdelen för molnskydd för körbara filer och icke-portabla körbara filer som laddas ned från internet eller som kommer från internetzonen.</span><span class="sxs-lookup"><span data-stu-id="98740-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="98740-127">Ett hashvärde för .exe-filen kontrolleras via den molnbaserade serverdelen för att avgöra om filen inte har identifierats tidigare.</span><span class="sxs-lookup"><span data-stu-id="98740-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="98740-128">Om molnserverdelen inte kan fastställa det kommer Microsoft Defender Antivirus att låsa filen och ladda upp en kopia till molnet.</span><span class="sxs-lookup"><span data-stu-id="98740-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="98740-129">I molnet utförs fler analyser för att fatta ett beslut om filen ska köras eller blockeras när den identifieras i framtiden, beroende på om den är skadlig eller inte.</span><span class="sxs-lookup"><span data-stu-id="98740-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="98740-130">I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.</span><span class="sxs-lookup"><span data-stu-id="98740-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="98740-131">Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen.</span><span class="sxs-lookup"><span data-stu-id="98740-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="98740-132">Du kan även [anpassa det meddelande som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras.</span><span class="sxs-lookup"><span data-stu-id="98740-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="98740-133">Du kan ändra företagets namn, kontaktinformation och meddelande-URL.</span><span class="sxs-lookup"><span data-stu-id="98740-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="98740-134">Aktivera Blockera när det först påträffas med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="98740-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="98740-135">Microsoft Intune är nu en del av Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="98740-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="98740-136">I administrationscentret för Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) går du till **Enheter** > **Konfigurationsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="98740-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="98740-137">Markera eller skapa en profil med profiltypen **Enhetsbegränsningar**.</span><span class="sxs-lookup"><span data-stu-id="98740-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="98740-138">I **Konfigurationsinställningar** för profilen Enhetsbegränsningar, anger eller bekräftar du följande inställningar under **Microsoft Defender Antivirus**:</span><span class="sxs-lookup"><span data-stu-id="98740-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="98740-139">**Molnbaserat skydd**: aktiverat </span><span class="sxs-lookup"><span data-stu-id="98740-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="98740-140">**Filblockeringsnivå**: hög</span><span class="sxs-lookup"><span data-stu-id="98740-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="98740-141">**Tidstillägg för genomsökning av filer via molnet**: 50</span><span class="sxs-lookup"><span data-stu-id="98740-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="98740-142">**Fråga användare innan exempel skickas**: skicka alla data utan att fråga</span><span class="sxs-lookup"><span data-stu-id="98740-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Konfigurationsblockering för Intune vid första anblicken":::

4. <span data-ttu-id="98740-144">Spara dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="98740-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="98740-145">Om du ställer in filblockeringsnivån på **Hög** används en hög identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="98740-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="98740-146">Om filblockering mot förmodan leder till falsk positiv identifiering av legitima filer kan säkerhetsteamet [återställa filer i karantän](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="98740-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="98740-147">Mer information om hur du konfigurerar enhetsbegränsningar för Microsoft Defender Antivirus i Intune finns i [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="98740-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="98740-148">En lista över enhetsbegränsningar för Microsoft Defender Antivirus i Intune finns i [Inställningar för enhetsbegränsning i Windows 10 (och senare) i Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="98740-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="98740-149">Aktivera Blockera när det först påträffas med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="98740-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="98740-150">Om du letar efter Microsoft Endpoint Configuration Manager så ingår det nu som en del av Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="98740-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="98740-151">I Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) går du till **Slutpunktssäkerhet** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="98740-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="98740-152">Markera en princip eller skapa en ny princip med profiltypen **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="98740-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="98740-153">Ange eller bekräfta följande konfigurationsinställningar:</span><span class="sxs-lookup"><span data-stu-id="98740-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="98740-154">**Aktivera molnbaserat skydd**: ja</span><span class="sxs-lookup"><span data-stu-id="98740-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="98740-155">**Skyddsnivå som levereras i molnet**: hög</span><span class="sxs-lookup"><span data-stu-id="98740-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="98740-156">**Utökad tidsgräns i Defender-moln i sekunder**: 50</span><span class="sxs-lookup"><span data-stu-id="98740-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Inställningar för Blockera när det först påträffas Endpoint Manager":::

4. <span data-ttu-id="98740-158">Tillämpa Microsoft Defender Antivirus-profilen på en grupp, till exempel **Alla användare**, **Alla enheter** eller **Alla användare och enheter**.</span><span class="sxs-lookup"><span data-stu-id="98740-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="98740-159">Aktivera Blockera när det först påträffas med en grupprincip</span><span class="sxs-lookup"><span data-stu-id="98740-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="98740-160">Vi rekommenderar att du använder Intune eller Microsoft Endpoint Manager för att aktivera Blockera när det först påträffas.</span><span class="sxs-lookup"><span data-stu-id="98740-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="98740-161">På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="98740-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="98740-162">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** > **Administrativa mallar** > **Windows-komponenter** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="98740-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="98740-163">I MAPS-avsnittet dubbelklickar du på **Konfigurera funktionen Blockera när det först påträffas**, anger **Aktiverad** och väljer **OK**.</span><span class="sxs-lookup"><span data-stu-id="98740-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98740-164">Om du väljer **Fråga alltid (0)** minskas skyddet på enheten.</span><span class="sxs-lookup"><span data-stu-id="98740-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="98740-165">Om du väljer **Skicka aldrig (2)** kommer Blockera när det först påträffas inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="98740-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="98740-166">I MAPS-avsnittet dubbelklickar du på **Skicka filexempel när ytterligare analys krävs** och anger **Aktiverat**.</span><span class="sxs-lookup"><span data-stu-id="98740-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="98740-167">Under **Skicka filexempel när ytterligare analys krävs** väljer du **Skicka alla exempel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="98740-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="98740-168">Distribuera grupprincipobjektet i nätverket som vanligt.</span><span class="sxs-lookup"><span data-stu-id="98740-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="98740-169">Bekräfta att Blockera när det först påträffas är aktiverat på enskilda klientenheter</span><span class="sxs-lookup"><span data-stu-id="98740-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="98740-170">Du kan kontrollera att Blockera när det först påträffas är aktiverat på enskilda klientenheter med Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="98740-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="98740-171">Blockera när det först påträffas aktiveras automatiskt så länge **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="98740-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="98740-172">Öppna Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="98740-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="98740-173">Välj **Skydd mot virus och hot** och under **Inställningar för skydd mot virus och hot** väljer du **Hantera inställningar**.</span><span class="sxs-lookup"><span data-stu-id="98740-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Skärmbild av inställningsetiketten för Skydd mot hot och virus i appen Windows-säkerhet":::

3. <span data-ttu-id="98740-175">Kontrollera att **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="98740-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="98740-176">Om de nödvändiga inställningarna konfigureras och distribueras med grupprinciper är inställningarna som beskrivs i det här avsnittet nedtonade och inte tillgängliga för användning på enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="98740-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="98740-177">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="98740-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="98740-178">Kontrollera att Blockera när det först påträffas fungerar</span><span class="sxs-lookup"><span data-stu-id="98740-178">Validate block at first sight is working</span></span>

<span data-ttu-id="98740-179">Om du vill verifiera att funktionen fungerar laddar du ned exempelfilen [Blockera exempelfil vid första anblicken](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="98740-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="98740-180">Om du vill ladda ned filen behöver du ett konto i Azure AD som har tilldelats rollen säkerhetsadministratör eller global administratör.</span><span class="sxs-lookup"><span data-stu-id="98740-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="98740-181">Kontrollera att funktionen Molnaktiverat skydd fungerar följer du instruktionerna i [Verifiera anslutningar mellan ditt nätverk och molnet](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="98740-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="98740-182">Inaktivera Blockera när det först påträffas</span><span class="sxs-lookup"><span data-stu-id="98740-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="98740-183">Om du inaktiverar Blockera när det först påträffas sänks skyddet för dina enheter och nätverket.</span><span class="sxs-lookup"><span data-stu-id="98740-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="98740-184">Du kan välja att inaktivera Blockera när det först påträffas om du vill behålla de nödvändiga inställningarna utan att använda Blockera när det först påträffas.</span><span class="sxs-lookup"><span data-stu-id="98740-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="98740-185">Du kan tillfälligt inaktivera Blockera när det först påträffas för att se hur funktionen påverkar nätverket.</span><span class="sxs-lookup"><span data-stu-id="98740-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="98740-186">Vi rekommenderar dock inte att du inaktiverar Blockera när det först påträffas permanent.</span><span class="sxs-lookup"><span data-stu-id="98740-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="98740-187">Inaktivera Blockera när det först påträffas med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="98740-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="98740-188">Gå till administrationscentret för Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) och logga in.</span><span class="sxs-lookup"><span data-stu-id="98740-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="98740-189">Gå till **Slutpunktssäkerhet** > **Antivirusprogram** och välj din princip för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="98740-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="98740-190">Under **Hantera** väljer du **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="98740-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="98740-191">Välj **Redigera** bredvid **Konfigurationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="98740-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="98740-192">Ändra en eller flera av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="98740-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="98740-193">Ställ in **Aktivera molnbaserat skydd** på **Nej** eller **Inte konfigurerat**.</span><span class="sxs-lookup"><span data-stu-id="98740-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="98740-194">Ställ in **Skyddsnivå som levereras i molnet** på **Inte konfigurerat**.</span><span class="sxs-lookup"><span data-stu-id="98740-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="98740-195">Avmarkera kryssrutan för **Utökad tidsgräns i Defender-moln i sekunder**.</span><span class="sxs-lookup"><span data-stu-id="98740-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="98740-196">Granska och spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="98740-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="98740-197">Inaktivera Blockera när det först påträffas med en grupprincip</span><span class="sxs-lookup"><span data-stu-id="98740-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="98740-198">På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="98740-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="98740-199">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="98740-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="98740-200">Öppna trädstrukturen via **Windows-komponenter** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="98740-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="98740-201">Dubbelklicka på **Konfigurera funktionen Blockera när det först påträffas** och ställ in alternativet på **Inaktiverat**.</span><span class="sxs-lookup"><span data-stu-id="98740-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98740-202">Nödvändiga grupprinciper inaktiveras eller ändras inte när du inaktiverar Blockera när det först påträffas.</span><span class="sxs-lookup"><span data-stu-id="98740-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="98740-203">Är du inte företagsadministratör eller IT-tekniker?</span><span class="sxs-lookup"><span data-stu-id="98740-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="98740-204">Om du inte är företagsadministratör eller IT-tekniker, men har frågor om Blockera när det först påträffas är det här avsnittet för dig.</span><span class="sxs-lookup"><span data-stu-id="98740-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="98740-205">Blockera när det först påträffas skyddar mot hot genom att identifiera och blockera skadlig programvara på några sekunder.</span><span class="sxs-lookup"><span data-stu-id="98740-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="98740-206">Även om det inte finns en inställning som kallas Blockera när det först påträffas, aktiveras funktionen när vissa inställningar konfigureras på enheten.</span><span class="sxs-lookup"><span data-stu-id="98740-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="98740-207">Så här aktiverar och inaktiverar du Blockera när det först påträffas på din enhet</span><span class="sxs-lookup"><span data-stu-id="98740-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="98740-208">Om du har en privat enhet som inte hanteras av en organisation kanske du undrar hur du aktiverar eller inaktiverar Blockera när det först påträffas.</span><span class="sxs-lookup"><span data-stu-id="98740-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="98740-209">Du kan hantera Blockera när det först påträffas med Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="98740-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="98740-210">Öppna Windows-säkerhetsappen på Windows 10-datorn.</span><span class="sxs-lookup"><span data-stu-id="98740-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="98740-211">Välj **Skydd mot virus och hot**.</span><span class="sxs-lookup"><span data-stu-id="98740-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="98740-212">Välj **Hantera inställningar** under **Inställningar för skydd mot virus och hot**.</span><span class="sxs-lookup"><span data-stu-id="98740-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="98740-213">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="98740-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="98740-214">Om du vill aktivera Blockera när det först påträffas ska du se till att både **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="98740-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="98740-215">Om du vill inaktivera Blockera när det först påträffas inaktiverar du **Molnbaserat skydd** eller **Skicka exempel automatiskt**.</span><span class="sxs-lookup"><span data-stu-id="98740-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="98740-216">Om du inaktiverar Blockera när det först påträffas sänks skyddsnivån för enheten.</span><span class="sxs-lookup"><span data-stu-id="98740-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="98740-217">Vi rekommenderar inte att du permanent inaktiverar Blockera när det först påträffas.</span><span class="sxs-lookup"><span data-stu-id="98740-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="98740-218">Se även</span><span class="sxs-lookup"><span data-stu-id="98740-218">See also</span></span>

- [<span data-ttu-id="98740-219">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="98740-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="98740-220">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="98740-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="98740-221">Skydda dig med Windows-säkerhet</span><span class="sxs-lookup"><span data-stu-id="98740-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
