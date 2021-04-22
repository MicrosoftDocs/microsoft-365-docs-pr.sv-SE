---
title: Introduktion med hjälp av Microsoft Endpoint Configuration Manager
description: Lär dig hur du onboardar till Microsoft Defender för Endpoint med Hjälp av Konfigurationshanteraren för Microsoft Endpoint
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 84273ce3e060eb86ee246a5cc6a8cae3cba743b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934495"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="41853-104">Introduktion med hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="41853-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41853-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="41853-105">**Applies to:**</span></span>
- [<span data-ttu-id="41853-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="41853-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41853-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41853-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41853-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="41853-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41853-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="41853-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="41853-110">Den här artikeln är en del av distributionsguiden och fungerar som ett exempel på onboarding-metod.</span><span class="sxs-lookup"><span data-stu-id="41853-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="41853-111">I ämnet [Planering](deployment-strategy.md) finns det flera metoder för att introducera enheter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="41853-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="41853-112">Det här avsnittet behandlar arkitekturen för samtidig hantering.</span><span class="sxs-lookup"><span data-stu-id="41853-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="41853-113">![Bild av molnbaserad arkitektur ](images/co-management-architecture.png)
 *Diagram över miljöarkitekturer*</span><span class="sxs-lookup"><span data-stu-id="41853-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="41853-114">Defender för Endpoint har stöd för registrering av olika slutpunkter och verktyg, men den här artikeln täcker inte in dem.</span><span class="sxs-lookup"><span data-stu-id="41853-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="41853-115">Mer information om allmän onboarding med andra distributionsverktyg och metoder som stöds finns i [Översikt över onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="41853-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="41853-116">Det här avsnittet leder användarna i:</span><span class="sxs-lookup"><span data-stu-id="41853-116">This topic guides users in:</span></span>
- <span data-ttu-id="41853-117">Steg 1: Introduktion till Windows-enheter till tjänsten</span><span class="sxs-lookup"><span data-stu-id="41853-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="41853-118">Steg 2: Konfigurera Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="41853-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="41853-119">Den här introduktionsvägledningen går igenom följande grundläggande steg som du måste vidta när du använder Konfigurationshanteraren för Microsoft Endpoint:</span><span class="sxs-lookup"><span data-stu-id="41853-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="41853-120">**Skapa en samling i Konfigurationshanteraren för Microsoft Endpoint**</span><span class="sxs-lookup"><span data-stu-id="41853-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="41853-121">**Konfigurera Microsoft Defender för slutpunktsfunktioner med hjälp av Konfigurationshanteraren för Microsoft Endpoint**</span><span class="sxs-lookup"><span data-stu-id="41853-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="41853-122">Endast Windows-enheter omfattas av den här exempeldistributionen.</span><span class="sxs-lookup"><span data-stu-id="41853-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="41853-123">Steg 1: Introducera Windows-enheter med Hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="41853-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="41853-124">Skapa samling</span><span class="sxs-lookup"><span data-stu-id="41853-124">Collection creation</span></span>
<span data-ttu-id="41853-125">Om du vill registrera Windows 10-enheter med Microsoft Endpoint Configuration Manager kan distributionen leda till en befintlig samling eller så kan en ny samling skapas för testning.</span><span class="sxs-lookup"><span data-stu-id="41853-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="41853-126">Registrering med verktyg som grupprincip eller manuell metod installerar inte någon agent i systemet.</span><span class="sxs-lookup"><span data-stu-id="41853-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="41853-127">I konsolen för Konfigurationshanteraren för Microsoft Endpoint konfigureras onboarding-processen som en del av inställningarna för efterlevnad i konsolen.</span><span class="sxs-lookup"><span data-stu-id="41853-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="41853-128">Alla system som får den här nödvändiga konfigurationen behåller den konfigurationen så länge Konfigurationshanteraren-klienten fortsätter att ta emot den här principen från hanteringspunkten.</span><span class="sxs-lookup"><span data-stu-id="41853-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="41853-129">Följ stegen nedan för att registrera slutpunkter med Hjälp av Konfigurationshanteraren för Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="41853-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="41853-130">Gå till Enhetssamlingar för tillgångar och efterlevnadsöversikt i konsolen **Konfigurationshanteraren \> \> för** Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="41853-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint1](images/configmgr-device-collections.png)

2. <span data-ttu-id="41853-132">Högerklicka på **Enhetssamling** och välj **Skapa enhetssamling**.</span><span class="sxs-lookup"><span data-stu-id="41853-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="41853-134">Ange ett **namn** och **en begränsad samling** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="41853-136">Välj **Lägg till regel** och välj **Frågeregel.**</span><span class="sxs-lookup"><span data-stu-id="41853-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="41853-138">Klicka **på** Nästa i **guiden Direktmedlemskap och** klicka på Redigera **frågeutdrag.**</span><span class="sxs-lookup"><span data-stu-id="41853-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="41853-140">Välj **Villkor** och välj sedan stjärnikonen.</span><span class="sxs-lookup"><span data-stu-id="41853-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint6](images/configmgr-criteria.png)

