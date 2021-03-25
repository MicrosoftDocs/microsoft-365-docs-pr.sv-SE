---
title: Aktivera reglerad mappåtkomst
keywords: Reglerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar, aktivera, aktivera, använda
description: Lär dig hur du skyddar viktiga filer genom att aktivera reglerad mappåtkomst
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a35c18d805ef3645659f49b8340cbb4cabab2f8d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165075"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="06df6-104">Aktivera reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="06df6-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06df6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="06df6-105">**Applies to:**</span></span>
- [<span data-ttu-id="06df6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="06df6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06df6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06df6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="06df6-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="06df6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="06df6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="06df6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="06df6-110">[Kontrollerad mappåtkomst](controlled-folders.md) hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="06df6-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="06df6-111">Reglerad mappåtkomst ingår i Windows 10 och Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="06df6-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="06df6-112">Du kan aktivera reglerad mappåtkomst på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="06df6-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="06df6-113">Appen Windows-säkerhet</span><span class="sxs-lookup"><span data-stu-id="06df6-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="06df6-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="06df6-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="06df6-115">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="06df6-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="06df6-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="06df6-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="06df6-117">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="06df6-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="06df6-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="06df6-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="06df6-119">[I granskningsläget](evaluate-controlled-folder-access.md) kan du testa hur funktionen fungerar (och granska händelser) utan att påverka den normala användningen av enheten.</span><span class="sxs-lookup"><span data-stu-id="06df6-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="06df6-120">Grupprincipinställningar som inaktiverar sammanslagning av lokala administratörslistor åsidosätter styrda inställningar för mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="06df6-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="06df6-121">De åsidosätter även skyddade mappar och tillåtna appar som angetts av den lokala administratören via kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="06df6-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="06df6-122">Dessa principer omfattar:</span><span class="sxs-lookup"><span data-stu-id="06df6-122">These policies include:</span></span>

* <span data-ttu-id="06df6-123">Microsoft Defender Antivirus **Konfigurera sammanslagning av lokala administratörer för listor**</span><span class="sxs-lookup"><span data-stu-id="06df6-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="06df6-124">System Center Endpoint Protection **Tillåt användare att lägga till undantag och åsidosättningar**</span><span class="sxs-lookup"><span data-stu-id="06df6-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="06df6-125">Mer information om hur du inaktiverar lokal list sammanslagning finns i Förhindra eller tillåta användare att lokalt ändra inställningarna för [Microsoft Defender AV-principen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)</span><span class="sxs-lookup"><span data-stu-id="06df6-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="06df6-126">Appen Windows-säkerhet</span><span class="sxs-lookup"><span data-stu-id="06df6-126">Windows Security app</span></span>

1. <span data-ttu-id="06df6-127">Öppna appen Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet.</span><span class="sxs-lookup"><span data-stu-id="06df6-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="06df6-128">Du kan också söka efter Defender på **startmenyn.**</span><span class="sxs-lookup"><span data-stu-id="06df6-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="06df6-129">Välj panelen **& skydd mot** hot (eller sköldikonen på den vänstra menyraden) och välj sedan **Utpressningstrojanskydd**.</span><span class="sxs-lookup"><span data-stu-id="06df6-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="06df6-130">Ställ in växlingsknappen **för kontrollerad mappåtkomst** på **På**.</span><span class="sxs-lookup"><span data-stu-id="06df6-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="06df6-131">Om reglerad mappåtkomst är konfigurerad med grupprincip-, PowerShell- eller MDM-CSP:er ändras statusen i Windows-säkerhetsappen efter en omstart av enheten.</span><span class="sxs-lookup"><span data-stu-id="06df6-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="06df6-132">Om funktionen är inställd på **granskningsläge för** något av dessa verktyg visas statusen som Av i Windows-säkerhetsappen. </span><span class="sxs-lookup"><span data-stu-id="06df6-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="06df6-133">Om du skyddar användarprofildata rekommenderar vi att användarprofilen finns på Standardinstallationsenhet i Windows.</span><span class="sxs-lookup"><span data-stu-id="06df6-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="06df6-134">Intune</span><span class="sxs-lookup"><span data-stu-id="06df6-134">Intune</span></span>

1. <span data-ttu-id="06df6-135">Logga in på [Azure Portal och](https://portal.azure.com) öppna Intune.</span><span class="sxs-lookup"><span data-stu-id="06df6-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="06df6-136">Gå till **Profiler för**  >  **enhetskonfiguration Skapa**  >  **profil**.</span><span class="sxs-lookup"><span data-stu-id="06df6-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="06df6-137">Namnge profilen, välj **Windows 10 och senare och** **Slutpunktsskydd**.</span><span class="sxs-lookup"><span data-stu-id="06df6-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="06df6-138">![Skapa profil för slutpunktsskydd](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="06df6-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="06df6-139">Gå till **Konfigurera**  >  **mappåtkomst via Windows Defender Exploit Guard** med  >  **kontrollerad**  >  **mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="06df6-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="06df6-140">Skriv sökvägen till varje program som har åtkomst till skyddade mappar och sökvägen till ytterligare mappar som behöver skyddas.</span><span class="sxs-lookup"><span data-stu-id="06df6-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="06df6-141">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="06df6-141">Select **Add**.</span></span><br/> <span data-ttu-id="06df6-142">![Aktivera kontrollerad mappåtkomst i Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="06df6-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="06df6-143">Wilcard stöds för program, men inte för mappar.</span><span class="sxs-lookup"><span data-stu-id="06df6-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="06df6-144">Undermappar är inte skyddade.</span><span class="sxs-lookup"><span data-stu-id="06df6-144">Subfolders are not protected.</span></span> <span data-ttu-id="06df6-145">Tillåtna appar fortsätter att utlösa händelser tills de startas om.</span><span class="sxs-lookup"><span data-stu-id="06df6-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="06df6-146">Välj **OK för** att spara alla öppna blad och **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="06df6-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="06df6-147">Välj profilen Uppgifter **,** tilldela alla **användare till & enheter** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="06df6-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="06df6-148">Hantering av mobila enheter (MDM)</span><span class="sxs-lookup"><span data-stu-id="06df6-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="06df6-149">Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="06df6-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="06df6-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="06df6-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="06df6-151">I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Slutpunktsskydd för**  >  **efterlevnad** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="06df6-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="06df6-152">Välj **Home**  >  **Create Exploit Guard-policy**.</span><span class="sxs-lookup"><span data-stu-id="06df6-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="06df6-153">Ange ett namn och en beskrivning, välj **Kontrollerad mappåtkomst** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="06df6-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="06df6-154">Välj om du vill blockera eller granska ändringar, tillåta andra appar eller lägga till andra mappar och välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="06df6-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="06df6-155">Wilcard stöds för program, men inte för mappar.</span><span class="sxs-lookup"><span data-stu-id="06df6-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="06df6-156">Undermappar är inte skyddade.</span><span class="sxs-lookup"><span data-stu-id="06df6-156">Subfolders are not protected.</span></span> <span data-ttu-id="06df6-157">Tillåtna appar fortsätter att utlösa händelser tills de startas om.</span><span class="sxs-lookup"><span data-stu-id="06df6-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="06df6-158">Granska inställningarna och välj **Nästa för** att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="06df6-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="06df6-159">När principen har skapats stänger **du**.</span><span class="sxs-lookup"><span data-stu-id="06df6-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="06df6-160">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="06df6-160">Group Policy</span></span>

1. <span data-ttu-id="06df6-161">Öppna grupprinciphanteringskonsolen på [](https://technet.microsoft.com/library/cc731212.aspx)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="06df6-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="06df6-162">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="06df6-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="06df6-163">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > Windows Defender Exploit Guard > kontrollerad mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="06df6-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="06df6-164">Dubbelklicka på inställningen Konfigurera **reglerad mappåtkomst** och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="06df6-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="06df6-165">I avsnittet alternativ måste du ange något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="06df6-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="06df6-166">**Aktivera** – Skadliga och misstänkta appar tillåts inte att göra ändringar i filer i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="06df6-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="06df6-167">Ett meddelande visas i Windows händelselogg.</span><span class="sxs-lookup"><span data-stu-id="06df6-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="06df6-168">**Inaktivera (standard)** – Funktionen kontrollerad mappåtkomst fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="06df6-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="06df6-169">Alla appar kan göra ändringar i filer i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="06df6-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="06df6-170">**Granskningsläge** – Ändringar tillåts om en skadlig eller misstänkt app försöker göra en ändring i en fil i en skyddad mapp.</span><span class="sxs-lookup"><span data-stu-id="06df6-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="06df6-171">Det registreras dock i Windows händelselogg där du kan bedöma påverkan på organisationen.</span><span class="sxs-lookup"><span data-stu-id="06df6-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="06df6-172">**Blockera endast diskändring** – Försök av icke-betrodda appar att skriva till diskhändelsen loggas i Windows-händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="06df6-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="06df6-173">De här loggarna finns i **Program-** och tjänstloggar > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="06df6-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="06df6-174">**Granska endast diskändring** – Endast försök att skriva till skyddade diskdeklareringsförsök registreras i Windows-händelseloggen **(under** Program- och  >  **tjänstloggar Microsoft**  >    >  **Windows Defender**  >    >  **Drift-ID 1124).**</span><span class="sxs-lookup"><span data-stu-id="06df6-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="06df6-175">Försök att ändra eller ta bort filer i skyddade mappar registreras inte.</span><span class="sxs-lookup"><span data-stu-id="06df6-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Skärmbild av grupprincipalternativet Aktiverad och Granskningsläge markerat i listrutan](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="06df6-177">Om du vill aktivera reglerad mappåtkomst fullt  ut måste du ställa **in** grupprincipalternativet på Aktiverad och välja Blockera i den nedrullningrullningsalternativsmeny som visas.</span><span class="sxs-lookup"><span data-stu-id="06df6-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="06df6-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="06df6-178">PowerShell</span></span>

1. <span data-ttu-id="06df6-179">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör.**</span><span class="sxs-lookup"><span data-stu-id="06df6-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="06df6-180">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="06df6-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="06df6-181">Du kan aktivera funktionen i granskningsläge genom att ange i `AuditMode` stället för `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="06df6-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="06df6-182">Används `Disabled` för att stänga av funktionen.</span><span class="sxs-lookup"><span data-stu-id="06df6-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="06df6-183">Se även</span><span class="sxs-lookup"><span data-stu-id="06df6-183">See also</span></span>

* [<span data-ttu-id="06df6-184">Skydda viktiga mappar med kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="06df6-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="06df6-185">Anpassa reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="06df6-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="06df6-186">Utvärdera Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="06df6-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-atp.md)