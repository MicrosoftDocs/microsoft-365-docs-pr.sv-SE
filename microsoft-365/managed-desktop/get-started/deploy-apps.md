---
title: Distribuera appar till enheter
description: Information om hur du lägger till och distribuerar appar Microsoft Hanterat skrivbord enheter.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922032"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="a3f6d-104">Distribuera appar till enheter</span><span class="sxs-lookup"><span data-stu-id="a3f6d-104">Deploy apps to devices</span></span>
<span data-ttu-id="a3f6d-105">I introduktionen till Microsoft Hanterat skrivbord ingår att lägga till och distribuera program på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="a3f6d-106">När du har använt Microsoft Hanterat skrivbord kan du lägga till och distribuera dina program.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="a3f6d-107">Den övergripande processen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="a3f6d-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="a3f6d-108">[Lägga till appar Microsoft Hanterat skrivbord](#1) -portalen – Det kan vara befintliga verksamhetsbaserade appar (LOB) eller appar från Microsoft Store för företag som du synkroniserat med Intune.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="a3f6d-109">[Skapa Azure Active Directory (AD) för apptilldelning](#2) – Du använder grupperna för att hantera apptilldelning.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="a3f6d-110">Tilldela dina användare appar</span><span class="sxs-lookup"><span data-stu-id="a3f6d-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="a3f6d-111">Steg 1: Lägga till appar Microsoft Hanterat skrivbord portalen</span><span class="sxs-lookup"><span data-stu-id="a3f6d-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="a3f6d-112">Du kan lägga [till Win32- Windows MSI-baserade](#lob-apps)appar eller [Microsoft Store för företag-appar](#msfb-apps) i Microsoft Hanterat skrivbord och sedan distribuera dem till Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="a3f6d-113">Win32 eller Windows MSI-baserade appar att Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a3f6d-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="a3f6d-114">Du kan lägga till verksamhetsbaserade appar (LOB) i Microsoft Hanterat skrivbord portal.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="a3f6d-115">Mer information om krav för appar som är installerade Microsoft Hanterat skrivbord enheter finns i [Microsoft Hanterat skrivbord för appar.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="a3f6d-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="a3f6d-116">I den här proceduren väljer du vilken typ av program du vill lägga till och konfigurerar och laddar sedan upp programkällan.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="a3f6d-117">**Så här lägger du till en LOB-app Windows appen på Microsoft Hanterat skrivbord portalen**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="a3f6d-118">Du kan logga in Microsoft Hanterat skrivbord-portalen eller logga in på Intune och sedan söka efter Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="a3f6d-119">Vi visar hur du loggar in Microsoft Hanterat skrivbord portalen.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="a3f6d-120">Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a3f6d-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="a3f6d-121">Under **Lager** väljer du **Appar**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="a3f6d-122">I apparbetsbelastningen väljer du Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="a3f6d-123">I **Lägg till app** väljer du **Verksamhets- eller** Windows **(Win32)**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="a3f6d-124">Om du valde verksamhetsbaserade **appar**, se [Lägga till en Windows-app](/intune/lob-apps-windows) för företag i Microsoft Intune för instruktioner om att lägga till och konfigurera verksamhetsbaserade appar.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="a3f6d-125">Om du valde **Windows (Win32)** finns instruktioner om hur du lägger till och konfigurerar Windows appar i [Win32-apphantering.](/intune/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="a3f6d-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="a3f6d-126">Microsoft Store för företag appar</span><span class="sxs-lookup"><span data-stu-id="a3f6d-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="a3f6d-127">Om du inte har registrerat dig hos Microsoft Store för företag kan du registrera dig när du handlar för appar.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="a3f6d-128">När du har dina appar kan du synkronisera dem med Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="a3f6d-129">**Köpa appar från Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="a3f6d-130">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med Microsoft Store för företag administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a3f6d-131">Välj **Köp för min grupp**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="a3f6d-132">Använd Sök för att hitta den app du vill använda och välj sedan appen.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="a3f6d-133">Välj Skaffa appen på **produktinformationen.**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="a3f6d-134">Microsoft Store lägger till appen **i Dina produkter** för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="a3f6d-135">**Tvinga fram synkronisering mellan Intune och Microsoft Store för företag**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="a3f6d-136">Logga in Microsoft Endpoint Manager [administrationscentret](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="a3f6d-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="a3f6d-137">Välj **Kopplingar och** token för  >  **klientorganisationsadministration**  >  **Microsoft Store för företag**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="a3f6d-138">Välj **Synkronisera** för att hämta de appar som du har köpt från Microsoft Store till Intune.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="a3f6d-139">**Verifiera att en synkronisering mellan Intune och Microsoft Store för företag är aktiv**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="a3f6d-140">Logga in på [Microsoft Store för företag](https://businessstore.microsoft.com) med Microsoft Store för företag administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a3f6d-141">Välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-141">Select **Manage**.</span></span>
3. <span data-ttu-id="a3f6d-142">Välj **Inställningar** och sedan **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="a3f6d-143">Under **Hanteringsverktyg** kontrollerar du att Intune visas och att statusen är **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="a3f6d-144">Steg 2: Skapa Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="a3f6d-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="a3f6d-145">Skapa tre Azure AD-grupper för varje app.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="a3f6d-146">I den här tabellen visas de grupper du behöver (Tillgänglig, Obligatoriskt och Avinstallera).</span><span class="sxs-lookup"><span data-stu-id="a3f6d-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="a3f6d-147">Apptilldelningstyp</span><span class="sxs-lookup"><span data-stu-id="a3f6d-147">App assignment type</span></span> |    <span data-ttu-id="a3f6d-148">Gruppanvändning</span><span class="sxs-lookup"><span data-stu-id="a3f6d-148">Group use</span></span>    | <span data-ttu-id="a3f6d-149">Exempel på Azure AD-namn</span><span class="sxs-lookup"><span data-stu-id="a3f6d-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="a3f6d-150">Kan användas</span><span class="sxs-lookup"><span data-stu-id="a3f6d-150">Available</span></span> |  <span data-ttu-id="a3f6d-151">Appen är tillgänglig från Företagsportal app eller webbplats.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="a3f6d-152">MMD – *appnamn* – tillgänglig</span><span class="sxs-lookup"><span data-stu-id="a3f6d-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="a3f6d-153">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a3f6d-153">Required</span></span> |  <span data-ttu-id="a3f6d-154">Appen installeras på enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="a3f6d-155">MMD – *appnamn* – obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="a3f6d-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="a3f6d-156">Avinstallera</span><span class="sxs-lookup"><span data-stu-id="a3f6d-156">Uninstall</span></span> |  <span data-ttu-id="a3f6d-157">Appen avinstalleras från enheter i de valda grupperna.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="a3f6d-158">MMD – *appnamn* – Avinstallera</span><span class="sxs-lookup"><span data-stu-id="a3f6d-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="a3f6d-159">Lägg till användarna i de här grupperna för att antingen göra programmet tillgängligt, installera appen eller ta bort programmet från Microsoft Hanterat skrivbord enhet.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="a3f6d-160">Steg 3: Tilldela appar till användarna</span><span class="sxs-lookup"><span data-stu-id="a3f6d-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="a3f6d-161">**Så här tilldelar du appen till användarna**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="a3f6d-162">Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a3f6d-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a3f6d-163">Välj Appar i fönstret **Hanterat skrivbord.**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="a3f6d-164">I apparbetsbelastningen väljer du det program du vill tilldela användare till och väljer **Tilldela användare grupper.**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="a3f6d-165">För den specifika appen väljer du en uppgiftstyp (Tillgänglig, Obligatoriskt, Avinstallera) och tilldelar lämplig grupp.</span><span class="sxs-lookup"><span data-stu-id="a3f6d-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="a3f6d-166">I fönstret Tilldela appar väljer du **OK.**</span><span class="sxs-lookup"><span data-stu-id="a3f6d-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="a3f6d-167">Steg för att komma igång med Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="a3f6d-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="a3f6d-168">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="a3f6d-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="a3f6d-169">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="a3f6d-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="a3f6d-170">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="a3f6d-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="a3f6d-171">Distribuera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="a3f6d-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="a3f6d-172">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="a3f6d-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="a3f6d-173">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="a3f6d-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="a3f6d-174">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="a3f6d-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="a3f6d-175">Distribuera program (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="a3f6d-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->