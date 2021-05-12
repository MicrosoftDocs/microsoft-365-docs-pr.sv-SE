---
title: Anpassa kontrollerad mappåtkomst
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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326539"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="beb2d-104">Anpassa kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="beb2d-104">Customize controlled folder access</span></span>

<span data-ttu-id="beb2d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="beb2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="beb2d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="beb2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="beb2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beb2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="beb2d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="beb2d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="beb2d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="beb2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="beb2d-110">Kontrollerad mappåtkomst hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="beb2d-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="beb2d-111">Reglerad mappåtkomst stöds i Windows Server 2019 och Windows 10 klienter.</span><span class="sxs-lookup"><span data-stu-id="beb2d-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="beb2d-112">Den här artikeln beskriver hur du anpassar funktioner för kontrollerad mappåtkomst och innehåller följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="beb2d-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="beb2d-113">Skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="beb2d-114">Lägga till appar som ska ha åtkomst till skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="beb2d-115">Tillåt signerade körbara filer att komma åt skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="beb2d-116">Anpassa meddelandet</span><span class="sxs-lookup"><span data-stu-id="beb2d-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="beb2d-117">Kontrollerad mappåtkomst övervakar appar för aktiviteter som identifieras som skadliga.</span><span class="sxs-lookup"><span data-stu-id="beb2d-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="beb2d-118">Ibland blockeras legitima appar från att göra ändringar i dina filer.</span><span class="sxs-lookup"><span data-stu-id="beb2d-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="beb2d-119">Om kontrollerad mappåtkomst påverkar organisationens produktivitet kan du överväga att köra den här funktionen i [granskningsläge](audit-windows-defender.md) för att helt bedöma påverkan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="beb2d-120">Skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-120">Protect additional folders</span></span>

<span data-ttu-id="beb2d-121">Kontrollerad mappåtkomst gäller många systemmappar och standardplatser, inklusive mappar som **Dokument,** **Bilder** och **Filmer.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="beb2d-122">Du kan lägga till andra mappar som ska skyddas, men du kan inte ta bort standardmapparna i standardlistan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="beb2d-123">Att lägga till andra mappar i kontrollerad mappåtkomst kan vara användbart när du inte lagrar filer i standard-Windows-biblioteken eller om du har ändrat standardplatsen för biblioteken.</span><span class="sxs-lookup"><span data-stu-id="beb2d-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="beb2d-124">Du kan också ange nätverksresurser och mappade enheter.</span><span class="sxs-lookup"><span data-stu-id="beb2d-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="beb2d-125">Miljövariabler och jokertecken stöds.</span><span class="sxs-lookup"><span data-stu-id="beb2d-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="beb2d-126">Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="beb2d-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="beb2d-127">Du kan använda Windows-säkerhet, Grupprincip, PowerShell-cmdlets eller tjänstleverantörer för konfigurationstjänster för hantering av mobila enheter för att lägga till och ta bort skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="beb2d-128">Använda Windows-säkerhet för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="beb2d-129">Öppna Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka efter *säkerhet* på Start-menyn.</span><span class="sxs-lookup"><span data-stu-id="beb2d-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="beb2d-130">Välj **Virus & skydd mot hot** och rulla sedan ned till avsnittet **Utpressningstrojanskydd.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="beb2d-131">Välj **Hantera utpressningstrojanskydd** för att öppna **skyddsfönstret för utpressningstrojaner.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="beb2d-132">Under avsnittet **Kontrollerad mappåtkomst** väljer du **Skyddade mappar**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="beb2d-133">Välj **Ja** i **kommandotolken för** användaråtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="beb2d-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="beb2d-134">Fönstret **Skyddade** mappar visas.</span><span class="sxs-lookup"><span data-stu-id="beb2d-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="beb2d-135">Välj **Lägg till en skyddad mapp** och följ anvisningarna för att lägga till mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="beb2d-136">Använda grupprinciper för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="beb2d-137">Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true) på datorn för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="beb2d-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="beb2d-138">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="beb2d-139">Gå till **Administrativa mallar för datorkonfigurationsprinciper** i   >    >  **redigeraren för grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="beb2d-140">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender sårbarhetsskyddad**  >  **mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="beb2d-141">**Obs!** I äldre versioner av Windows kanske du ser **Windows Defender Antivirus** i stället **för Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="beb2d-142">Dubbelklicka på **Konfigurerade skyddade mappar** och ställ sedan in alternativet Aktiverad . </span><span class="sxs-lookup"><span data-stu-id="beb2d-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="beb2d-143">Välj **Visa** och ange varje mapp som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="beb2d-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="beb2d-144">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="beb2d-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="beb2d-145">Använda PowerShell för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="beb2d-146">Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**</span><span class="sxs-lookup"><span data-stu-id="beb2d-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="beb2d-147">Skriv följande PowerShell-cmdlet och `<the folder to be protected>` ersätt med mappens sökväg (till `"c:\apps\"` exempel):</span><span class="sxs-lookup"><span data-stu-id="beb2d-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="beb2d-148">Upprepa steg 2 för varje mapp som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="beb2d-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="beb2d-149">Mappar som är skyddade är synliga i Windows-säkerhet appen.</span><span class="sxs-lookup"><span data-stu-id="beb2d-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="PowerShell-fönster med cmdleten visad":::

