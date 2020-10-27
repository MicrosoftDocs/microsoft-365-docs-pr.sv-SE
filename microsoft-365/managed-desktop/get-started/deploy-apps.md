---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar program till Microsoft Managed Station ära datorer.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, branschspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769112"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="540f7-104">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="540f7-104">Deploy apps to devices</span></span>
<span data-ttu-id="540f7-105">Del av registrering på Microsoft Managed Desktop inkluderar att lägga till och distribuera appar till din användares enheter.</span><span class="sxs-lookup"><span data-stu-id="540f7-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="540f7-106">När du använder Microsoft Managed Desktop Portal kan du lägga till och distribuera dina appar.</span><span class="sxs-lookup"><span data-stu-id="540f7-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="540f7-107">Den övergripande processen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="540f7-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="540f7-108">[Lägga till program till Microsoft Managed Desktop Portal](#1) -det här kan vara befintliga LOB-appar (Line-of Business) eller appar från Microsoft Store för företag som du har synkroniserat med Intune.</span><span class="sxs-lookup"><span data-stu-id="540f7-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="540f7-109">[Skapa Azure Active Directory-grupper (AD) för program tilldelning](#2) – Använd de här grupperna för att hantera program tilldelning.</span><span class="sxs-lookup"><span data-stu-id="540f7-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="540f7-110">Tilldela appar till dina användare</span><span class="sxs-lookup"><span data-stu-id="540f7-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="540f7-111">Steg 1: Lägg till program till Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="540f7-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="540f7-112">Du kan lägga till [Win32-eller Windows MSI-baserade appar](#lob-apps)eller [Microsoft Store för företag-program](#msfb-apps) till Microsoft Managed Desktop, och sedan distribuera dem till Microsoft Managed Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="540f7-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="540f7-113">Win32-eller Windows MSI-baserade program till Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="540f7-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="540f7-114">Du kan lägga till dina program för branschspecifika affärer (LOB) på Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="540f7-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="540f7-115">Information om kraven för program som är installerade på Microsoft-hanterade Station ära enheter finns i [Microsoft Managed Desktop program krav](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="540f7-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="540f7-116">I den här proceduren väljer du vilken typ av program du vill lägga till och konfigurerar sedan program källan.</span><span class="sxs-lookup"><span data-stu-id="540f7-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="540f7-117">**Så här lägger du till ett LOB-program eller Windows-appen på Microsoft Managed Desktop Portal**</span><span class="sxs-lookup"><span data-stu-id="540f7-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="540f7-118">Du kan logga in på Microsoft Managed Desktop portal eller logga in i Intune och sedan söka efter Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="540f7-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="540f7-119">Vi kommer att visa att du loggar in på Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="540f7-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="540f7-120">Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="540f7-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="540f7-121">Under **lager** väljer du **appar** .</span><span class="sxs-lookup"><span data-stu-id="540f7-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="540f7-122">I apparnas arbets belastning väljer du **Lägg till** .</span><span class="sxs-lookup"><span data-stu-id="540f7-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="540f7-123">I **Lägg till app** väljer du **line of Business-appen** eller **Windows-programmet (Win32)** .</span><span class="sxs-lookup"><span data-stu-id="540f7-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="540f7-124">Om du valde **branschspecifika program** kan du läsa [lägga till en Windows line of Business-app i Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) för instruktioner om hur du lägger till och konfigurerar branschspecifika appar.</span><span class="sxs-lookup"><span data-stu-id="540f7-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="540f7-125">Om du valde **Windows-programmet (Win32)** kan du läsa om hur du lägger till och konfigurerar Windows-appar i [Win32 program hantering](https://docs.microsoft.com/intune/apps-win32-app-management) .</span><span class="sxs-lookup"><span data-stu-id="540f7-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="540f7-126">Microsoft Store för företag-appar</span><span class="sxs-lookup"><span data-stu-id="540f7-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="540f7-127">Om du inte har registrerat dig för Microsoft Store för företag kan du registrera dig när du handlar med appar.</span><span class="sxs-lookup"><span data-stu-id="540f7-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="540f7-128">När du har dina appar kan du synkronisera dem med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="540f7-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="540f7-129">**Så här köper du program från Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="540f7-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="540f7-130">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt administratörs konto för Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="540f7-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="540f7-131">Välj **butik för min grupp** .</span><span class="sxs-lookup"><span data-stu-id="540f7-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="540f7-132">Använd Sök funktionen för att hitta den app du vill använda och välj appen.</span><span class="sxs-lookup"><span data-stu-id="540f7-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="540f7-133">På produkt uppgifterna väljer du **Hämta appen** .</span><span class="sxs-lookup"><span data-stu-id="540f7-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="540f7-134">Microsoft Store lägger till appen till **dina produkter** för din organisation.</span><span class="sxs-lookup"><span data-stu-id="540f7-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="540f7-135">**Så här tvingar du en synkronisering mellan Intune och Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="540f7-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="540f7-136">Logga in i [administrations centret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="540f7-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="540f7-137">Välj **Tenant administration**  >  **anslutningar för innehavaradministration och tokens**  >  **Microsoft Store för företag** .</span><span class="sxs-lookup"><span data-stu-id="540f7-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="540f7-138">Välj **Synkronisera** för att få de program som du har köpt från Microsoft Store till Intune.</span><span class="sxs-lookup"><span data-stu-id="540f7-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="540f7-139">**Så här kontrollerar du att synkronisering mellan Intune och Microsoft Store för företag är aktiv**</span><span class="sxs-lookup"><span data-stu-id="540f7-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="540f7-140">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med ditt administratörs konto för Microsoft Store för företag.</span><span class="sxs-lookup"><span data-stu-id="540f7-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="540f7-141">Välj **Hantera** .</span><span class="sxs-lookup"><span data-stu-id="540f7-141">Select **Manage** .</span></span>
3. <span data-ttu-id="540f7-142">Välj **Inställningar** och sedan **fördela** .</span><span class="sxs-lookup"><span data-stu-id="540f7-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="540f7-143">Kontrol lera att Intune visas under **hanterings verktyg** och att statusen är **aktive** rad.</span><span class="sxs-lookup"><span data-stu-id="540f7-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="540f7-144">Steg 2: Skapa Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="540f7-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="540f7-145">Skapa tre Azure AD-grupper för varje app.</span><span class="sxs-lookup"><span data-stu-id="540f7-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="540f7-146">I den här tabellen visas de grupper som behövs (tillgängliga, obligatoriska och avinstallationer).</span><span class="sxs-lookup"><span data-stu-id="540f7-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="540f7-147">Typ av tilldelnings program</span><span class="sxs-lookup"><span data-stu-id="540f7-147">App assignment type</span></span> |    <span data-ttu-id="540f7-148">Grupp användning</span><span class="sxs-lookup"><span data-stu-id="540f7-148">Group use</span></span>    | <span data-ttu-id="540f7-149">Exempel på Azure AD-namn</span><span class="sxs-lookup"><span data-stu-id="540f7-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="540f7-150">Kan användas</span><span class="sxs-lookup"><span data-stu-id="540f7-150">Available</span></span> |  <span data-ttu-id="540f7-151">Programmet kommer att vara tillgängligt från företags portalen eller webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="540f7-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="540f7-152">MMD – *program namn* – tillgängligt</span><span class="sxs-lookup"><span data-stu-id="540f7-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="540f7-153">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="540f7-153">Required</span></span> |  <span data-ttu-id="540f7-154">Programmet är installerat på enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="540f7-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="540f7-155">MMD – *program namn* – obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="540f7-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="540f7-156">Avinstallera</span><span class="sxs-lookup"><span data-stu-id="540f7-156">Uninstall</span></span> |  <span data-ttu-id="540f7-157">Programmet avinstalleras från enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="540f7-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="540f7-158">MMD – *program namn* – avinstallera</span><span class="sxs-lookup"><span data-stu-id="540f7-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="540f7-159">Lägg till användare i de här grupperna för att antingen göra programmet tillgängligt, installera programmet eller ta bort programmet från Microsoft Managed Desktop-enheten.</span><span class="sxs-lookup"><span data-stu-id="540f7-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="540f7-160">Steg 3: tilldela appar till dina användare</span><span class="sxs-lookup"><span data-stu-id="540f7-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="540f7-161">**Så här tilldelar du appen till användarna**</span><span class="sxs-lookup"><span data-stu-id="540f7-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="540f7-162">Logga in på [administrations portalen för Microsoft Managed Desktop](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="540f7-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="540f7-163">Välj **appar** i fönstret hanterad skriv bord.</span><span class="sxs-lookup"><span data-stu-id="540f7-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="540f7-164">I apparnas arbets belastning väljer du den app du vill tilldela användare och väljer **Tilldela användar grupper** .</span><span class="sxs-lookup"><span data-stu-id="540f7-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="540f7-165">För det specifika programmet väljer du en tilldelnings typ (tillgänglig, nödvändig, avinstallation) och tilldelar lämplig grupp.</span><span class="sxs-lookup"><span data-stu-id="540f7-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="540f7-166">I fönstret tilldela appar väljer du **OK** .</span><span class="sxs-lookup"><span data-stu-id="540f7-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="540f7-167">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="540f7-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="540f7-168">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="540f7-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="540f7-169">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="540f7-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="540f7-170">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="540f7-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="540f7-171">Distribuera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="540f7-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="540f7-172">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="540f7-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="540f7-173">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="540f7-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="540f7-174">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="540f7-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="540f7-175">Distribuera appar (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="540f7-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
