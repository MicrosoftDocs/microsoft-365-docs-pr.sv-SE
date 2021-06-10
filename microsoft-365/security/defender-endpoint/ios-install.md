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
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842307"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="d57f9-104">Distribuera Microsoft Defender för Slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="d57f9-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d57f9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d57f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="d57f9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d57f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d57f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d57f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d57f9-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d57f9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d57f9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d57f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d57f9-110">I det här avsnittet beskrivs hur du distribuerar Defender för Slutpunkt på iOS Intune-företagsportal registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="d57f9-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="d57f9-111">Mer information om registrering av Intune-enheter finns i [Registrera iOS-/iPadOS-enheter i Intune.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="d57f9-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d57f9-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d57f9-112">Before you begin</span></span>

- <span data-ttu-id="d57f9-113">Kontrollera att du har åtkomst till [administrationscentret för Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="d57f9-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="d57f9-114">Se till att iOS-registreringen utförs för dina användare.</span><span class="sxs-lookup"><span data-stu-id="d57f9-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="d57f9-115">Användarna måste ha en Defender för slutpunktslicens tilldelad för att kunna använda Defender för slutpunkt i iOS.</span><span class="sxs-lookup"><span data-stu-id="d57f9-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="d57f9-116">Anvisningar om [hur du tilldelar licenser](/azure/active-directory/users-groups-roles/licensing-groups-assign) finns i Tilldela licenser till användare.</span><span class="sxs-lookup"><span data-stu-id="d57f9-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d57f9-117">Microsoft Defender för slutpunkt på iOS är tillgängligt i [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="d57f9-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="d57f9-118">Distributionssteg</span><span class="sxs-lookup"><span data-stu-id="d57f9-118">Deployment steps</span></span>

<span data-ttu-id="d57f9-119">Distribuera Defender för Slutpunkt på iOS via Intune-företagsportal.</span><span class="sxs-lookup"><span data-stu-id="d57f9-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="d57f9-120">Lägg till en iOS Store-app</span><span class="sxs-lookup"><span data-stu-id="d57f9-120">Add iOS store app</span></span>

1. <span data-ttu-id="d57f9-121">I [administrationscentret för Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)går du till **Appar**  ->  **iOS/iPadOS Lägg**  ->  **till**  ->  **iOS Store-app och** klickar på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-122">![Bild av Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="d57f9-123">På sidan Lägg till app klickar du på **Sök i App Store** och skriver Microsoft Defender **Endpoint** i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="d57f9-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="d57f9-124">I avsnittet med sökresultat klickar du på *Microsoft Defender Endpoint och* klickar på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="d57f9-125">Välj **iOS 11.0** som Minimum-operativsystem.</span><span class="sxs-lookup"><span data-stu-id="d57f9-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="d57f9-126">Granska resten av informationen om programmet och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="d57f9-127">Gå till *avsnittet Obligatoriska* i avsnittet Uppgifter **och** välj Lägg **till grupp**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="d57f9-128">Du kan sedan välja den användargrupp(er) som du vill rikta Defender mot Endpoint i iOS-appen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="d57f9-129">Klicka **på Markera** och sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d57f9-130">Den valda användargruppen ska bestå av intune-registrerade användare.</span><span class="sxs-lookup"><span data-stu-id="d57f9-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-131">![Bild av Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="d57f9-132">I avsnittet *Granska + Skapa* kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="d57f9-133">Inom en liten stund bör appen Defender för Slutpunkt skapas korrekt och ett meddelande bör visas i det övre högra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="d57f9-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="d57f9-134">På sidan med appinformation som  visas i avsnittet Övervaka väljer du Enhetsinstallationsstatus **för** att verifiera att enhetsinstallationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="d57f9-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-135">![Bild av Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="d57f9-136">Automatisk registrering av VPN-profil (förenklad registrering)</span><span class="sxs-lookup"><span data-stu-id="d57f9-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="d57f9-137">Administratörer kan konfigurera automatisk konfiguration av VPN-profilen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="d57f9-138">Det här ställer automatiskt in Defender för Endpoint VPN-profilen utan att användaren behöver göra det under registrering.</span><span class="sxs-lookup"><span data-stu-id="d57f9-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="d57f9-139">Observera att VPN används för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="d57f9-140">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="d57f9-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="d57f9-141">I [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)går du till   ->  **Konfigurationsprofiler för enheter** Skapa  ->  **profil**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="d57f9-142">Välj **Plattform** som **iOS/iPadOS** och **Profiltyp** som **VPN.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="d57f9-143">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-143">Click **Create**.</span></span>
1. <span data-ttu-id="d57f9-144">Skriv in ett namn på profilen och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="d57f9-145">Välj **Anpassad VPN** för Anslutningstyp och ange följande i avsnittet **Bas-VPN:**</span><span class="sxs-lookup"><span data-stu-id="d57f9-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="d57f9-146">Anslutningsnamn = Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="d57f9-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="d57f9-147">VPN-serveradress = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="d57f9-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="d57f9-148">Autentiseringsmetod = "Användarnamn och lösenord"</span><span class="sxs-lookup"><span data-stu-id="d57f9-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="d57f9-149">Delade tunnlar = Inaktivera</span><span class="sxs-lookup"><span data-stu-id="d57f9-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="d57f9-150">VPN-identifierare = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="d57f9-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="d57f9-151">I paren med nyckelvärden anger du nyckeln **AutoOnboard och** anger värdet **till True**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="d57f9-152">Typ av automatisk VPN = On-demand VPN</span><span class="sxs-lookup"><span data-stu-id="d57f9-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="d57f9-153">Klicka **på** Lägg **till för på** begäran-regler och välj Jag vill göra följande = Upprätta **VPN**, Jag vill begränsa till = **Alla domäner.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![En skärmbild av VPN-profilkonfiguration](images/ios-deploy-8.png)

1. <span data-ttu-id="d57f9-155">Klicka på Nästa och tilldela profilen till riktade användare.</span><span class="sxs-lookup"><span data-stu-id="d57f9-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="d57f9-156">I avsnittet *Granska + Skapa* kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="d57f9-157">Fullständig registrering och kontrollstatus</span><span class="sxs-lookup"><span data-stu-id="d57f9-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="d57f9-158">När Defender för slutpunkt på iOS har installerats på enheten visas appikonen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![En skärmbild av en beskrivning av en smartphone som genererats automatiskt](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="d57f9-160">Tryck på appikonen Defender för slutpunkt (MSDefender) och följ anvisningarna på skärmen för att slutföra introduktionsstegen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="d57f9-161">Informationen innefattar godkännande av iOS-behörigheter som krävs av Defender för Endpoint på iOS.</span><span class="sxs-lookup"><span data-stu-id="d57f9-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="d57f9-162">Vid lyckad registrering börjar enheten visas i listan Enheter i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="d57f9-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-163">![En skärmbild av en beskrivning av en mobiltelefon automatiskt genererad](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="d57f9-164">Konfigurera Microsoft Defender för slutpunkt för övervakat läge</span><span class="sxs-lookup"><span data-stu-id="d57f9-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="d57f9-165">Microsoft Defender för Slutpunkt för iOS-appen har särskild kapacitet för övervakade iOS-/iPadOS-enheter, givet de utökade hanteringsfunktionerna som tillhandahålls av plattformen på dessa typer av enheter.</span><span class="sxs-lookup"><span data-stu-id="d57f9-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="d57f9-166">Om du vill dra nytta av de här funktionerna behöver appen Defender för slutpunkt veta om en enhet är i övervakat läge.</span><span class="sxs-lookup"><span data-stu-id="d57f9-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="d57f9-167">Konfigurera övervakat läge via Intune</span><span class="sxs-lookup"><span data-stu-id="d57f9-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="d57f9-168">Med Intune kan du konfigurera appen Defender för iOS via en princip för appkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d57f9-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d57f9-169">Den här appkonfigurationsprincipen för övervakade enheter gäller endast hanterade enheter och bör riktas för alla hanterade iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="d57f9-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="d57f9-170">Logga in på [administrationscentret Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) gå till Programkonfigurationsprinciper,   >  **Lägg**  >  **till**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="d57f9-171">Klicka på **Hanterade enheter.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-172">![Bild av Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="d57f9-173">Ange *följande* information på sidan Skapa appkonfigurationsprincip:</span><span class="sxs-lookup"><span data-stu-id="d57f9-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="d57f9-174">Principnamn</span><span class="sxs-lookup"><span data-stu-id="d57f9-174">Policy Name</span></span>
    - <span data-ttu-id="d57f9-175">Plattform: Välj iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="d57f9-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="d57f9-176">Riktad app: Välj **Microsoft Defender Endpoint** i listan</span><span class="sxs-lookup"><span data-stu-id="d57f9-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-177">![Bild av Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="d57f9-178">På nästa skärm väljer du **Använd konfigurationsdesignern** som format.</span><span class="sxs-lookup"><span data-stu-id="d57f9-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="d57f9-179">Ange följande egenskap:</span><span class="sxs-lookup"><span data-stu-id="d57f9-179">Specify the following property:</span></span>
    - <span data-ttu-id="d57f9-180">Konfigurationsnyckel: issupervised</span><span class="sxs-lookup"><span data-stu-id="d57f9-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="d57f9-181">Värdetyp: Sträng</span><span class="sxs-lookup"><span data-stu-id="d57f9-181">Value type: String</span></span>
    - <span data-ttu-id="d57f9-182">Konfigurationsvärde: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="d57f9-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-183">![Bild av Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="d57f9-184">Klicka **på Nästa** så att sidan **Omfattningstaggar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="d57f9-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="d57f9-185">Omfattningstaggar är valfria.</span><span class="sxs-lookup"><span data-stu-id="d57f9-185">Scope tags are optional.</span></span> <span data-ttu-id="d57f9-186">Klicka **på Nästa** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="d57f9-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="d57f9-187">På sidan **Uppgifter väljer** du de grupper som ska få den här profilen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="d57f9-188">I det här scenariot är det bäst att rikta alla **enheter mot mål.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="d57f9-189">Mer information om hur du tilldelar profiler finns i [Tilldela användar- och enhetsprofiler.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="d57f9-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="d57f9-190">När du distribuerar till användargrupper måste en användare logga in på en enhet innan principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d57f9-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="d57f9-191">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-191">Click **Next**.</span></span>

1. <span data-ttu-id="d57f9-192">På sidan **Granska + skapa** väljer du Skapa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="d57f9-193">Den nya profilen visas i listan över konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="d57f9-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="d57f9-194">För förbättrade funktioner mot nätfiske kan du därefter distribuera en anpassad profil på de övervakade iOS-enheterna.</span><span class="sxs-lookup"><span data-stu-id="d57f9-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="d57f9-195">Följ stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="d57f9-195">Follow the steps below:</span></span>
    - <span data-ttu-id="d57f9-196">Ladda ned konfigurationsprofilen från [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="d57f9-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="d57f9-197">Gå till  ->  **Konfigurationsprofiler för enheter iOS/iPadOS**  ->    ->  **Skapa profil**</span><span class="sxs-lookup"><span data-stu-id="d57f9-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d57f9-198">![Bild på Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="d57f9-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="d57f9-199">Ange ett namn på profilen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-199">Provide a name of the profile.</span></span> <span data-ttu-id="d57f9-200">När du uppmanas att importera en konfigurationsprofilfil väljer du den som hämtats ovan.</span><span class="sxs-lookup"><span data-stu-id="d57f9-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="d57f9-201">I avsnittet **Uppgift** väljer du den enhetsgrupp för vilken du vill använda den här profilen.</span><span class="sxs-lookup"><span data-stu-id="d57f9-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="d57f9-202">Det är en bra metod att detta ska tillämpas på alla hanterade iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="d57f9-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="d57f9-203">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d57f9-203">Click **Next**.</span></span>
    - <span data-ttu-id="d57f9-204">På sidan **Granska + skapa** väljer du Skapa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="d57f9-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="d57f9-205">Den nya profilen visas i listan över konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="d57f9-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d57f9-206">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d57f9-206">Next Steps</span></span>

[<span data-ttu-id="d57f9-207">Konfigurera Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="d57f9-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
