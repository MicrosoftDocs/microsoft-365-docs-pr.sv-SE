---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar appar på Microsoft Managed Desktop-enheter.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, företagsspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046334"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="059bd-104">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="059bd-104">Deploy apps to devices</span></span>
<span data-ttu-id="059bd-105">En del av introduktionen till Microsoft Managed Desktop är att lägga till och distribuera appar på användarens enheter.</span><span class="sxs-lookup"><span data-stu-id="059bd-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="059bd-106">När du använder Microsoft Managed Desktop-portalen kan du lägga till och distribuera dina appar.</span><span class="sxs-lookup"><span data-stu-id="059bd-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="059bd-107">Den övergripande processen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="059bd-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="059bd-108">[Lägg till appar i Microsoft Managed Desktop-portalen](#1) – Det kan vara befintliga LOB-appar (line-of-business) eller appar från Microsoft Store för företag som du har synkroniserat med Intune.</span><span class="sxs-lookup"><span data-stu-id="059bd-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="059bd-109">[Skapa Azure Active Directory (AD) grupper för apptilldelning](#2) - Du använder dessa grupper för att hantera apptilldelning.</span><span class="sxs-lookup"><span data-stu-id="059bd-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="059bd-110">Tilldela appar till användarna</span><span class="sxs-lookup"><span data-stu-id="059bd-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="059bd-111">Steg 1: Lägga till appar i Microsoft Managed Desktop-portalen</span><span class="sxs-lookup"><span data-stu-id="059bd-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="059bd-112">Du kan lägga till [Win32- eller Windows MSI-baserade appar](#lob-apps)eller [Microsoft Store för företag-appar](#msfb-apps) på Microsoft Managed Desktop och sedan distribuera dem på Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="059bd-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="059bd-113">Win32- eller Windows MSI-baserade appar till Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="059bd-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="059bd-114">Du kan lägga till dina LOB-appar (line-of-business) i Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="059bd-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="059bd-115">Information om krav för appar som är installerade på Microsoft Hanterade stationära enheter finns i [microsofts appkrav för hanterade skrivbord](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="059bd-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="059bd-116">I den här proceduren väljer du vilken typ av app du vill lägga till och konfigurerar och laddar sedan upp appkällan.</span><span class="sxs-lookup"><span data-stu-id="059bd-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="059bd-117">**Så här lägger du till din LOB-app eller Windows-app i Microsoft Managed Desktop-portalen**</span><span class="sxs-lookup"><span data-stu-id="059bd-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="059bd-118">Du kan logga in på Microsoft Managed Desktop-portalen eller logga in på Intune och sedan söka efter Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059bd-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="059bd-119">Vi visar inloggning på Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="059bd-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="059bd-120">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="059bd-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="059bd-121">Under **Lager**väljer du **Appar**.</span><span class="sxs-lookup"><span data-stu-id="059bd-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="059bd-122">Välj **Lägg till**i arbetsbelastningen Appar .</span><span class="sxs-lookup"><span data-stu-id="059bd-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="059bd-123">Välj **Line-of-business-app** eller **Windows-app (Win32) i** **Lägg till**app .</span><span class="sxs-lookup"><span data-stu-id="059bd-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="059bd-124">Om du har valt **Line-of-business-app**läser du [Lägga till en Windows-business-app i Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) för instruktioner om hur du lägger till och konfigurerar affärsappar.</span><span class="sxs-lookup"><span data-stu-id="059bd-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="059bd-125">Om du har valt **Windows-app (Win32)** läser du [Win32-apphanteringen](https://docs.microsoft.com/intune/apps-win32-app-management) för instruktioner om hur du lägger till och konfigurerar Windows-appar.</span><span class="sxs-lookup"><span data-stu-id="059bd-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="059bd-126">Microsoft Store för företag-appar</span><span class="sxs-lookup"><span data-stu-id="059bd-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="059bd-127">Om du inte har registrerat dig hos Microsoft Store för företag kan du registrera dig när du handlar för appar.</span><span class="sxs-lookup"><span data-stu-id="059bd-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="059bd-128">När du har dina appar kan du synkronisera dem med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059bd-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="059bd-129">**Så här köper du appar från Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="059bd-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="059bd-130">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt Microsoft Store för företag-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="059bd-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="059bd-131">Välj **Handla för min grupp**.</span><span class="sxs-lookup"><span data-stu-id="059bd-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="059bd-132">Använd Sök för att hitta den app du vill ha och välj appen.</span><span class="sxs-lookup"><span data-stu-id="059bd-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="059bd-133">På produktinformationen väljer du **Hämta appen**.</span><span class="sxs-lookup"><span data-stu-id="059bd-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="059bd-134">Microsoft Store lägger till appen i **Dina produkter** för din organisation.</span><span class="sxs-lookup"><span data-stu-id="059bd-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="059bd-135">**Så här tvingar du fram en synkronisering mellan Intune och Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="059bd-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="059bd-136">Logga in på [Azure Portal](https://portal.azure.com/) som Intune Admin eller Global Admin för din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="059bd-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="059bd-137">Välj **Alla tjänster > Intune**.</span><span class="sxs-lookup"><span data-stu-id="059bd-137">Select **All services > Intune**.</span></span> <span data-ttu-id="059bd-138">Intune finns i avsnittet Övervakning + Hantering.</span><span class="sxs-lookup"><span data-stu-id="059bd-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="059bd-139">Välj **Klientappar**i fönstret Intune och välj sedan **Microsoft Store för företag**.</span><span class="sxs-lookup"><span data-stu-id="059bd-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="059bd-140">Välj **Aktivera** om du vill synkronisera dina Microsoft Store för företag-appar med Intune.</span><span class="sxs-lookup"><span data-stu-id="059bd-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="059bd-141">Om du inte redan har gjort det kan du registrera och koppla ditt Microsoft Store för företag-konto till Intune</span><span class="sxs-lookup"><span data-stu-id="059bd-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="059bd-142">Välj det språk som appar från Microsoft Store för företag ska visas i Intune-konsolen</span><span class="sxs-lookup"><span data-stu-id="059bd-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="059bd-143">Välj **Synkronisera om** du vill synkronisera dina Microsoft Store för företag-appar med Intune.</span><span class="sxs-lookup"><span data-stu-id="059bd-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="059bd-144">Kontrollera att synkroniseringen mellan Microsoft Store för företag och Intune är aktiv (nästa steg).</span><span class="sxs-lookup"><span data-stu-id="059bd-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="059bd-145">**Så här kontrollerar du att en synkronisering mellan Intune och Microsoft Store för företag är aktiv**</span><span class="sxs-lookup"><span data-stu-id="059bd-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="059bd-146">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt Microsoft Store för företag-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="059bd-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="059bd-147">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="059bd-147">Select **Manage**.</span></span>
3. <span data-ttu-id="059bd-148">Välj **Inställningar** och välj sedan **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="059bd-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="059bd-149">Kontrollera att Intune visas under **Hanteringsverktyg**och att statusen är **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="059bd-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="059bd-150">Steg 2: Skapa Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="059bd-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="059bd-151">Skapa tre Azure AD-grupper för varje app.</span><span class="sxs-lookup"><span data-stu-id="059bd-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="059bd-152">I den här tabellen beskrivs de grupper du behöver (Tillgänglig, Obligatorisk och Avinstallera).</span><span class="sxs-lookup"><span data-stu-id="059bd-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="059bd-153">Typ av apptilldelning</span><span class="sxs-lookup"><span data-stu-id="059bd-153">App assignment type</span></span> |    <span data-ttu-id="059bd-154">Gruppanvändning</span><span class="sxs-lookup"><span data-stu-id="059bd-154">Group use</span></span>    | <span data-ttu-id="059bd-155">Exempel på Azure AD-namn</span><span class="sxs-lookup"><span data-stu-id="059bd-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="059bd-156">Kan användas</span><span class="sxs-lookup"><span data-stu-id="059bd-156">Available</span></span> |  <span data-ttu-id="059bd-157">Appen kommer att vara tillgänglig från Company Portal app eller webbplats.</span><span class="sxs-lookup"><span data-stu-id="059bd-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="059bd-158">MMD – *appnamn* – Tillgängligt</span><span class="sxs-lookup"><span data-stu-id="059bd-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="059bd-159">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="059bd-159">Required</span></span> |  <span data-ttu-id="059bd-160">Appen installeras på enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="059bd-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="059bd-161">MMD – *appnamn* – Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="059bd-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="059bd-162">Avinstallera</span><span class="sxs-lookup"><span data-stu-id="059bd-162">Uninstall</span></span> |  <span data-ttu-id="059bd-163">Appen avinstalleras från enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="059bd-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="059bd-164">MMD – *appnamn* – Avinstallera</span><span class="sxs-lookup"><span data-stu-id="059bd-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="059bd-165">Lägg till användarna i dessa grupper för att antingen göra appen availabe, installera appen eller ta bort appen från sin Microsoft Managed Desktop-enhet.</span><span class="sxs-lookup"><span data-stu-id="059bd-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="059bd-166">Steg 3: Tilldela appar till användarna</span><span class="sxs-lookup"><span data-stu-id="059bd-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="059bd-167">**Så här tilldelar du appen till användarna**</span><span class="sxs-lookup"><span data-stu-id="059bd-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="059bd-168">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="059bd-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="059bd-169">Välj **Appar**i fönstret Hanterade skrivbord .</span><span class="sxs-lookup"><span data-stu-id="059bd-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="059bd-170">I arbetsbelastningen Appar väljer du den app som du vill tilldela användare till och väljer **Tilldela användargrupper**.</span><span class="sxs-lookup"><span data-stu-id="059bd-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="059bd-171">För den specifika appen väljer du en tilldelningstyp (Tillgänglig, Obligatorisk, Avinstallera) och tilldelar lämplig grupp.</span><span class="sxs-lookup"><span data-stu-id="059bd-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="059bd-172">Välj **OK**i fönstret Tilldela appar .</span><span class="sxs-lookup"><span data-stu-id="059bd-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="059bd-173">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="059bd-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="059bd-174">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="059bd-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="059bd-175">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="059bd-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="059bd-176">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="059bd-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="059bd-177">Distribuera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="059bd-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="059bd-178">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="059bd-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="059bd-179">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="059bd-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="059bd-180">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="059bd-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="059bd-181">Distribuera appar (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="059bd-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
