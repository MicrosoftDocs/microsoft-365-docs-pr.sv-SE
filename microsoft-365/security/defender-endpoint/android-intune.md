---
title: Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune
description: Här beskrivs hur du distribuerar Microsoft Defender för slutpunkt på Android med Microsoft Intune
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mde, android, installation, distribuera, avinstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1935533ad924b7589bdfee6f3119fb667fb60b73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841516"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="ef618-104">Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ef618-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef618-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ef618-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef618-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef618-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef618-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef618-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef618-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ef618-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ef618-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ef618-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="ef618-110">Lär dig hur du distribuerar Defender för slutpunkt på Android Intune-företagsportal enheter med registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="ef618-110">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="ef618-111">Mer information om registrering av Intune-enheter finns  [i Registrera din enhet](/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="ef618-111">For more information about Intune device enrollment, see  [Enroll your device](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="ef618-112">**Defender för slutpunkt på Android är nu tillgängligt på [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="ef618-112">**Defender for Endpoint on Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="ef618-113">Du kan ansluta till Google Play från Intune för att distribuera Defender för slutpunktsappen i alla registreringslägena för Enhetsadministratör och Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ef618-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="ef618-114">Uppdateringar av appen sker automatiskt via Google Play.</span><span class="sxs-lookup"><span data-stu-id="ef618-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="ef618-115">Distribuera på registrerade enheter med enhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="ef618-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="ef618-116">**Distribuera Defender för slutpunkt på Android Intune-företagsportal – registrerade enheter som enhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="ef618-116">**Deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="ef618-117">Lär dig hur du distribuerar Defender för slutpunkt på Android Intune-företagsportal enheter – registrerade enheter som enhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="ef618-117">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="ef618-118">Lägg till som Android Store-app</span><span class="sxs-lookup"><span data-stu-id="ef618-118">Add as Android store app</span></span>

1. <span data-ttu-id="ef618-119">Gå [Microsoft Endpoint Manager App Android-appar](https://go.microsoft.com/fwlink/?linkid=2109431) **Lägg** till \> **Android** \> **\> Store-app** i administrationscentret och välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="ef618-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Bild av Microsoft Endpoint Manager Lägg till android Store-program](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="ef618-121">På sidan **Lägg till app** och i avsnittet *Programinformation* anger du:</span><span class="sxs-lookup"><span data-stu-id="ef618-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="ef618-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="ef618-122">**Name**</span></span> 
   - <span data-ttu-id="ef618-123">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="ef618-123">**Description**</span></span>
   - <span data-ttu-id="ef618-124">**Publisher** som Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef618-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="ef618-125">**URL för app store** som https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender för slutpunktsapp google Play Store URL)</span><span class="sxs-lookup"><span data-stu-id="ef618-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="ef618-126">Andra fält är valfria.</span><span class="sxs-lookup"><span data-stu-id="ef618-126">Other fields are optional.</span></span> <span data-ttu-id="ef618-127">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ef618-127">Select **Next**.</span></span>

   ![Bild av Microsoft Endpoint Manager Lägg till appinformation i administrationscentret](images/mda-addappinfo.png)

