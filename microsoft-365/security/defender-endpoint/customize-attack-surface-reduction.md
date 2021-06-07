---
title: Anpassa regler för minskning av attackytan
description: Individuellt ange regler i gransknings-, block- eller inaktiverade lägen och lägga till filer och mappar som ska undantas från reglerna för att minska attackytan
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, anpassa, konfigurera, utesluta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 232f7133f177e3d0aa93fcb2835fb86bcfd0d37c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769329"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="2feee-104">Anpassa regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2feee-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="2feee-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2feee-105">**Applies to:**</span></span>
- [<span data-ttu-id="2feee-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2feee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2feee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2feee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2feee-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2feee-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2feee-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2feee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="2feee-110">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="2feee-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2feee-111">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="2feee-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2feee-112">[Minskningsregler för attackytan](enable-attack-surface-reduction.md) hjälper till att förhindra programvarubeteenden som ofta missbrukeras för att avslöja din enhet eller ditt nätverk.</span><span class="sxs-lookup"><span data-stu-id="2feee-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="2feee-113">En attackerare kan till exempel försöka köra ett osignerat skript från en USB-enhet eller ha ett makro i ett Office-dokument som ringer anrop direkt till Win32 API.</span><span class="sxs-lookup"><span data-stu-id="2feee-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="2feee-114">Minskning av attackytan kan begränsa dessa typer av riskfyllda beteenden och förbättra organisationens grundbeteende.</span><span class="sxs-lookup"><span data-stu-id="2feee-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="2feee-115">Lär dig hur du kan [](#exclude-files-and-folders) anpassa regler för att minska attackytan genom att utesluta filer och mappar eller lägga till anpassad [text](#customize-the-notification) i meddelandemeddelandet som visas på en användares dator.</span><span class="sxs-lookup"><span data-stu-id="2feee-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="2feee-116">Du kan ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner Windows:</span><span class="sxs-lookup"><span data-stu-id="2feee-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="2feee-117">Windows 10 Pro, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="2feee-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2feee-118">Windows 10 Enterprise, version [1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare</span><span class="sxs-lookup"><span data-stu-id="2feee-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2feee-119">Windows Server, [version 1803 (Halvårskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) eller senare</span><span class="sxs-lookup"><span data-stu-id="2feee-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="2feee-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) Du kan använda grupprincip-, PowerShell- och MDM-konfigurationstjänstleverantörer (Mobile Device Management) för att konfigurera de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="2feee-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="2feee-121">Undanta filer och mappar</span><span class="sxs-lookup"><span data-stu-id="2feee-121">Exclude files and folders</span></span>

<span data-ttu-id="2feee-122">Du kan välja att undanta filer och mappar från att utvärderas med hjälp av minskningsregler för attackytan.</span><span class="sxs-lookup"><span data-stu-id="2feee-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="2feee-123">När filen har uteslutits blockeras den inte från att köras även om en minskningsregel för attackytan identifierar att filen innehåller skadligt beteende.</span><span class="sxs-lookup"><span data-stu-id="2feee-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

> [!WARNING]
> <span data-ttu-id="2feee-124">Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.</span><span class="sxs-lookup"><span data-stu-id="2feee-124">This could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="2feee-125">Att utesluta filer eller mappar kan allvarligt minska skyddet som tillhandahålls av minskningsregler för attackytan.</span><span class="sxs-lookup"><span data-stu-id="2feee-125">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="2feee-126">Filer som skulle ha blockerats av en regel tillåts köras och ingen rapport eller händelse registreras.</span><span class="sxs-lookup"><span data-stu-id="2feee-126">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="2feee-127">Ett undantag gäller för alla regler som tillåter undantag.</span><span class="sxs-lookup"><span data-stu-id="2feee-127">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="2feee-128">Du kan ange en enskild fil, mappsökväg eller det fullständigt kvalificerade domännamnet för en resurs.</span><span class="sxs-lookup"><span data-stu-id="2feee-128">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="2feee-129">Du kan dock inte begränsa ett undantag till en viss regel.</span><span class="sxs-lookup"><span data-stu-id="2feee-129">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="2feee-130">Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="2feee-130">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="2feee-131">Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="2feee-131">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="2feee-132">Minskning av attackytan stöder miljövariabler och jokertecken.</span><span class="sxs-lookup"><span data-stu-id="2feee-132">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="2feee-133">Information om hur du använder jokertecken finns i använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="2feee-133">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="2feee-134">Om du stöter på problem med regler för att identifiera filer som du tror inte ska identifieras kan du använda [granskningsläge för att testa regeln.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="2feee-134">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="2feee-135">Regelbeskrivning</span><span class="sxs-lookup"><span data-stu-id="2feee-135">Rule description</span></span> | <span data-ttu-id="2feee-136">GUID</span><span class="sxs-lookup"><span data-stu-id="2feee-136">GUID</span></span> |
|:----|:----|:----|
| <span data-ttu-id="2feee-137">Blockera alla Office från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="2feee-137">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="2feee-138">Blockera körning av potentiellt oönskade skript</span><span class="sxs-lookup"><span data-stu-id="2feee-138">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="2feee-139">Blockera Win32 API-anrop från Office makro</span><span class="sxs-lookup"><span data-stu-id="2feee-139">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="2feee-140">Blockera Office program från att skapa körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="2feee-140">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="2feee-141">Blockera Office-program från att mata in kod i andra processer</span><span class="sxs-lookup"><span data-stu-id="2feee-141">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="2feee-142">Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="2feee-142">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="2feee-143">Blockera körbart innehåll från e-postklient och webbaserad e-post</span><span class="sxs-lookup"><span data-stu-id="2feee-143">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="2feee-144">Blockera körbara filer från att köras såvida de inte uppfyller villkoren för en vän, ålder eller ett betrott listvillkor</span><span class="sxs-lookup"><span data-stu-id="2feee-144">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="2feee-145">Använd avancerat skydd mot utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="2feee-145">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| <span data-ttu-id="2feee-146">Blockera att autentiseringsuppgifter stjäls från Windows lokala säkerhetsutfärdares undersystem (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="2feee-146">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="2feee-147">Blockera processskapanden som kommer från PSExec- och WMI-kommandon</span><span class="sxs-lookup"><span data-stu-id="2feee-147">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="2feee-148">Blockera icke betrodda och osignerade processer som körs från USB</span><span class="sxs-lookup"><span data-stu-id="2feee-148">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="2feee-149">Blockera Office kommunikationsprogram från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="2feee-149">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="2feee-150">Blockera Adobe Reader från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="2feee-150">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="2feee-151">Blockera beständighet via WMI-händelseprenumeration</span><span class="sxs-lookup"><span data-stu-id="2feee-151">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

<span data-ttu-id="2feee-152">Mer information [om varje regel](attack-surface-reduction.md) finns i avsnittet för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="2feee-152">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="2feee-153">Använda grupprinciper för att utesluta filer och mappar</span><span class="sxs-lookup"><span data-stu-id="2feee-153">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="2feee-154">På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](https://technet.microsoft.com/library/cc731212.aspx), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2feee-154">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="2feee-155">I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="2feee-155">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="2feee-156">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender sårbarhetsattackytan.**  >  </span><span class="sxs-lookup"><span data-stu-id="2feee-156">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="2feee-157">Dubbelklicka på inställningen Exkludera **filer och sökvägar från minskningsregler för attackytan** och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="2feee-157">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2feee-158">Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.**</span><span class="sxs-lookup"><span data-stu-id="2feee-158">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="2feee-159">Ange **0** i **värdekolumnen** för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="2feee-159">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="2feee-160">Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**</span><span class="sxs-lookup"><span data-stu-id="2feee-160">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="2feee-161">Använda PowerShell för att utesluta filer och mappar</span><span class="sxs-lookup"><span data-stu-id="2feee-161">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="2feee-162">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**</span><span class="sxs-lookup"><span data-stu-id="2feee-162">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="2feee-163">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2feee-163">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="2feee-164">Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler mappar i listan.</span><span class="sxs-lookup"><span data-stu-id="2feee-164">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2feee-165">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="2feee-165">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="2feee-166">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="2feee-166">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="2feee-167">Använda MDM-csP:er för att utesluta filer och mappar</span><span class="sxs-lookup"><span data-stu-id="2feee-167">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="2feee-168">Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="2feee-168">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="2feee-169">Anpassa meddelandet</span><span class="sxs-lookup"><span data-stu-id="2feee-169">Customize the notification</span></span>

<span data-ttu-id="2feee-170">Du kan anpassa meddelandet för när en regel utlöses och spärra en app eller fil.</span><span class="sxs-lookup"><span data-stu-id="2feee-170">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="2feee-171">Mer information [Windows-säkerhet](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) artikeln.</span><span class="sxs-lookup"><span data-stu-id="2feee-171">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2feee-172">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2feee-172">Related topics</span></span>

* [<span data-ttu-id="2feee-173">Minska attackytor med minskningsregler för attackytan</span><span class="sxs-lookup"><span data-stu-id="2feee-173">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="2feee-174">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2feee-174">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="2feee-175">Utvärdera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2feee-175">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="2feee-176">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2feee-176">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