7. <span data-ttu-id="41853-142">Se till att villkorstypen är ett enkelt värde  , välj var som operativsystem **–** versionsnummer , operator som är större än eller lika med och **värde 14393** och klicka på **OK.** </span><span class="sxs-lookup"><span data-stu-id="41853-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint7](images/configmgr-simple-value.png)

8. <span data-ttu-id="41853-144">Välj **Nästa** och **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="41853-144">Select **Next** and **Close**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="41853-146">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41853-146">Select **Next**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint9](images/configmgr-confirm.png)


<span data-ttu-id="41853-148">När du har slutfört den här uppgiften har du en enhetssamling med alla Windows 10-slutpunkter i miljön.</span><span class="sxs-lookup"><span data-stu-id="41853-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="41853-149">Steg 2: Konfigurera Microsoft Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="41853-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="41853-150">I det här avsnittet får du hjälp med att konfigurera följande funktioner med Konfigurationshanteraren för Microsoft Endpoint på Windows-enheter:</span><span class="sxs-lookup"><span data-stu-id="41853-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="41853-151">**Identifiering och svar för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="41853-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="41853-152">**Nästa generations skydd**</span><span class="sxs-lookup"><span data-stu-id="41853-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="41853-153">**Minskning av attackytan**</span><span class="sxs-lookup"><span data-stu-id="41853-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="41853-154">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="41853-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="41853-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="41853-155">Windows 10</span></span>
<span data-ttu-id="41853-156">I Microsoft Defender Säkerhetscenter kan du ladda ned onboarding-principen som kan användas för att skapa principen i System Center Configuration Manager och distribuera den principen på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="41853-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="41853-157">Från en Microsoft Defender Säkerhetscenter-portal väljer [du Inställningar och sedan Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span><span class="sxs-lookup"><span data-stu-id="41853-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="41853-158">Under Distributionsmetod väljer du den version av **Microsoft Endpoint Configuration Manager som stöds.**</span><span class="sxs-lookup"><span data-stu-id="41853-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="41853-160">Välj **Ladda ned paket**.</span><span class="sxs-lookup"><span data-stu-id="41853-160">Select **Download package**.</span></span>

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt11](images/mdatp-download-package.png)

4. <span data-ttu-id="41853-162">Spara paketet på en tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="41853-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="41853-163">I Microsoft Endpoint Configuration Manager går du till: Tillgångar och efterlevnad **> Översikt > Endpoint Protection > Microsoft Defender ATP-principer.**</span><span class="sxs-lookup"><span data-stu-id="41853-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="41853-164">Högerklicka på **Microsoft Defender ATP-principer** och välj **Skapa Microsoft Defender ATP-princip**.</span><span class="sxs-lookup"><span data-stu-id="41853-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint12](images/configmgr-create-policy.png)

7. <span data-ttu-id="41853-166">Ange namn och beskrivning, kontrollera **att Onboarding** är markerat och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41853-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Bild av guiden Konfigurationshanteraren för Microsoft Endpoint13](images/configmgr-policy-name.png)


8. <span data-ttu-id="41853-168">Klicka **på Bläddra**.</span><span class="sxs-lookup"><span data-stu-id="41853-168">Click **Browse**.</span></span>

