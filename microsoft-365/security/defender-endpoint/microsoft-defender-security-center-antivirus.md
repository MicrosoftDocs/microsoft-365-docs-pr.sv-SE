---
title: Microsoft Defender Antivirus i Windows-säkerhet appen
description: Med Microsoft Defender Antivirus som nu ingår i Windows-säkerhet kan du granska, jämföra och utföra vanliga uppgifter.
keywords: wdav, antivirus, brandvägg, säkerhet, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c15e68a74c9bf518822fce211d6c7d5c4dbc3f2c
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007455"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="96242-104">Microsoft Defender Antivirus i Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="96242-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

<span data-ttu-id="96242-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="96242-105">**Applies to:**</span></span>

- [<span data-ttu-id="96242-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="96242-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="96242-107">I Windows 10, version 1703 och senare är Windows Defender en del av Windows-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="96242-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="96242-108">Inställningar som tidigare ingick i Windows Defender-klienten och huvudklienten Windows Inställningar har kombinerats och flyttats till den nya appen, som installeras som standard som en del av Windows 10, version 1703.</span><span class="sxs-lookup"><span data-stu-id="96242-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96242-109">Om du inaktiverar Windows-säkerhet Center inaktiveras inte Microsoft Defender Antivirus eller [Windows Defender brandväggen.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="96242-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="96242-110">De inaktiveras automatiskt när ett antivirusprogram eller en brandvägg för tredje part installeras och hålls uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="96242-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="96242-111">Om du inaktiverar tjänsten Windows-säkerhet Center eller konfigurerar de tillhörande grupprincipinställningarna så att den inte startas eller körs kan det hända att Windows-säkerhet-appen visar inaktuell eller felaktig information om antivirus- eller brandväggsprodukter som du har installerat på enheten.</span><span class="sxs-lookup"><span data-stu-id="96242-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="96242-112">Det kan också förhindra Microsoft Defender Antivirus från att aktivera sig själv om du har ett gammalt eller inaktuellt antivirusprogram från tredje part eller om du avinstallerar antivirusprodukter från tredje part som du kanske har installerat tidigare.</span><span class="sxs-lookup"><span data-stu-id="96242-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="96242-113">Det här minskar skyddet på enheten avsevärt och kan leda till skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="96242-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="96242-114">Mer [Windows-säkerhet om andra](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) funktioner Windows kan övervakas i appen finns i artikeln om säkerhet.</span><span class="sxs-lookup"><span data-stu-id="96242-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="96242-115">Appen Windows-säkerhet ett klientgränssnitt i Windows 10, version 1703 och senare.</span><span class="sxs-lookup"><span data-stu-id="96242-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="96242-116">Det är inte den Microsoft Defender Säkerhetscenter webbportal som används för att granska och hantera [Microsoft Defender för slutpunkt.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="96242-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="96242-117">Granska inställningarna för skydd mot virus och hot i Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="96242-117">Review virus and threat protection settings in the Windows Security app</span></span>

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Inställningar för skydd mot virus och hot i Windows-säkerhet datorprogrammet":::

1. <span data-ttu-id="96242-119">Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Defender på **startmenyn.**</span><span class="sxs-lookup"><span data-stu-id="96242-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="96242-120">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="96242-121">I följande avsnitt beskrivs hur du utför några av de vanligaste uppgifterna när du granskar eller interagerar med hotskyddet som tillhandahålls av Microsoft Defender Antivirus i Windows-säkerhet-appen.</span><span class="sxs-lookup"><span data-stu-id="96242-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="96242-122">Om de här inställningarna konfigureras och distribueras med grupprincip kommer inställningarna som beskrivs i det här avsnittet att vara nedtonade och inte tillgängliga för användning i enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="96242-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="96242-123">Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="96242-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="96242-124">I [avsnittet Konfigurera användarinteraktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) beskrivs hur du kan konfigurera inställningar för åsidosättning av lokala policyer.</span><span class="sxs-lookup"><span data-stu-id="96242-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="96242-125">Köra en genomsökning med Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="96242-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="96242-126">Öppna Windows-säkerhet-appen genom att söka efter **Säkerhet** på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-127">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-128">Välj **Snabbsökning**.</span><span class="sxs-lookup"><span data-stu-id="96242-128">Select **Quick scan**.</span></span> <span data-ttu-id="96242-129">Du kan också köra en fullständig genomsökning genom att **välja Skanningsalternativ** och sedan välja ett alternativ, till exempel **Fullständig sökning**.</span><span class="sxs-lookup"><span data-stu-id="96242-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="96242-130">Granska uppdateringsversionen av säkerhetsintelligens och ladda ned de senaste uppdateringarna Windows-säkerhet säkerhetsappen</span><span class="sxs-lookup"><span data-stu-id="96242-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="Versionsnummer för säkerhetsintelligens":::

1. <span data-ttu-id="96242-132">Öppna Windows-säkerhet-appen genom att söka efter *Säkerhet* på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-133">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-134">Välj **Uppdateringar & skydd mot virus .**</span><span class="sxs-lookup"><span data-stu-id="96242-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="96242-135">Den installerade versionen visas tillsammans med en del information om när den laddades ned.</span><span class="sxs-lookup"><span data-stu-id="96242-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="96242-136">Du kan kontrollera din aktuella version mot den senaste versionen som finns tillgänglig för manuell nedladdning eller granska ändringsloggen för den versionen.</span><span class="sxs-lookup"><span data-stu-id="96242-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="96242-137">Se [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="96242-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="96242-138">Välj **Sök efter uppdateringar för** att ladda ned nya skyddsuppdateringar (om det finns några).</span><span class="sxs-lookup"><span data-stu-id="96242-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="96242-139">Kontrollera Microsoft Defender Antivirus är aktiverat i Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="96242-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="96242-140">Öppna Windows-säkerhet-appen genom att söka efter *Säkerhet* på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-141">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-142">Välj **Inställningar & för skydd mot virushot**.</span><span class="sxs-lookup"><span data-stu-id="96242-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="96242-143">Ändra **realtidsskyddet till** **På**.</span><span class="sxs-lookup"><span data-stu-id="96242-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96242-144">Om du **inaktiverar realtidsskyddet** aktiveras det automatiskt igen efter en kort fördröjning.</span><span class="sxs-lookup"><span data-stu-id="96242-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="96242-145">Detta är för att säkerställa att du är skyddad från skadlig programvara och hot.</span><span class="sxs-lookup"><span data-stu-id="96242-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="96242-146">Om du installerar ett annat antivirusprogram inaktiveras Microsoft Defender Antivirus automatiskt och anges som sådant i Windows-säkerhet programmet.</span><span class="sxs-lookup"><span data-stu-id="96242-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="96242-147">En inställning visas som gör att du kan aktivera [begränsad regelbunden genomsökning.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="96242-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="96242-148">Lägga till undantag för Microsoft Defender Antivirus i Windows-säkerhet appen</span><span class="sxs-lookup"><span data-stu-id="96242-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="96242-149">Öppna Windows-säkerhet-appen genom att söka efter *Säkerhet* på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-150">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-151">Under Hantera **inställningar väljer** du Inställningar & för skydd mot **virus .**</span><span class="sxs-lookup"><span data-stu-id="96242-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="96242-152">Under inställningen **Undantag väljer** du Lägg till eller ta **bort undantag.**</span><span class="sxs-lookup"><span data-stu-id="96242-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="96242-153">Välj plusikonen **+** () om du vill välja typ och ange alternativ för varje undantag.</span><span class="sxs-lookup"><span data-stu-id="96242-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="96242-154">I följande tabell sammanfattas undantagstyper och vad som händer:</span><span class="sxs-lookup"><span data-stu-id="96242-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="96242-155">Exkluderingstyp</span><span class="sxs-lookup"><span data-stu-id="96242-155">Exclusion type</span></span>  |<span data-ttu-id="96242-156">Definieras av</span><span class="sxs-lookup"><span data-stu-id="96242-156">Defined by</span></span>  |<span data-ttu-id="96242-157">Vad som händer</span><span class="sxs-lookup"><span data-stu-id="96242-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="96242-158">**Fil**</span><span class="sxs-lookup"><span data-stu-id="96242-158">**File**</span></span> |<span data-ttu-id="96242-159">Plats</span><span class="sxs-lookup"><span data-stu-id="96242-159">Location</span></span> <br/><span data-ttu-id="96242-160">Exempel: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="96242-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="96242-161">Den specifika filen hoppas över av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="96242-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="96242-162">**Mapp**</span><span class="sxs-lookup"><span data-stu-id="96242-162">**Folder**</span></span>    |<span data-ttu-id="96242-163">Plats</span><span class="sxs-lookup"><span data-stu-id="96242-163">Location</span></span> <br/><span data-ttu-id="96242-164">Exempel: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="96242-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="96242-165">Alla objekt i den angivna mappen hoppas över av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="96242-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="96242-166">**Filtyp**</span><span class="sxs-lookup"><span data-stu-id="96242-166">**File type**</span></span>   |<span data-ttu-id="96242-167">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="96242-167">File extension</span></span> <br/><span data-ttu-id="96242-168">Exempel: `.test`</span><span class="sxs-lookup"><span data-stu-id="96242-168">Example: `.test`</span></span> |<span data-ttu-id="96242-169">Alla filer med tillägget `.test` var som helst på din enhet hoppas över av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="96242-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="96242-170">**Process**</span><span class="sxs-lookup"><span data-stu-id="96242-170">**Process**</span></span>     |<span data-ttu-id="96242-171">Körbar sökväg</span><span class="sxs-lookup"><span data-stu-id="96242-171">Executable file path</span></span> <br><span data-ttu-id="96242-172">Exempel: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="96242-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="96242-173">Den specifika processen och alla filer som öppnas av den processen hoppas över av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="96242-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="96242-174">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="96242-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="96242-175">Konfigurera och validera undantag baserat på filtillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="96242-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="96242-176">Konfigurera undantag för filer som öppnas av processer</span><span class="sxs-lookup"><span data-stu-id="96242-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="96242-177">Granska historik för identifiering av hot Windows Defender appen Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="96242-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="96242-178">Öppna Windows-säkerhet-appen genom att söka efter *Säkerhet* på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-179">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-180">Välj **Skyddshistorik**.</span><span class="sxs-lookup"><span data-stu-id="96242-180">Select **Protection history**.</span></span> <span data-ttu-id="96242-181">Eventuella tidigare objekt visas.</span><span class="sxs-lookup"><span data-stu-id="96242-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="96242-182">Ange alternativ för utpressningstrojaner och återställning</span><span class="sxs-lookup"><span data-stu-id="96242-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="96242-183">Öppna Windows-säkerhet-appen genom att söka efter *Säkerhet* på Start-menyn och sedan välja **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="96242-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="96242-184">Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).</span><span class="sxs-lookup"><span data-stu-id="96242-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="96242-185">Under **Utpressningstrojanskydd** väljer du **Hantera utpressningstrojanskydd**.</span><span class="sxs-lookup"><span data-stu-id="96242-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="96242-186">Information om hur **du ändrar inställningarna för kontrollerad** mappåtkomst finns i Skydda viktiga mappar med [kontrollerad mappåtkomst.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="96242-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="96242-187">Om du vill konfigurera återställningsalternativ för  utpressningstrojaner väljer du Konfigurera **under** Återställning av utpressningstrojandata och följer anvisningarna för att länka eller konfigurera ditt OneDrive-konto så att du enkelt kan återställa efter en utpressningstrojanattack.</span><span class="sxs-lookup"><span data-stu-id="96242-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="96242-188">Se även</span><span class="sxs-lookup"><span data-stu-id="96242-188">See also</span></span>
- [<span data-ttu-id="96242-189">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="96242-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)