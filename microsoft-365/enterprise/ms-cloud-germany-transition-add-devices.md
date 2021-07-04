---
title: Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Ytterligare enhetsinformation om tjänster när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 684af01b2d90f44b2cda1cf050d1e4db70f92915
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289445"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="88d8f-103">Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="88d8f-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="88d8f-104">Azure AD-anslutna och registrerade enheter som är anslutna till Microsoft Cloud Deutschland måste migreras efter fas 9 och före fas 10.</span><span class="sxs-lookup"><span data-stu-id="88d8f-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="88d8f-105">Migreringen av en enhet beror på enhetstyper, operativsystem och Azure AD-relation.</span><span class="sxs-lookup"><span data-stu-id="88d8f-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span>

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="88d8f-106">Azure AD-anslutna Windows 10 enheter</span><span class="sxs-lookup"><span data-stu-id="88d8f-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="88d8f-107">Om en Windows 10 är Azure AD-ansluten måste den vara frånkopplad från Azure AD och måste vara ansluten igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span>

<span data-ttu-id="88d8f-108">[![Azure AD-Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88d8f-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="88d8f-109">Om användaren är administratör på en Windows 10 kan användaren avregistrera enheten från Azure AD och åter ansluta till den i tre steg.</span><span class="sxs-lookup"><span data-stu-id="88d8f-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="88d8f-110">Steg 1: Avgör om enheten är Azure-ID ansluten</span><span class="sxs-lookup"><span data-stu-id="88d8f-110">Step 1: Determine if the device is Azure ID joined</span></span>

1. <span data-ttu-id="88d8f-111">Logga in med ditt jobbkonto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-111">Sign in with your work account.</span></span>
2. <span data-ttu-id="88d8f-112">Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="88d8f-113">Leta efter ett konto i listan som är **anslutet till [...]' s Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span>
4. <span data-ttu-id="88d8f-114">Om det finns ett anslutet konto fortsätter du med steg 2.</span><span class="sxs-lookup"><span data-stu-id="88d8f-114">If a connected account exists, proceed with Step 2.</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="88d8f-115">Steg 2: Koppla bort enheten från Azure AD</span><span class="sxs-lookup"><span data-stu-id="88d8f-115">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="88d8f-116">Klicka **på Koppla** från på det anslutna arbets- eller skolkontot.</span><span class="sxs-lookup"><span data-stu-id="88d8f-116">Click **Disconnect** on the connected work or School Account.</span></span>
2. <span data-ttu-id="88d8f-117">Bekräfta frånkopplingen två gånger.</span><span class="sxs-lookup"><span data-stu-id="88d8f-117">Confirm the disconnect twice.</span></span>
3. <span data-ttu-id="88d8f-118">Ange ett lokalt administratörsnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="88d8f-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="88d8f-119">Enheten kopplas från.</span><span class="sxs-lookup"><span data-stu-id="88d8f-119">The device is disconnected.</span></span>
4. <span data-ttu-id="88d8f-120">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-120">Restart the device.</span></span>

### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="88d8f-121">Steg 3: Anslut enheten till Azure AD</span><span class="sxs-lookup"><span data-stu-id="88d8f-121">Step 3: Join the device to Azure AD</span></span>

1. <span data-ttu-id="88d8f-122">Logga in med den lokala administratörens autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="88d8f-122">Sign in with the credentials of the local administrator.</span></span>
2. <span data-ttu-id="88d8f-123">Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="88d8f-124">Klicka **på Anslut**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-124">Click **Connect**.</span></span>
4. <span data-ttu-id="88d8f-125">**VIKTIGT:** Klicka **på Anslut till Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5. <span data-ttu-id="88d8f-126">Ange e-postadressen och lösenordet för ditt arbetskonto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="88d8f-127">Enheten är ansluten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-127">The device is connected.</span></span>
6. <span data-ttu-id="88d8f-128">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-128">Restart the device.</span></span>
7. <span data-ttu-id="88d8f-129">Logga in med e-postadressen och lösenordet för ditt arbetskonto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="88d8f-130">Om användaren inte är administratör för enheten kan en global Azure AD-administratör skapa det lokala administratörskontot på enheten genom att följa den här konfigurationssökvägen och sedan ansluta till enheten igen:</span><span class="sxs-lookup"><span data-stu-id="88d8f-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="88d8f-131">*Inställningar > konton > andra konton > okänd > Lägg till användare utan Microsoft-konto*</span><span class="sxs-lookup"><span data-stu-id="88d8f-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="88d8f-132">För att åter gå med i organisationen kan autentiseringsuppgifterna för alla arbetskonto från din organisation användas i det här steget.</span><span class="sxs-lookup"><span data-stu-id="88d8f-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span>

<span data-ttu-id="88d8f-133">Tänk på att det arbetskonto som användes för att ansluta till enheten automatiskt framhävs som administratör för enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="88d8f-134">Alla andra arbetskonto från organisationen kan logga in på enheten men har inga administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="88d8f-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="88d8f-135">Azure AD-registrerade (arbetsplats-anslutna) Windows 10 enheter</span><span class="sxs-lookup"><span data-stu-id="88d8f-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>

<span data-ttu-id="88d8f-136">Om en Windows 10 är Azure AD-registrerad måste den kopplas bort från Azure AD och anslutas igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="88d8f-137">[![Azure AD-Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88d8f-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="88d8f-138">Steg 1: Avgör om enheten är registrerad Azure-ID</span><span class="sxs-lookup"><span data-stu-id="88d8f-138">Step 1: Determine if the device is Azure ID registered</span></span>

1. <span data-ttu-id="88d8f-139">Logga in med din användare.</span><span class="sxs-lookup"><span data-stu-id="88d8f-139">Sign in with your user.</span></span>
2. <span data-ttu-id="88d8f-140">Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="88d8f-141">Upptäck ditt arbetskonto i listan och kontrollera om det är **anslutet till [...]' s Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="88d8f-142">Om ditt arbetskonto finns i listan men INTE är anslutet till ett Azure AD fortsätter du med steg 2.</span><span class="sxs-lookup"><span data-stu-id="88d8f-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="88d8f-143">I annat fall är enheten en Azure AD-ansluten enhet och du måste hänvisa till [Azure AD-Windows 10 enheter.](#azure-ad-joined-windows-10-devices)</span><span class="sxs-lookup"><span data-stu-id="88d8f-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="88d8f-144">Steg 2: Koppla bort enheten från Azure AD</span><span class="sxs-lookup"><span data-stu-id="88d8f-144">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="88d8f-145">Klicka på ditt arbetskonto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-145">Click on your work account.</span></span> <span data-ttu-id="88d8f-146">Knapparna *Info och* *Koppla från* visas.</span><span class="sxs-lookup"><span data-stu-id="88d8f-146">The buttons *Info* and *Disconnect* appear.</span></span>
2. <span data-ttu-id="88d8f-147">Klicka **på Koppla från.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-147">Click **Disconnect**.</span></span>
3. <span data-ttu-id="88d8f-148">Bekräfta kontoborttagningen från enheten genom att klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-148">Confirm account removal from the device by clicking **Yes**.</span></span>

### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="88d8f-149">Steg 3: Anslut till Azure AD</span><span class="sxs-lookup"><span data-stu-id="88d8f-149">Step 3: Connect the device to Azure AD</span></span>

1. <span data-ttu-id="88d8f-150">Klicka **på Anslut**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-150">Click **Connect**.</span></span>
2. <span data-ttu-id="88d8f-151">Ange e-postadressen till ditt arbetskonto och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-151">Enter the email address of your work account and click **Next**.</span></span>
3. <span data-ttu-id="88d8f-152">Ange lösenordet för ditt arbetskonto och klicka på **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-152">Enter the password of your work account and click **Sign in**.</span></span>
4. <span data-ttu-id="88d8f-153">Bekräfta genom att klicka **på Klar**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="88d8f-154">Ditt arbetskonto visas igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="88d8f-155">Android</span><span class="sxs-lookup"><span data-stu-id="88d8f-155">Android</span></span>

<span data-ttu-id="88d8f-156">För Android måste användarna avregistrera sig och registrera sina enheter igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="88d8f-157">Det kan du göra via Microsoft Authenticator eller det Företagsportal appen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span>

- <span data-ttu-id="88d8f-158">Från Microsoft Authenticator kan användarna gå till **enhetsregistreringen Inställningar >.**</span><span class="sxs-lookup"><span data-stu-id="88d8f-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="88d8f-159">Därifrån kan användare avregistrera sig och registrera sin enhet igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-159">From there users can unregister and re-register their device.</span></span>

- <span data-ttu-id="88d8f-160">I Företagsportal enheter kan användarna gå till **fliken Enheter** och ta bort enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="88d8f-161">Därefter kan du registrera enheten igen med hjälp av Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="88d8f-161">After that, re-enroll the device by using Company Portal.</span></span>

- <span data-ttu-id="88d8f-162">Användare kan också avregistrera och registrera igen genom att ta bort kontot från sidan kontoinställningar och sedan lägga till arbetskontot igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="88d8f-163">Så här avregistrerar du och registrerar om enheten på Android med hjälp av Microsoft Authenticator appen:</span><span class="sxs-lookup"><span data-stu-id="88d8f-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1. <span data-ttu-id="88d8f-164">Öppna Microsoft Authenticator och gå till **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2. <span data-ttu-id="88d8f-165">Välj **Enhetsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-165">Select **Device registration**.</span></span>
3. <span data-ttu-id="88d8f-166">Avregistrera enheten genom att välja **Avregistrera**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-166">Unregister the device by selecting **Unregister**.</span></span>
4. <span data-ttu-id="88d8f-167">För **enhetsregistrering** registrerar du enheten igen genom att skriva din e-postadress och väljer **registrera**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="88d8f-168">Så här avregistrerar du och registrerar en Android-enhet på Inställningar Android-enhet:</span><span class="sxs-lookup"><span data-stu-id="88d8f-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1. <span data-ttu-id="88d8f-169">Öppna **Enhetshanteraren Inställningar** gå till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-169">Open **Device Settings** and go to **Accounts**.</span></span>
2. <span data-ttu-id="88d8f-170">Välj det arbetskonto du vill registrera igen och välj Ta **bort konto**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3. <span data-ttu-id="88d8f-171">När kontot har tagits bort går du till **sidan Konton** och väljer Lägg till konto **> Arbetskonto**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4. <span data-ttu-id="88d8f-172">I **Workplace Join** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="88d8f-173">Så här avregistrerar du och registrerar om enheten på Android från Företagsportal:</span><span class="sxs-lookup"><span data-stu-id="88d8f-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1. <span data-ttu-id="88d8f-174">Starta Företagsportal gå till **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="88d8f-174">Launch Company Portal and go to **Devices** tab.</span></span>
2. <span data-ttu-id="88d8f-175">Välj enheten om du vill se enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-175">Select the device to see the device details.</span></span>
3. <span data-ttu-id="88d8f-176">På ellipsmenyn (tre punkter) väljer du Ta **bort** enhet och slutför borttagningen genom att bekräfta i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="88d8f-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4. <span data-ttu-id="88d8f-177">Du bör nu vara utloggad från Företagsportal appen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="88d8f-178">Välj **Logga in** för att registrera enheten igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="88d8f-179">Mer information om åtgärder som krävs under migreringsfasen av den här arbetsbelastningen, eller som påverkar administration eller användning, finns i informationen om Azure Active Directory (Azure AD) i Ytterligare Azure AD-information för migreringen från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="88d8f-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="88d8f-180">iOS</span><span class="sxs-lookup"><span data-stu-id="88d8f-180">iOS</span></span>

<span data-ttu-id="88d8f-181">På iOS-enheter måste en användare manuellt ta bort cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla inbyggda appar på enheten.</span><span class="sxs-lookup"><span data-stu-id="88d8f-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="88d8f-182">Steg 1: Om det finns tar du bort kontot från Microsoft Authenticator programmet</span><span class="sxs-lookup"><span data-stu-id="88d8f-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="88d8f-183">Tryck på kontot i Microsoft Authenticator appen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="88d8f-184">Tryck **Inställningar** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="88d8f-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="88d8f-185">Om du inte ser ikonen **Inställningar** kanske du inte använder den senaste versionen av Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="88d8f-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="88d8f-186">Tryck på **knappen Ta bort** konto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="88d8f-187">Tryck **på Alla appar på den här enheten**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-187">Tap **All apps on this device**.</span></span>

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="88d8f-188">Steg 2: Avregistrera enheten från Microsoft Authenticator appen</span><span class="sxs-lookup"><span data-stu-id="88d8f-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="88d8f-189">Tryck på menyikonen i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="88d8f-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="88d8f-190">Tryck **Inställningar** och sedan **på Enhetsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="88d8f-190">Tap **Settings** and then **Device Registration**.</span></span>
3. <span data-ttu-id="88d8f-191">Om ditt konto visas trycker du på **Avregistrera enhet** **och Fortsätt** i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="88d8f-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="88d8f-192">Därefter bör du inte se något konto.</span><span class="sxs-lookup"><span data-stu-id="88d8f-192">You should see no account after that.</span></span>

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="88d8f-193">Steg 3: Logga ut från enskilda appar om det behövs</span><span class="sxs-lookup"><span data-stu-id="88d8f-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="88d8f-194">Användare kan gå till enskilda appar som Outlook, Teams och OneDrive och ta bort konton från dessa program.</span><span class="sxs-lookup"><span data-stu-id="88d8f-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="88d8f-195">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="88d8f-195">Frequently asked questions</span></span>

<span data-ttu-id="88d8f-196">**Hur vet jag om min organisation påverkas?**</span><span class="sxs-lookup"><span data-stu-id="88d8f-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="88d8f-197">Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några Azure AD-registrerade eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="88d8f-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="88d8f-198">Om din organisation har Azure AD registrerat eller Azure AD-anslutna enheter måste organisationen följa instruktionerna på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="88d8f-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="88d8f-199">**När registrerar mina användare sina enheter igen?**</span><span class="sxs-lookup"><span data-stu-id="88d8f-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="88d8f-200">Det är viktigt att du bara avregistrerar och registrerar dina enheter igen när [fas 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) är klar.</span><span class="sxs-lookup"><span data-stu-id="88d8f-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="88d8f-201">Du måste slutföra omregistreringen innan fas 10 startar, annars kan åtkomsten till din enhet gå förlorade.</span><span class="sxs-lookup"><span data-stu-id="88d8f-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="88d8f-202">**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**</span><span class="sxs-lookup"><span data-stu-id="88d8f-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="88d8f-203">Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="88d8f-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="88d8f-204">Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter det datum då organisationen har passerat [fas 9 i migreringsprocessen.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="88d8f-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="88d8f-205">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="88d8f-205">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d8f-206">Intune-tjänstens huvudnamn aktiveras efter fas [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)i migreringsprocessen, vilket antyder aktiveringen av Azure AD-enhetsregistrering.</span><span class="sxs-lookup"><span data-stu-id="88d8f-206">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="88d8f-207">Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen.</span><span class="sxs-lookup"><span data-stu-id="88d8f-207">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="88d8f-208">Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot Azure Active Directory PowerShell för Graph modul.</span><span class="sxs-lookup"><span data-stu-id="88d8f-208">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="88d8f-209">Mer information</span><span class="sxs-lookup"><span data-stu-id="88d8f-209">More information</span></span>

<span data-ttu-id="88d8f-210">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="88d8f-210">Getting started:</span></span>

- [<span data-ttu-id="88d8f-211">Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena</span><span class="sxs-lookup"><span data-stu-id="88d8f-211">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="88d8f-212">Migreringshjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="88d8f-212">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="88d8f-213">Så här väljer du in för migrering</span><span class="sxs-lookup"><span data-stu-id="88d8f-213">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="88d8f-214">Kundupplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="88d8f-214">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="88d8f-215">Flytta genom övergången:</span><span class="sxs-lookup"><span data-stu-id="88d8f-215">Moving through the transition:</span></span>

- [<span data-ttu-id="88d8f-216">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="88d8f-216">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="88d8f-217">Ytterligare arbete</span><span class="sxs-lookup"><span data-stu-id="88d8f-217">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="88d8f-218">Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="88d8f-218">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="88d8f-219">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="88d8f-219">Cloud apps:</span></span>

- [<span data-ttu-id="88d8f-220">Information om Dynamics 365-migreringsprogram</span><span class="sxs-lookup"><span data-stu-id="88d8f-220">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="88d8f-221">Power BI i migreringsprogrammet</span><span class="sxs-lookup"><span data-stu-id="88d8f-221">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="88d8f-222">Komma igång med din Microsoft Teams uppgradering</span><span class="sxs-lookup"><span data-stu-id="88d8f-222">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