> [!IMPORTANT]
> <span data-ttu-id="beb2d-151">Används `Add-MpPreference` för att lägga till appar i listan och inte `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="beb2d-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="beb2d-152">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="beb2d-153">Använda MDM-csps för att skydda ytterligare mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="beb2d-154">Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="beb2d-155">Tillåta specifika appar att göra ändringar i kontrollerade mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="beb2d-156">Du kan ange om vissa appar alltid anses vara säkra och ge skrivbehörighet till filer i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="beb2d-157">Tillåta appar kan vara användbart om en viss app som du känner till och litar på blockeras av funktionen kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="beb2d-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beb2d-158">Som standard läggs Windows appar som anses vara användarvänliga i listan över tillåtna appar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="beb2d-159">Sådana appar som läggs till automatiskt registreras inte i listan som visas i Windows-säkerhet-appen eller med hjälp av de associerade PowerShell-cmdletarna.</span><span class="sxs-lookup"><span data-stu-id="beb2d-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="beb2d-160">Du borde inte behöva lägga till de flesta appar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="beb2d-161">Lägg bara till appar om de blockeras och du kan kontrollera tillförlitligheten.</span><span class="sxs-lookup"><span data-stu-id="beb2d-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="beb2d-162">När du lägger till ett program måste du ange programmets plats.</span><span class="sxs-lookup"><span data-stu-id="beb2d-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="beb2d-163">Endast appen på den platsen får åtkomst till de skyddade mapparna.</span><span class="sxs-lookup"><span data-stu-id="beb2d-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="beb2d-164">Om programmet (med samma namn) finns på en annan plats läggs det inte till i listan över tillåtna program och kan blockeras av kontrollerad mappåtkomst.</span><span class="sxs-lookup"><span data-stu-id="beb2d-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="beb2d-165">Ett tillåtet program eller en tillåten tjänst har skrivbehörighet till en reglerad mapp när den har startats.</span><span class="sxs-lookup"><span data-stu-id="beb2d-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="beb2d-166">En uppdateringstjänst fortsätter till exempel att utlösa händelser när den tillåts tills den stoppas och startas om.</span><span class="sxs-lookup"><span data-stu-id="beb2d-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="beb2d-167">Använd appen Windows Defender säkerhet för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="beb2d-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="beb2d-168">Öppna Windows-säkerhet genom att söka efter Säkerhet på **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="beb2d-169">Välj panelen **& virusskydd** (eller sköldikonen på den vänstra menyraden) och välj sedan Hantera utpressningstrojanskydd. </span><span class="sxs-lookup"><span data-stu-id="beb2d-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="beb2d-170">Under avsnittet **Kontrollerad mappåtkomst** väljer du **Tillåt en app via reglerad mappåtkomst**</span><span class="sxs-lookup"><span data-stu-id="beb2d-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="beb2d-171">Välj **Lägg till en tillåten app** och följ anvisningarna för att lägga till appar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knappen Lägg till en tillåten app":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="beb2d-173">Använda grupprinciper för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="beb2d-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="beb2d-174">Öppna grupprinciphanteringskonsolen på [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="beb2d-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="beb2d-175">I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="beb2d-176">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender sårbarhetsskyddad**  >  **mappåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="beb2d-177">Dubbelklicka på inställningen **Konfigurera tillåtna** program och ställ in alternativet **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="beb2d-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="beb2d-178">Välj **Visa** och ange varje app.</span><span class="sxs-lookup"><span data-stu-id="beb2d-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="beb2d-179">Använda PowerShell för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="beb2d-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="beb2d-180">Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**</span><span class="sxs-lookup"><span data-stu-id="beb2d-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="beb2d-181">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="beb2d-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="beb2d-182">Om du till exempel vill lägga till *test.exe* körbara filer som finns i mappen *C:\apps* ser cmdleten ut så här:</span><span class="sxs-lookup"><span data-stu-id="beb2d-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="beb2d-183">Fortsätt att använda `Add-MpPreference -ControlledFolderAccessAllowedApplications` för att lägga till fler appar i listan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="beb2d-184">Appar som läggs till med den här cmdleten visas Windows-säkerhet appen.</span><span class="sxs-lookup"><span data-stu-id="beb2d-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdleten tillåter en app":::

> [!IMPORTANT]
> <span data-ttu-id="beb2d-186">Används `Add-MpPreference` för att lägga till eller lägga till appar i listan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="beb2d-187">Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.</span><span class="sxs-lookup"><span data-stu-id="beb2d-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="beb2d-188">Använda MDM CSP för att tillåta specifika appar</span><span class="sxs-lookup"><span data-stu-id="beb2d-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="beb2d-189">Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="beb2d-190">Tillåt signerade körbara filer att komma åt skyddade mappar</span><span class="sxs-lookup"><span data-stu-id="beb2d-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="beb2d-191">Med hjälp av Microsoft Defender för slutpunktscertifikat och filindikatorer kan signerade körbara filer få åtkomst till skyddade mappar.</span><span class="sxs-lookup"><span data-stu-id="beb2d-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="beb2d-192">Mer information om implementering finns [i Skapa indikatorer baserade på certifikat.](indicator-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="beb2d-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="beb2d-193">Det här gäller inte för skriptmotorer, inklusive Powershell</span><span class="sxs-lookup"><span data-stu-id="beb2d-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="beb2d-194">Anpassa meddelandet</span><span class="sxs-lookup"><span data-stu-id="beb2d-194">Customize the notification</span></span>

<span data-ttu-id="beb2d-195">Mer information om hur du anpassar meddelandet när en regel utlöses och blockerar en app eller fil finns i Konfigurera aviseringsmeddelanden [i Microsoft Defender för slutpunkt.](configure-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="beb2d-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="beb2d-196">Se även</span><span class="sxs-lookup"><span data-stu-id="beb2d-196">See also</span></span>

- [<span data-ttu-id="beb2d-197">Skydda viktiga mappar med kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="beb2d-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="beb2d-198">Aktivera kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="beb2d-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="beb2d-199">Utvärdera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="beb2d-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