9. <span data-ttu-id="41853-169">Navigera till platsen för den nedladdade filen från steg 4 ovan.</span><span class="sxs-lookup"><span data-stu-id="41853-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="41853-170">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41853-170">Click **Next**.</span></span>
11. <span data-ttu-id="41853-171">Konfigurera agenten med lämpliga exempel **(Ingen eller** **Alla filtyper).**</span><span class="sxs-lookup"><span data-stu-id="41853-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Bild av konfigurationsinställningar1](images/configmgr-config-settings.png)

12. <span data-ttu-id="41853-173">Välj lämplig telemetri **(Normal eller** **Expedited)** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Bild på konfigurationsinställningar2](images/configmgr-telemetry.png)

14. <span data-ttu-id="41853-175">Verifiera konfigurationen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-175">Verify the configuration, then click **Next**.</span></span>

     ![Bild på konfigurationsinställningar3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="41853-177">Klicka **på** Stäng när guiden är klar.</span><span class="sxs-lookup"><span data-stu-id="41853-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="41853-178">Högerklicka på Defender för slutpunktsprincipen som du just skapade i konsolen Konfigurationshanteraren för Microsoft Endpoint och välj **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="41853-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Bild på konfigurationsinställningar4](images/configmgr-deploy.png)

17. <span data-ttu-id="41853-180">På den högra panelen markerar du den tidigare skapade samlingen och klickar på **OK.**</span><span class="sxs-lookup"><span data-stu-id="41853-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Bild på konfigurationsinställningar5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="41853-182">Tidigare versioner av Windows-klienten (Windows 7 och Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="41853-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="41853-183">Följ stegen nedan för att identifiera defender för slutpunktsarbetsyta och arbetsytenyckel, som krävs för registrering av tidigare versioner av Windows.</span><span class="sxs-lookup"><span data-stu-id="41853-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="41853-184">Från en Microsoft Defender Säkerhetscenter-portal väljer **du Inställningar > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="41853-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="41853-185">Under Operativsystem väljer du **Windows 7 SP1 och 8.1.**</span><span class="sxs-lookup"><span data-stu-id="41853-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="41853-186">Kopiera **arbetsyte-ID** **och arbetsytenyckel** och spara dem.</span><span class="sxs-lookup"><span data-stu-id="41853-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="41853-187">De kommer att användas senare i processen.</span><span class="sxs-lookup"><span data-stu-id="41853-187">They will be used later in the process.</span></span>

    ![Bild på onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="41853-189">Installera Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="41853-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="41853-190">MMA stöds för närvarande (från och med januari 2019) på följande Windows-operativsystem:</span><span class="sxs-lookup"><span data-stu-id="41853-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="41853-191">Server-SKU:er: Windows Server 2008 SP1 eller nyare</span><span class="sxs-lookup"><span data-stu-id="41853-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="41853-192">Klient-SKU:er: Windows 7 SP1 och senare</span><span class="sxs-lookup"><span data-stu-id="41853-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="41853-193">MMA-agenten måste installeras på Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="41853-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="41853-194">För att kunna installera agenten måste vissa system ladda ned uppdateringen för kundupplevelse och diagnostisk [telemetri](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) för att kunna samla in data med MMA.</span><span class="sxs-lookup"><span data-stu-id="41853-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="41853-195">Dessa systemversioner omfattar men kan inte begränsas till:</span><span class="sxs-lookup"><span data-stu-id="41853-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="41853-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="41853-196">Windows 8.1</span></span>

    -   <span data-ttu-id="41853-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="41853-197">Windows 7</span></span>

    -   <span data-ttu-id="41853-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="41853-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="41853-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="41853-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="41853-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="41853-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="41853-201">Mer specifikt för Windows 7 SP1 måste följande korrigeringar vara installerade:</span><span class="sxs-lookup"><span data-stu-id="41853-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="41853-202">Installera [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="41853-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="41853-203">Installera [antingen .NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) **eller** 
         [KB3154518.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="41853-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="41853-204">Installera inte båda på samma system.</span><span class="sxs-lookup"><span data-stu-id="41853-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="41853-205">Om du använder en proxyserver för att ansluta till Internet kan du gå till avsnittet Konfigurera proxyinställningar.</span><span class="sxs-lookup"><span data-stu-id="41853-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="41853-206">När den är klar bör du se onboarded endpoints i portalen inom en timme.</span><span class="sxs-lookup"><span data-stu-id="41853-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="41853-207">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="41853-207">Next generation protection</span></span> 
<span data-ttu-id="41853-208">Microsoft Defender Antivirus är en inbyggd antimalwarelösning som ger nästa generations skydd för stationära datorer, bärbara datorer och servrar.</span><span class="sxs-lookup"><span data-stu-id="41853-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="41853-209">I konsolen Konfigurationshanteraren för Microsoft Endpoint navigerar du till Assets **and Compliance Overview Endpoint Protection \> \> \> Antimalware Policys** och **väljer Create Antimalware Policy**.</span><span class="sxs-lookup"><span data-stu-id="41853-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Bild på program mot skadlig programvara](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="41853-211">Välj Schemalagda genomsökningar **,** Sökinställningar **,** Standardåtgärder **,** Realtidsskydd , **Undantagsinställningar,** Avancerat, Åsidosättningar av hot, **Molnskyddstjänst** och Säkerhetsintelligensuppdateringar och välj **OK.**   </span><span class="sxs-lookup"><span data-stu-id="41853-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Bild av nästa generations skyddsfönster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="41853-213">I vissa branscher eller vissa utvalda företagskunder kan ha specifika behov av hur Antivirus är konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="41853-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="41853-214">Snabbsökning kontra fullständig sökning och anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="41853-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="41853-215">Mer information finns i [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="41853-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Bild av nästa generations skyddsfönster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Bild av nästa generations skyddsfönster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Bild av nästa generations skyddsfönster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Bild av nästa generations skyddsfönster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Bild av nästa generations skyddsfönster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Bild av nästa generations skyddsfönster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Bild av nästa generations skyddsfönster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Bild av nästa generations skyddsfönster9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="41853-224">Högerklicka på den nyligen skapade programprincipen för program mot skadlig programvara och välj **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="41853-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Bild av nästa generations skyddsfönster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="41853-226">Rikta den nya principen mot skadlig programvara mot din Windows 10-samling och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="41853-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Bild av nästa generations skyddsfönster11](images/configmgr-select-collection.png)

<span data-ttu-id="41853-228">När du har slutfört den här uppgiften har du nu konfigurerat Windows Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="41853-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="41853-229">Minska attackytan</span><span class="sxs-lookup"><span data-stu-id="41853-229">Attack surface reduction</span></span>
<span data-ttu-id="41853-230">Minskning av attackytan hos Defender för Endpoint inkluderar funktionsuppsättningen som är tillgänglig under Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="41853-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="41853-231">ASR-regler (Attack Surface Reduction), kontrollerad mappåtkomst, nätverksskydd och sårbarhetsskydd.</span><span class="sxs-lookup"><span data-stu-id="41853-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="41853-232">Alla dessa funktioner ger ett granskningsläge och ett blockläge.</span><span class="sxs-lookup"><span data-stu-id="41853-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="41853-233">I granskningsläge påverkas inte slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="41853-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="41853-234">Allt som det gör är att samla in ytterligare telemetri och göra den tillgänglig i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="41853-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="41853-235">Syftet med en distribution är att stegvis flytta säkerhetskontroller till blockläge.</span><span class="sxs-lookup"><span data-stu-id="41853-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="41853-236">Så här anger du ASR-regler i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="41853-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="41853-237">Gå till Konsolen för Konfigurationshanteraren för Microsoft Endpoint, navigera till Tillgångar och Översikt över efterlevnadsslutpunktsskydd **\> Windows Defender Exploit \> \> Guard** och välj **Create Exploit Guard-policy.**</span><span class="sxs-lookup"><span data-stu-id="41853-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint 0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="41853-239">Välj **Minska attackytan**.</span><span class="sxs-lookup"><span data-stu-id="41853-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="41853-240">Ange att regler **ska granskas** och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="41853-242">Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="41853-244">När principen har skapats klickar du på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="41853-244">Once the policy is created click **Close**.</span></span>

    ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Bild av Konsol för Microsoft Endpoint Manager1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="41853-247">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="41853-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="41853-249">Rikta principen mot den nya Windows 10-samlingen och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="41853-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Bild på konsol för Konfigurationshanteraren för Microsoft Endpoint5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="41853-251">När du har slutfört den här uppgiften har du nu konfigurerat ASR-regler i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="41853-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="41853-252">Nedan följer ytterligare steg för att verifiera om ASR-regler tillämpas korrekt på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="41853-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="41853-253">(Det kan ta några minuter)</span><span class="sxs-lookup"><span data-stu-id="41853-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="41853-254">Från en webbläsare går du till <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="41853-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="41853-255">Välj **Konfigurationshantering** på menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="41853-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="41853-256">Klicka **på Gå till hantering av attackytor** i hanteringspanelen för attackytor.</span><span class="sxs-lookup"><span data-stu-id="41853-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Bild på hantering av attackytor](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="41853-258">Klicka **på fliken** Konfiguration i rapporterna för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="41853-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="41853-259">Den visar en översikt över asr-regler och status för ASR-regler på varje enhet.</span><span class="sxs-lookup"><span data-stu-id="41853-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![En skärmbild av rapporterna för minskning av attackytan1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="41853-261">Klicka på varje enhet visar konfigurationsinformation för ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="41853-261">Click each device shows configuration details of ASR rules.</span></span>

    ![En skärmbild av minskningsregler för attackytan2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="41853-263">Mer [information finns i Optimera ASR-regeldistribution](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   och identifieringar.</span><span class="sxs-lookup"><span data-stu-id="41853-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="41853-264">Ange nätverksskyddsregler i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="41853-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="41853-265">Gå till Konsolen för Konfigurationshanteraren för Microsoft Endpoint, navigera till Tillgångar och Översikt över efterlevnadsslutpunktsskydd **\> Windows Defender Exploit \> \> Guard** och välj **Create Exploit Guard-policy.**</span><span class="sxs-lookup"><span data-stu-id="41853-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![En skärmbild av System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="41853-267">Välj **Nätverksskydd**.</span><span class="sxs-lookup"><span data-stu-id="41853-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="41853-268">Ange inställningen Granskning **och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![En skärmbild av System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="41853-270">Bekräfta den nya Exploit Guard-policyn genom att klicka **på Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![En skärmbild av Sårbarhet GUard-policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="41853-272">Klicka på Stäng när principen har **skapats.**</span><span class="sxs-lookup"><span data-stu-id="41853-272">Once the policy is created click on **Close**.</span></span>

    ![En skärmbild av Sårbarhet GUard-policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="41853-274">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="41853-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="41853-276">Välj principen för den nya Windows 10-samlingen och välj **OK.**</span><span class="sxs-lookup"><span data-stu-id="41853-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="41853-278">När du har slutfört den här uppgiften har du nu konfigurerat nätverksskydd i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="41853-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="41853-279">Så här ställer du in regler för kontrollerad mappåtkomst i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="41853-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="41853-280">Gå till Konsolen för Konfigurationshanteraren för Microsoft Endpoint, navigera till Tillgångar och Översikt över efterlevnadsslutpunktsskydd **\> Windows Defender Exploit \> \> Guard** och välj **Create Exploit Guard-policy.**</span><span class="sxs-lookup"><span data-stu-id="41853-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="41853-282">Välj **Reglerad mappåtkomst.**</span><span class="sxs-lookup"><span data-stu-id="41853-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="41853-283">Ange att konfigurationen ska **granskas och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="41853-285">Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41853-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="41853-287">Klicka på Stäng när principen har **skapats.**</span><span class="sxs-lookup"><span data-stu-id="41853-287">Once the policy is created click on **Close**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="41853-289">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="41853-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="41853-291">Rikta principen mot den nya Windows 10-samlingen och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="41853-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="41853-293">Nu har du konfigurerat kontrollerad mappåtkomst i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="41853-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="41853-294">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="41853-294">Related topic</span></span>
- [<span data-ttu-id="41853-295">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="41853-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
