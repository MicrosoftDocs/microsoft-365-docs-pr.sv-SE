---
title: Appbaserad distribution av Microsoft Defender för Slutpunkt i iOS
ms.reviewer: ''
description: Här beskrivs hur du distribuerar Microsoft Defender för slutpunkt i iOS med hjälp av en app
keywords: microsoft, defender, Microsoft Defender för slutpunkt, ios, app, installation, distribuera, avinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 62eefbd17b826aa2cfb541c04ba206d0f58f9bbf
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935059"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="1e187-104">Distribuera Microsoft Defender för Slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="1e187-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e187-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1e187-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e187-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1e187-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e187-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e187-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1e187-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1e187-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e187-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1e187-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1e187-110">I det här avsnittet beskrivs distribution av Defender för Slutpunkt på iOS på Registrerade enheter i Intune-företagsportal.</span><span class="sxs-lookup"><span data-stu-id="1e187-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="1e187-111">Mer information om registrering av Intune-enheter finns i [Registrera iOS-/iPadOS-enheter i Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="1e187-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e187-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1e187-112">Before you begin</span></span>

- <span data-ttu-id="1e187-113">Kontrollera att du har åtkomst till [administrationscentret för Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="1e187-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="1e187-114">Se till att iOS-registreringen utförs för dina användare.</span><span class="sxs-lookup"><span data-stu-id="1e187-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="1e187-115">Användarna måste ha en Defender för slutpunktslicens tilldelad för att kunna använda Defender för slutpunkt i iOS.</span><span class="sxs-lookup"><span data-stu-id="1e187-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="1e187-116">Anvisningar om [hur du tilldelar licenser](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) finns i Tilldela licenser till användare.</span><span class="sxs-lookup"><span data-stu-id="1e187-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="1e187-117">Microsoft Defender för slutpunkt på iOS är nu tillgängligt i [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="1e187-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="1e187-118">Distributionssteg</span><span class="sxs-lookup"><span data-stu-id="1e187-118">Deployment steps</span></span>

<span data-ttu-id="1e187-119">Distribuera Defender för Slutpunkt i iOS via Intune-företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="1e187-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="1e187-120">Lägg till en iOS Store-app</span><span class="sxs-lookup"><span data-stu-id="1e187-120">Add iOS store app</span></span>

1. <span data-ttu-id="1e187-121">I [administrationscentret för Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)går du till **Appar**  ->  **iOS/iPadOS Lägg**  ->  **till**  ->  **iOS Store-app och** klickar på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="1e187-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-122">![Bild av Administrationscenter för Microsoft Endpoint Manager1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="1e187-123">På sidan Lägg till app klickar du på **Sök i App Store** och skriver Microsoft Defender **Endpoint** i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="1e187-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="1e187-124">I avsnittet med sökresultat klickar du på *Microsoft Defender Endpoint och* klickar på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="1e187-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="1e187-125">Välj **iOS 11.0** som Minimum-operativsystem.</span><span class="sxs-lookup"><span data-stu-id="1e187-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="1e187-126">Granska resten av informationen om programmet och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1e187-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="1e187-127">Gå till *avsnittet Obligatoriska* i avsnittet Uppgifter **och** välj Lägg **till grupp**.</span><span class="sxs-lookup"><span data-stu-id="1e187-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="1e187-128">Du kan sedan välja den användargrupp(er) som du vill rikta Defender mot Endpoint i iOS-appen.</span><span class="sxs-lookup"><span data-stu-id="1e187-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="1e187-129">Klicka **på Markera** och sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="1e187-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e187-130">Den valda användargruppen ska bestå av intune-registrerade användare.</span><span class="sxs-lookup"><span data-stu-id="1e187-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-131">![Bild av Administrationscenter för Microsoft Endpoint Manager2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="1e187-132">I avsnittet *Granska + Skapa* kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="1e187-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="1e187-133">Inom en liten stund bör appen Defender för Slutpunkt skapas korrekt och ett meddelande bör visas i det övre högra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="1e187-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="1e187-134">På sidan med appinformation som  visas i avsnittet Övervaka väljer du Enhetsinstallationsstatus **för** att verifiera att enhetsinstallationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1e187-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-135">![Bild av Administrationscenter för Microsoft Endpoint Manager3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="1e187-136">Fullständig registrering och kontrollstatus</span><span class="sxs-lookup"><span data-stu-id="1e187-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="1e187-137">När Defender för slutpunkt på iOS har installerats på enheten visas appikonen.</span><span class="sxs-lookup"><span data-stu-id="1e187-137">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![En skärmbild av en beskrivning av en smartphone som genererats automatiskt](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="1e187-139">Tryck på appikonen Defender för slutpunkt och följ instruktionerna på skärmen för att slutföra introduktionsstegen.</span><span class="sxs-lookup"><span data-stu-id="1e187-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="1e187-140">Informationen innefattar godkännande av iOS-behörigheter som krävs av Defender för Endpoint på iOS.</span><span class="sxs-lookup"><span data-stu-id="1e187-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="1e187-141">Om onboarding lyckas visas enheten i listan Enheter i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="1e187-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-142">![En skärmbild av en beskrivning av en mobiltelefon automatiskt genererad](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="1e187-143">Konfigurera Microsoft Defender för slutpunkt för övervakat läge</span><span class="sxs-lookup"><span data-stu-id="1e187-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="1e187-144">Microsoft Defender för Slutpunkt för iOS-appen har särskild kapacitet för övervakade iOS-/iPadOS-enheter, givet de utökade hanteringsfunktionerna som tillhandahålls av plattformen på dessa typer av enheter.</span><span class="sxs-lookup"><span data-stu-id="1e187-144">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="1e187-145">Om du vill dra nytta av de här funktionerna behöver appen Defender för slutpunkt veta om en enhet är i övervakat läge.</span><span class="sxs-lookup"><span data-stu-id="1e187-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="1e187-146">Konfigurera övervakat läge via Intune</span><span class="sxs-lookup"><span data-stu-id="1e187-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="1e187-147">Med Intune kan du konfigurera appen Defender för iOS via en princip för appkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1e187-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1e187-148">Den här appkonfigurationsprincipen för övervakade enheter gäller endast hanterade enheter och bör riktas för alla hanterade iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="1e187-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="1e187-149">Logga in på [administrationscentret för Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) gå till Appkonfigurationsprinciper   >  **Lägg**  >  **till**.</span><span class="sxs-lookup"><span data-stu-id="1e187-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="1e187-150">Klicka på **Hanterade enheter.**</span><span class="sxs-lookup"><span data-stu-id="1e187-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-151">![Bild av Administrationscenter för Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="1e187-152">Ange *följande* information på sidan Skapa appkonfigurationsprincip:</span><span class="sxs-lookup"><span data-stu-id="1e187-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="1e187-153">Principnamn</span><span class="sxs-lookup"><span data-stu-id="1e187-153">Policy Name</span></span>
    - <span data-ttu-id="1e187-154">Plattform: Välj iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="1e187-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="1e187-155">Riktad app: Välj **Microsoft Defender ATP** i listan</span><span class="sxs-lookup"><span data-stu-id="1e187-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-156">![Bild av Administrationscenter för Microsoft Endpoint Manager5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="1e187-157">På nästa skärm väljer du **Använd konfigurationsdesignern** som format.</span><span class="sxs-lookup"><span data-stu-id="1e187-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="1e187-158">Ange följande egenskap:</span><span class="sxs-lookup"><span data-stu-id="1e187-158">Specify the following property:</span></span>
    - <span data-ttu-id="1e187-159">Konfigurationsnyckel: issupervised</span><span class="sxs-lookup"><span data-stu-id="1e187-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="1e187-160">Värdetyp: Sträng</span><span class="sxs-lookup"><span data-stu-id="1e187-160">Value type: String</span></span>
    - <span data-ttu-id="1e187-161">Konfigurationsvärde: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="1e187-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-162">![Bild av Administrationscenter för Microsoft Endpoint Manager](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="1e187-163">Klicka **på Nästa** så att sidan **Omfattningstaggar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="1e187-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="1e187-164">Omfattningstaggar är valfria.</span><span class="sxs-lookup"><span data-stu-id="1e187-164">Scope tags are optional.</span></span> <span data-ttu-id="1e187-165">Klicka **på Nästa** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="1e187-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="1e187-166">På sidan **Uppgifter väljer** du de grupper som ska få den här profilen.</span><span class="sxs-lookup"><span data-stu-id="1e187-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="1e187-167">I det här scenariot är det bäst att rikta alla **enheter mot mål.**</span><span class="sxs-lookup"><span data-stu-id="1e187-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="1e187-168">Mer information om hur du tilldelar profiler finns i [Tilldela användar- och enhetsprofiler.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="1e187-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="1e187-169">När du distribuerar till användargrupper måste en användare logga in på en enhet innan principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1e187-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="1e187-170">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1e187-170">Click **Next**.</span></span>

1. <span data-ttu-id="1e187-171">På sidan **Granska + skapa** väljer du Skapa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="1e187-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="1e187-172">Den nya profilen visas i listan över konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="1e187-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="1e187-173">För förbättrade funktioner mot nätfiske kan du därefter distribuera en anpassad profil på de övervakade iOS-enheterna.</span><span class="sxs-lookup"><span data-stu-id="1e187-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="1e187-174">Följ stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="1e187-174">Follow the steps below:</span></span>
    - <span data-ttu-id="1e187-175">Ladda ned konfigurationsprofilen från [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="1e187-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="1e187-176">Gå till  ->  **Konfigurationsprofiler för enheter iOS/iPadOS**  ->    ->  **Skapa profil**</span><span class="sxs-lookup"><span data-stu-id="1e187-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e187-177">![Bild av Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="1e187-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="1e187-178">Ange ett namn på profilen.</span><span class="sxs-lookup"><span data-stu-id="1e187-178">Provide a name of the profile.</span></span> <span data-ttu-id="1e187-179">När du uppmanas att importera en konfigurationsprofilfil väljer du den som hämtats ovan.</span><span class="sxs-lookup"><span data-stu-id="1e187-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="1e187-180">I avsnittet **Uppgift** väljer du den enhetsgrupp för vilken du vill använda den här profilen.</span><span class="sxs-lookup"><span data-stu-id="1e187-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="1e187-181">Det är en bra metod att detta ska tillämpas på alla hanterade iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="1e187-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="1e187-182">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="1e187-182">Click **Next**.</span></span>
    - <span data-ttu-id="1e187-183">På sidan **Granska + skapa** väljer du Skapa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="1e187-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="1e187-184">Den nya profilen visas i listan över konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="1e187-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e187-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1e187-185">Next Steps</span></span>

[<span data-ttu-id="1e187-186">Konfigurera Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="1e187-186">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