3. <span data-ttu-id="ef618-129">Gå till *avsnittet* Obligatoriska i avsnittet Uppgifter **och** välj Lägg **till grupp.**</span><span class="sxs-lookup"><span data-stu-id="ef618-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="ef618-130">Du kan sedan välja den användargrupp(er) som du vill rikta Defender för Endpoint på Android-appen till.</span><span class="sxs-lookup"><span data-stu-id="ef618-130">You can then choose the user group(s) that you would like to target Defender for Endpoint on Android app.</span></span> <span data-ttu-id="ef618-131">Välj **Markera** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ef618-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ef618-132">Den valda användargruppen ska bestå av intune-registrerade användare.</span><span class="sxs-lookup"><span data-stu-id="ef618-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Bild av Microsoft Endpoint Manager valda användargrupperna i administrationscentret](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="ef618-134">I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ef618-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="ef618-135">Inom en liten stund kunde appen Defender för Slutpunkt skapas och ett meddelande visades i det övre högra hörnet på sidan.</span><span class="sxs-lookup"><span data-stu-id="ef618-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Bild av Microsoft Endpoint Manager Admin Center-meddelandet om Defender-slutpunktsappen](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="ef618-137">På sidan med appinformation som  visas i avsnittet Övervaka väljer du Enhetsinstallationsstatus **för** att verifiera att enhetsinstallationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="ef618-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-138">![Bild av Microsoft Endpoint Manager Admin Center-enhet](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="ef618-139">Fullständig registrering och kontrollstatus</span><span class="sxs-lookup"><span data-stu-id="ef618-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="ef618-140">När Defender för slutpunkt på Android har installerats på enheten visas appikonen.</span><span class="sxs-lookup"><span data-stu-id="ef618-140">Once Defender for Endpoint on Android has been installed on the device, you'll see the app icon.</span></span>

    ![Ikon på mobil enhet](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="ef618-142">Tryck på appikonen Microsoft Defender för Slutpunkt och följ anvisningarna på skärmen för att slutföra introduktionen av appen.</span><span class="sxs-lookup"><span data-stu-id="ef618-142">Tap the Microsoft Defender for Endpoint app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="ef618-143">Informationen innefattar godkännande av Android-behörigheter som krävs av Defender för Endpoint på Android.</span><span class="sxs-lookup"><span data-stu-id="ef618-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint on Android.</span></span>

3. <span data-ttu-id="ef618-144">Vid lyckad registrering börjar enheten visas i listan Enheter i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ef618-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Bild på enhet i Defender för Slutpunktsportalen](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="ef618-146">Distribuera på registrerade enheter för Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="ef618-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="ef618-147">Defender för slutpunkt på Android stöder registrerade enheter för Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ef618-147">Defender for Endpoint on Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="ef618-148">Mer information om de registreringsalternativ som stöds av Intune finns i [Alternativ för registrering.](/mem/intune/enrollment/android-enroll)</span><span class="sxs-lookup"><span data-stu-id="ef618-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="ef618-149">**För närvarande stöds personligt ägda enheter med arbetsprofil och fullständigt hanterad användarenhetsregistrering i företagsägd distribution.**</span><span class="sxs-lookup"><span data-stu-id="ef618-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="ef618-150">Lägga till Microsoft Defender för slutpunkt på Android som en hanterad Google Play-app</span><span class="sxs-lookup"><span data-stu-id="ef618-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="ef618-151">Följ stegen nedan för att lägga till appen Microsoft Defender för slutpunkt i ditt hanterade Google Play.</span><span class="sxs-lookup"><span data-stu-id="ef618-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="ef618-152">I [Microsoft Endpoint Manager appcenter går](https://go.microsoft.com/fwlink/?linkid=2109431) du till **Appar** \> **Android-appar Lägg** \> **till** och väljer **Hanterad Google Play-app.**</span><span class="sxs-lookup"><span data-stu-id="ef618-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-153">![Bild på Microsoft Endpoint Manager administrationscenter hanterat google play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="ef618-154">På den hanterade Google Play-sidan som läses in därefter går du till sökrutan och letar upp **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="ef618-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="ef618-155">Din sökning ska visa appen Microsoft Defender för slutpunkt i ditt hanterade Google Play.</span><span class="sxs-lookup"><span data-stu-id="ef618-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="ef618-156">Klicka på microsoft Defender för slutpunktsappen i sökresultatet för appar.</span><span class="sxs-lookup"><span data-stu-id="ef618-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Bild av Microsoft Endpoint Manager appsökning i administrationscentret](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="ef618-158">På sidan Appbeskrivning som kommer härnäst bör du kunna se appinformationen på Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="ef618-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="ef618-159">Granska informationen på sidan och välj sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="ef618-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-160">![En skärmbild av ett Hanterat Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="ef618-161">Du får de behörigheter som Defender för Endpoint får för att det ska fungera.</span><span class="sxs-lookup"><span data-stu-id="ef618-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="ef618-162">Granska dem och välj sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="ef618-162">Review them and then select **Approve**.</span></span>

    ![En skärmbild av Defender för godkännande av slutpunktsförhandsgranskningsappen](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="ef618-164">Då visas sidan Inställningar för godkännande.</span><span class="sxs-lookup"><span data-stu-id="ef618-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="ef618-165">Sidan bekräftar din inställning för att hantera nya appbehörigheter som Defender för Slutpunkt på Android kan fråga.</span><span class="sxs-lookup"><span data-stu-id="ef618-165">The page confirms your preference to handle new app permissions that Defender for Endpoint on Android might ask.</span></span> <span data-ttu-id="ef618-166">Granska alternativen och välj det alternativ du vill använda.</span><span class="sxs-lookup"><span data-stu-id="ef618-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="ef618-167">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="ef618-167">Select **Done**.</span></span>

    <span data-ttu-id="ef618-168">Som standard markeras Behåll godkänd som hanterad Google Play *när appen begär nya behörigheter*</span><span class="sxs-lookup"><span data-stu-id="ef618-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-169">![Bild på fliken Meddelanden](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="ef618-170">När du har valt behörighetshantering väljer du Synkronisera **för att** synkronisera Microsoft Defender för Endpoint till din applista.</span><span class="sxs-lookup"><span data-stu-id="ef618-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-171">![Bild på synkroniseringssidan](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="ef618-172">Synkroniseringen slutförs om några minuter.</span><span class="sxs-lookup"><span data-stu-id="ef618-172">The sync will complete in a few minutes.</span></span>

    ![Bild på Android-appen](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="ef618-174">Välj knappen **Uppdatera** på skärmen Android-appar så ska Microsoft Defender för Slutpunkt visas i applistan.</span><span class="sxs-lookup"><span data-stu-id="ef618-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender for Endpoint should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-175">![Bild på listan med Android-appar](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="ef618-176">Defender för Endpoint har stöd för appkonfigurationsprinciper för hanterade enheter via Intune.</span><span class="sxs-lookup"><span data-stu-id="ef618-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="ef618-177">Den här funktionen kan användas för att automatiskt skapa tillämpliga Android-behörigheter, så slutanvändaren behöver inte acceptera dessa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="ef618-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="ef618-178">På sidan **Appar går** du till **Principprinciper > principer för programkonfiguration > Lägg till > hanterade enheter.**</span><span class="sxs-lookup"><span data-stu-id="ef618-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Bild på android Microsoft Endpoint Manager hanterade enheter i administrationscentret för Android](images/android-mem.png)

    1. <span data-ttu-id="ef618-180">På sidan **Skapa appkonfigurationsprincip** anger du följande information:</span><span class="sxs-lookup"><span data-stu-id="ef618-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="ef618-181">Namn: Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="ef618-181">Name: Microsoft Defender for Endpoint.</span></span>
        - <span data-ttu-id="ef618-182">Välj **Android Enterprise** som plattform.</span><span class="sxs-lookup"><span data-stu-id="ef618-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="ef618-183">Välj **Endast Arbetsprofil** som Profiltyp.</span><span class="sxs-lookup"><span data-stu-id="ef618-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="ef618-184">Klicka **på Välj app**, **Microsoft Defender ATP**, välj **OK** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ef618-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ef618-185">![Bild av sidan skapa programkonfigurationsprincip](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="ef618-186">På sidan **Inställningar** till avsnittet Behörigheter klickar du på Lägg till för att visa listan med behörigheter som stöds.</span><span class="sxs-lookup"><span data-stu-id="ef618-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="ef618-187">Välj följande behörigheter i avsnittet Lägg till behörigheter:</span><span class="sxs-lookup"><span data-stu-id="ef618-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="ef618-188">Extern lagring (läsa)</span><span class="sxs-lookup"><span data-stu-id="ef618-188">External storage (read)</span></span>
       - <span data-ttu-id="ef618-189">Extern lagring (skrivning)</span><span class="sxs-lookup"><span data-stu-id="ef618-189">External storage (write)</span></span>

       <span data-ttu-id="ef618-190">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef618-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ef618-191">![Bild av konfigurationsprincipen för skapa app i Android](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="ef618-192">Nu bör du se både de behörigheter som visas och nu kan  du automatiskt tilldela båda genom att välja autogrant i listrutan Behörighetstillstånd och sedan **välja Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ef618-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ef618-193">![Bild av konfigurationsprincip för skapa app för automatisk grant av android](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="ef618-194">På sidan Assignments väljer du den användargrupp som den här appkonfigurationsprincipen ska **tilldelas** till.</span><span class="sxs-lookup"><span data-stu-id="ef618-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="ef618-195">Klicka **på Markera grupper som ska** inkluderas och markera tillämplig grupp och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ef618-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="ef618-196">Gruppen som väljs här är vanligtvis samma grupp som du tilldelar Microsoft Defender för endpoint Android-appen.</span><span class="sxs-lookup"><span data-stu-id="ef618-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ef618-197">![Bild av konfigurationsprincipen för att skapa program](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="ef618-198">På sidan **Granska + Skapa** som kommer upp härnäst granskar du all information och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ef618-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="ef618-199">Appkonfigurationsprincipen för Defender för slutpunkt som automatiskt tilldelas lagringsbehörigheten tilldelas nu till den valda användargruppen.</span><span class="sxs-lookup"><span data-stu-id="ef618-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="ef618-200">![Bild på android-granskning, konfigurationspolicy för att skapa app](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="ef618-201">Välj **Microsoft Defender ATP** i listan \> **Egenskaper** \> **uppgifter** \> **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="ef618-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Bild på lista över appar](images/mda-properties.png)


11. <span data-ttu-id="ef618-203">Tilldela appen som en *obligatorisk* app till en användargrupp.</span><span class="sxs-lookup"><span data-stu-id="ef618-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="ef618-204">Det installeras automatiskt i *arbetsprofilen* vid nästa synkronisering av enheten via Företagsportal appen.</span><span class="sxs-lookup"><span data-stu-id="ef618-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="ef618-205">Uppgiften kan göras genom att gå till avsnittet Lägg till *grupp* \> **som krävs,** markera användargruppen och klicka på **Välj.**</span><span class="sxs-lookup"><span data-stu-id="ef618-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-206">![Bild på sidan Redigera program](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="ef618-207">På sidan **Redigera** program granskar du all information som angetts ovan.</span><span class="sxs-lookup"><span data-stu-id="ef618-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="ef618-208">Välj sedan **Granska + Spara och** sedan Spara igen **för** att påbörja uppgiften.</span><span class="sxs-lookup"><span data-stu-id="ef618-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="ef618-209">Automatisk konfiguration av alltid på VPN</span><span class="sxs-lookup"><span data-stu-id="ef618-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="ef618-210">Defender för Endpoint har stöd för principer för enhetskonfiguration för hanterade enheter via Intune.</span><span class="sxs-lookup"><span data-stu-id="ef618-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="ef618-211">Den här funktionen kan användas för automatisk konfiguration av alltid på VPN på registrerade enheter för Android Enterprise, så slutanvändaren behöver inte konfigurera **VPN-tjänsten** under registrering.</span><span class="sxs-lookup"><span data-stu-id="ef618-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="ef618-212">På **enheter** väljer du **Konfigurationsprofiler**  >  **Skapa**  >  **profilplattform**  >  **Android Enterprise–** **Välj enhetsbegränsningar** under något av följande, beroende på vilken typ av enhetsregistrering du har</span><span class="sxs-lookup"><span data-stu-id="ef618-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="ef618-213">**Fullständigt hanterad, dedikerad och Corporate-Owned arbetsprofil**</span><span class="sxs-lookup"><span data-stu-id="ef618-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="ef618-214">**Personligt ägd arbetsprofil**</span><span class="sxs-lookup"><span data-stu-id="ef618-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="ef618-215">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ef618-215">Select **Create**.</span></span>
 
   > ![Bild på konfigurationsprofil för enheter Skapa](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="ef618-217">**Konfigurationsinställningar Inställningar** Ange ett **namn** och en **beskrivning** för att unikt identifiera konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="ef618-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Bild på enheter, konfigurationsprofilens namn och beskrivning](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="ef618-219">Välj **Anslutningar** och konfigurera VPN:</span><span class="sxs-lookup"><span data-stu-id="ef618-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="ef618-220">Aktivera **att alltid på VPN** konfigurera en VPN-klient i arbetsprofilen så att den automatiskt ansluter och återansluter till VPN när det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="ef618-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="ef618-221">Endast en VPN-klient kan konfigureras för alltid-på VPN på en viss enhet, så se till att inte ha fler än en alltid-på VPN-policy distribuerad till en enda enhet.</span><span class="sxs-lookup"><span data-stu-id="ef618-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="ef618-222">Välj **Custom** i VPN-klientlistrutan Custom VPN i det här fallet Defender för Endpoint VPN som används för att tillhandahålla Web Protection-funktionen.</span><span class="sxs-lookup"><span data-stu-id="ef618-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="ef618-223">Appen Microsoft Defender för slutpunkt måste installeras på användarens enhet för att den ska fungera automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ef618-223">Microsoft Defender for Endpoint app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="ef618-224">Ange **paket-ID** för Microsoft Defender för slutpunktsappen i Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="ef618-224">Enter **Package ID** of the Microsoft Defender for Endpoint app in Google Play store.</span></span> <span data-ttu-id="ef618-225">För Defender-appens URL https://play.google.com/store/apps/details?id=com.microsoft.scmx är Paket-ID **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="ef618-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="ef618-226">**Nedlåst listläge** Inte konfigurerad (standard)</span><span class="sxs-lookup"><span data-stu-id="ef618-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Bild på konfigurationsprofil för enheter aktiverar Alltid VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="ef618-228">**Uppgift** På sidan  **Assignments**   väljer du den användargrupp som den här appkonfigurationsprincipen ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="ef618-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="ef618-229">Klicka **på Markera grupper** som ska ingå och markera tillämplig grupp och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ef618-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="ef618-230">Gruppen som väljs här är vanligtvis samma grupp som du tilldelar Microsoft Defender för endpoint Android-appen.</span><span class="sxs-lookup"><span data-stu-id="ef618-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Bild på konfigurationsprofil för enheter Tilldelning](images/4autosetupofvpn.png)

5. <span data-ttu-id="ef618-232">På sidan **Granska + Skapa** som kommer upp härnäst granskar du all information och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ef618-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="ef618-233">Profil för enhetskonfiguration har nu tilldelats den valda användargruppen.</span><span class="sxs-lookup"><span data-stu-id="ef618-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Bild på konfigurationsprofil för enheter – Granska och skapa](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="ef618-235">Fullständig registrering och kontrollstatus</span><span class="sxs-lookup"><span data-stu-id="ef618-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="ef618-236">Bekräfta installationsstatusen för Microsoft Defender för slutpunkt på Android genom att klicka på **Enhetsinstallationsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ef618-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="ef618-237">Kontrollera att enheten visas här.</span><span class="sxs-lookup"><span data-stu-id="ef618-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ef618-238">![Bild på enhetsinstallationsstatus](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="ef618-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="ef618-239">På enheten kan du verifiera onboarding-status genom att gå till **arbetsprofilen**.</span><span class="sxs-lookup"><span data-stu-id="ef618-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="ef618-240">Kontrollera att Defender för slutpunkt är tillgängligt och att du är registrerad för personligt **ägda enheter med arbetsprofilen**.</span><span class="sxs-lookup"><span data-stu-id="ef618-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="ef618-241">Om du är registrerad på en enhet som ägs av en företagsägd, fullständigt hanterad användare har du en enda profil på enheten där du kan bekräfta att Defender för Slutpunkt är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ef618-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Bild av app på en mobil enhet](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="ef618-243">När appen är installerad öppnar du appen och godkänner behörigheterna. Därefter lyckades din registrering.</span><span class="sxs-lookup"><span data-stu-id="ef618-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Bild på mobil enhet med Microsoft Defender för Endpoint-appen](images/mda-devicesafe.png)

4. <span data-ttu-id="ef618-245">I det här läget har enheten introducerats till Defender för slutpunkt på Android.</span><span class="sxs-lookup"><span data-stu-id="ef618-245">At this stage the device is successfully onboarded onto Defender for Endpoint on Android.</span></span> <span data-ttu-id="ef618-246">Du kan kontrollera detta på [Microsoft Defender Säkerhetscenter](https://securitycenter.microsoft.com) genom att gå till **sidan** Enheter.</span><span class="sxs-lookup"><span data-stu-id="ef618-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Bild av Microsoft Defender för Slutpunktsportalen](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="ef618-248">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ef618-248">Related topics</span></span>
- [<span data-ttu-id="ef618-249">Översikt över Microsoft Defender för Endpoint för Android</span><span class="sxs-lookup"><span data-stu-id="ef618-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="ef618-250">Konfigurera Microsoft Defender för Endpoint för Android-funktioner</span><span class="sxs-lookup"><span data-stu-id="ef618-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
