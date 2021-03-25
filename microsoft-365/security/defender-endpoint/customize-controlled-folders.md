---
title: Anpassa reglerad mappåtkomst
description: Lägg till andra mappar som ska skyddas med kontrollerad mappåtkomst eller tillåta appar som felaktigt blockerar ändringar av viktiga filer.
keywords: Kontrollerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar, anpassa, lägga till mapp, lägga till app, tillåta, lägga till körbar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163345"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="866b6-104">Anpassa reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="866b6-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="866b6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="866b6-105">**Applies to:**</span></span>
- [<span data-ttu-id="866b6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="866b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="866b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="866b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="866b6-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="866b6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="866b6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="866b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="866b6-110">Kontrollerad mappåtkomst hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="866b6-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="866b6-111">Reglerad mappåtkomst stöds i Windows Server 2019- och Windows 10-klienter.</span><span class="sxs-lookup"><span data-stu-id="866b6-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="866b6-112">Den här artikeln beskriver hur du anpassar funktioner för kontrollerad mappåtkomst och innehåller följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="866b6-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="866b6-113">Skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="866b6-114">Lägga till appar som ska ha åtkomst till skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="866b6-115">Tillåt signerade körbara filer att komma åt skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="866b6-116">Anpassa meddelandet</span><span class="sxs-lookup"><span data-stu-id="866b6-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="866b6-117">Kontrollerad mappåtkomst övervakar appar för aktiviteter som identifieras som skadliga.</span><span class="sxs-lookup"><span data-stu-id="866b6-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="866b6-118">Ibland blockeras legitima appar från att göra ändringar i dina filer.</span><span class="sxs-lookup"><span data-stu-id="866b6-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="866b6-119">Om kontrollerad mappåtkomst påverkar organisationens produktivitet kan du överväga att köra den här funktionen i [granskningsläge](audit-windows-defender.md) för att helt bedöma påverkan.</span><span class="sxs-lookup"><span data-stu-id="866b6-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="866b6-120">Skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-120">Protect additional folders</span></span>

<span data-ttu-id="866b6-121">Kontrollerad mappåtkomst gäller många systemmappar och standardplatser, inklusive mappar som **Dokument,** **Bilder** och **Filmer.**</span><span class="sxs-lookup"><span data-stu-id="866b6-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="866b6-122">Du kan lägga till fler mappar som ska skyddas, men du kan inte ta bort standardmapparna i standardlistan.</span><span class="sxs-lookup"><span data-stu-id="866b6-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="866b6-123">Att lägga till andra mappar i kontrollerad mappåtkomst kan vara praktiskt när du inte lagrar filer i standardbiblioteken i Windows eller om du har ändrat standardplatsen för biblioteken.</span><span class="sxs-lookup"><span data-stu-id="866b6-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="866b6-124">Du kan också ange nätverksresurser och mappade enheter.</span><span class="sxs-lookup"><span data-stu-id="866b6-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="866b6-125">Miljövariabler och jokertecken stöds.</span><span class="sxs-lookup"><span data-stu-id="866b6-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="866b6-126">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="866b6-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="866b6-127">Du kan använda Windows-säkerhetsappen, grupprincipen, PowerShell-cmdlets eller tjänstleverantörer för konfiguration av mobil enhetshantering till att lägga till och ta bort ytterligare skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="866b6-128">Använda Windows-säkerhetsappen för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="866b6-129">Öppna appen Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="866b6-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="866b6-130">Välj **Virus & skydd mot hot** och rulla sedan ned till avsnittet **Utpressningstrojanskydd.**</span><span class="sxs-lookup"><span data-stu-id="866b6-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="866b6-131">Välj **Hantera utpressningstrojanskydd** för att öppna **skyddsfönstret för utpressningstrojaner.**</span><span class="sxs-lookup"><span data-stu-id="866b6-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="866b6-132">Under avsnittet **Kontrollerad mappåtkomst** väljer du **Skyddade mappar**.</span><span class="sxs-lookup"><span data-stu-id="866b6-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="866b6-133">Välj **Ja** i **kommandotolken för** användaråtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="866b6-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="866b6-134">Fönstret **Skyddade** mappar visas.</span><span class="sxs-lookup"><span data-stu-id="866b6-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="866b6-135">Välj **Lägg till en skyddad mapp** och följ anvisningarna för att lägga till mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="866b6-136">Använda grupprinciper för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="866b6-137">Öppna grupprinciphanteringskonsolen på [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och välj sedan **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="866b6-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="866b6-138">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="866b6-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="866b6-139">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender  >  **Sårbarhetsskyddad**  >  **mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="866b6-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="866b6-140">Dubbelklicka på **Konfigurerade skyddade mappar och** ställ in alternativet Aktiverad . </span><span class="sxs-lookup"><span data-stu-id="866b6-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="866b6-141">Välj **Visa** och ange varje mapp.</span><span class="sxs-lookup"><span data-stu-id="866b6-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="866b6-142">Använda PowerShell för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="866b6-143">Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**</span><span class="sxs-lookup"><span data-stu-id="866b6-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="866b6-144">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="866b6-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="866b6-145">Upprepa steg 2 tills du har lagt till alla mappar som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="866b6-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="866b6-146">Mappar som läggs till visas i appen Windows-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="866b6-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Skärmbild av ett PowerShell-fönster med cmdleten ovan angivet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="866b6-148">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="866b6-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="866b6-149">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="866b6-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="866b6-150">Använda MDM-csps för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="866b6-151">Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="866b6-152">Tillåta specifika appar att göra ändringar i kontrollerade mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="866b6-153">Du kan ange om vissa appar alltid anses vara säkra och ge skrivbehörighet till filer i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="866b6-154">Tillåta appar kan vara användbart om en viss app som du känner till och litar på blockeras av funktionen kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="866b6-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="866b6-155">Som standard lägger Windows till appar som anses vara användarvänliga i listan över tillåtna appar.</span><span class="sxs-lookup"><span data-stu-id="866b6-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="866b6-156">Sådana appar som läggs till automatiskt registreras inte i listan som visas i Windows-säkerhetsappen eller med hjälp av de associerade PowerShell-cmdletarna.</span><span class="sxs-lookup"><span data-stu-id="866b6-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="866b6-157">Du borde inte behöva lägga till de flesta appar.</span><span class="sxs-lookup"><span data-stu-id="866b6-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="866b6-158">Lägg bara till appar om de blockeras och du kan kontrollera tillförlitligheten.</span><span class="sxs-lookup"><span data-stu-id="866b6-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="866b6-159">När du lägger till ett program måste du ange programmets plats.</span><span class="sxs-lookup"><span data-stu-id="866b6-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="866b6-160">Endast appen på den platsen får åtkomst till de skyddade mapparna.</span><span class="sxs-lookup"><span data-stu-id="866b6-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="866b6-161">Om programmet (med samma namn) finns på en annan plats läggs det inte till i listan över tillåtna och kan blockeras av kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="866b6-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="866b6-162">Ett tillåtet program eller en tillåten tjänst har skrivbehörighet till en reglerad mapp när den har startats.</span><span class="sxs-lookup"><span data-stu-id="866b6-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="866b6-163">En uppdateringstjänst fortsätter till exempel att utlösa händelser när den tillåts tills den stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="866b6-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="866b6-164">Använda appen Windows Defender Säkerhet för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="866b6-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="866b6-165">Öppna appen Windows-säkerhet genom att söka efter Säkerhet på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="866b6-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="866b6-166">Välj panelen **& virusskydd** (eller sköldikonen på den vänstra menyraden) och välj sedan Hantera utpressningstrojanskydd. </span><span class="sxs-lookup"><span data-stu-id="866b6-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="866b6-167">Under avsnittet **Kontrollerad mappåtkomst** väljer du **Tillåt en app via reglerad mappåtkomst**</span><span class="sxs-lookup"><span data-stu-id="866b6-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="866b6-168">Välj **Lägg till en tillåten app** och följ anvisningarna för att lägga till appar.</span><span class="sxs-lookup"><span data-stu-id="866b6-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Skärmbild av hur du lägger till en knapp för tillåtna appar](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="866b6-170">Använda grupprinciper för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="866b6-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="866b6-171">Öppna grupprinciphanteringskonsolen på [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="866b6-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="866b6-172">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="866b6-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="866b6-173">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender  >  **Sårbarhetsskyddad**  >  **mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="866b6-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="866b6-174">Dubbelklicka på inställningen **Konfigurera tillåtna** program och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="866b6-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="866b6-175">Välj **Visa** och ange varje app.</span><span class="sxs-lookup"><span data-stu-id="866b6-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="866b6-176">Använda PowerShell för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="866b6-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="866b6-177">Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**</span><span class="sxs-lookup"><span data-stu-id="866b6-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="866b6-178">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="866b6-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="866b6-179">Om du till exempel vill lägga till *test.exe* körbara filer som finns i mappen *C:\apps* ser cmdleten ut så här:</span><span class="sxs-lookup"><span data-stu-id="866b6-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="866b6-180">Fortsätt att använda `Add-MpPreference -ControlledFolderAccessAllowedApplications` för att lägga till fler appar i listan.</span><span class="sxs-lookup"><span data-stu-id="866b6-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="866b6-181">Appar som läggs till med den här cmdleten visas i Windows-säkerhetsappen.</span><span class="sxs-lookup"><span data-stu-id="866b6-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Skärmbild av ett PowerShell-fönster med ovanstående cmdlet angivet](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="866b6-183">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="866b6-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="866b6-184">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="866b6-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="866b6-185">Använda MDM CSP för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="866b6-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="866b6-186">Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="866b6-187">Tillåt signerade körbara filer att komma åt skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="866b6-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="866b6-188">Med hjälp av Microsoft Defender för slutpunktscertifikat och filindikatorer kan signerade körbara filer få åtkomst till skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="866b6-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="866b6-189">Mer information om implementering finns [i Skapa indikatorer baserade på certifikat.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="866b6-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="866b6-190">Det här gäller inte för skriptmotorer, inklusive Powershell</span><span class="sxs-lookup"><span data-stu-id="866b6-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="866b6-191">Anpassa meddelandet</span><span class="sxs-lookup"><span data-stu-id="866b6-191">Customize the notification</span></span>

<span data-ttu-id="866b6-192">Mer information om hur du anpassar meddelandet när en regel utlöses och blockerar en app eller fil finns i Konfigurera aviseringsmeddelanden [i Microsoft Defender för slutpunkt.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)</span><span class="sxs-lookup"><span data-stu-id="866b6-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="866b6-193">Se även</span><span class="sxs-lookup"><span data-stu-id="866b6-193">See also</span></span>

- [<span data-ttu-id="866b6-194">Skydda viktiga mappar med kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="866b6-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="866b6-195">Aktivera reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="866b6-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="866b6-196">Utvärdera minskningsregler för attackytor</span><span class="sxs-lookup"><span data-stu-id="866b6-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
