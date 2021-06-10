---
title: Introduktion med hjälp av Microsoft Endpoint Configuration Manager
description: Lär dig hur du onboardar till Microsoft Defender för Endpoint med Microsoft Endpoint Configuration Manager
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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843512"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f9fc6-104">Introduktion med hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f9fc6-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9fc6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9fc6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f9fc6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f9fc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9fc6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f9fc6-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f9fc6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f9fc6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f9fc6-110">Den här artikeln är en del av distributionsguiden och fungerar som ett exempel på onboarding-metod.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="f9fc6-111">I ämnet [Planering](deployment-strategy.md) finns det flera metoder för att introducera enheter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="f9fc6-112">Det här avsnittet behandlar arkitekturen för samtidig hantering.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="f9fc6-113">![Bild av molnbaserad arkitektur ](images/co-management-architecture.png)
 *Diagram över miljöarkitekturer*</span><span class="sxs-lookup"><span data-stu-id="f9fc6-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="f9fc6-114">Defender för Endpoint har stöd för registrering av olika slutpunkter och verktyg, men den här artikeln täcker inte in dem.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="f9fc6-115">Mer information om allmän onboarding med andra distributionsverktyg och metoder som stöds finns i [Översikt över onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="f9fc6-116">Det här avsnittet leder användarna i:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-116">This topic guides users in:</span></span>
- <span data-ttu-id="f9fc6-117">Steg 1: Windows enheter till tjänsten</span><span class="sxs-lookup"><span data-stu-id="f9fc6-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="f9fc6-118">Steg 2: Konfigurera Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="f9fc6-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="f9fc6-119">Den här introduktionsvägledningen går igenom följande grundläggande steg som du måste vidta när du använder Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="f9fc6-120">**Skapa en samling i Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="f9fc6-121">**Konfigurera Microsoft Defender för slutpunktsfunktioner med Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="f9fc6-122">Endast Windows enheter omfattas av den här exempeldistributionen.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f9fc6-123">Steg 1: Onboard Windows enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f9fc6-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="f9fc6-124">Skapa samling</span><span class="sxs-lookup"><span data-stu-id="f9fc6-124">Collection creation</span></span>
<span data-ttu-id="f9fc6-125">Om du Windows 10 registrera Microsoft Endpoint Configuration Manager-enheter med hjälp av Microsoft Endpoint Configuration Manager kan distributionen ha en befintlig samling som mål, eller så kan en ny samling skapas för testning.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="f9fc6-126">Registrering med verktyg som grupprincip eller manuell metod installerar inte någon agent i systemet.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="f9fc6-127">I Microsoft Endpoint Configuration Manager konsolen konfigureras onboarding-processen som en del av inställningarna för efterlevnad i konsolen.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="f9fc6-128">Alla system som får den här nödvändiga konfigurationen behåller den konfigurationen så länge Konfigurationshanteraren-klienten fortsätter att ta emot den här principen från hanteringspunkten.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="f9fc6-129">Följ stegen nedan för att registrera slutpunkter med hjälp Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="f9fc6-130">I Microsoft Endpoint Configuration Manager navigera till Enhetssamlingar **för tillgångar och \> \> efterlevnadsöversikt.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Bild på Microsoft Endpoint Configuration Manager 1](images/configmgr-device-collections.png)

2. <span data-ttu-id="f9fc6-132">Högerklicka på **Enhetssamling** och välj **Skapa enhetssamling**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager 2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="f9fc6-134">Ange ett **namn** och **en begränsad samling** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager 3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="f9fc6-136">Välj **Lägg till regel** och välj **Frågeregel.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Bild av Microsoft Endpoint Configuration Manager guiden4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="f9fc6-138">Klicka **på** Nästa i **guiden Direktmedlemskap och** klicka på Redigera **frågeutdrag.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Bild på Microsoft Endpoint Configuration Manager 5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="f9fc6-140">Välj **Villkor** och välj sedan stjärnikonen.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Bild på Microsoft Endpoint Configuration Manager 6](images/configmgr-criteria.png)

7. <span data-ttu-id="f9fc6-142">Se till att villkorstypen är ett enkelt värde  , välj var som operativsystem **–** versionsnummer , operator som är större än eller lika med och **värde 14393** och klicka på **OK.** </span><span class="sxs-lookup"><span data-stu-id="f9fc6-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager 7](images/configmgr-simple-value.png)

8. <span data-ttu-id="f9fc6-144">Välj **Nästa** och **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-144">Select **Next** and **Close**.</span></span>

    ![Bild av Microsoft Endpoint Configuration Manager guiden8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="f9fc6-146">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-146">Select **Next**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager guiden9](images/configmgr-confirm.png)


<span data-ttu-id="f9fc6-148">När du har slutfört den här uppgiften har du en enhetssamling med Windows 10 alla slutpunkter i miljön.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="f9fc6-149">Steg 2: Konfigurera Microsoft Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="f9fc6-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="f9fc6-150">I det här avsnittet får du hjälp med att konfigurera följande funktioner Microsoft Endpoint Configuration Manager på Windows enheter:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="f9fc6-151">**Identifiering och svar för slutpunkt**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="f9fc6-152">**Nästa generations skydd**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="f9fc6-153">**Minskning av attackytan**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="f9fc6-154">Identifiering och svar av slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f9fc6-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="f9fc6-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f9fc6-155">Windows 10</span></span>
<span data-ttu-id="f9fc6-156">I Microsoft Defender Säkerhetscenter kan du ladda ned onboarding-principen som kan användas för att skapa principen i System Center Configuration Manager och distribuera den till Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="f9fc6-157">På en Microsoft Defender Säkerhetscenter portal väljer [du Inställningar och sedan Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span><span class="sxs-lookup"><span data-stu-id="f9fc6-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="f9fc6-158">Under Distributionsmetod väljer du den version **av** Microsoft Endpoint Configuration Manager .</span><span class="sxs-lookup"><span data-stu-id="f9fc6-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="f9fc6-160">Välj **Ladda ned paket**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-160">Select **Download package**.</span></span>

    ![Bild av introduktionsguiden för Microsoft Defender för slutpunkt11](images/mdatp-download-package.png)

4. <span data-ttu-id="f9fc6-162">Spara paketet på en tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="f9fc6-163">I Microsoft Endpoint Configuration Manager du till: **Tillgångar och efterlevnad > Översikt > Endpoint Protection > Microsoft Defender ATP Principer.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="f9fc6-164">Högerklicka på Microsoft Defender ATP **och** välj **Skapa Microsoft Defender ATP princip**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager 12](images/configmgr-create-policy.png)

7. <span data-ttu-id="f9fc6-166">Ange namn och beskrivning, kontrollera **att Onboarding** är markerat och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager 13](images/configmgr-policy-name.png)


8. <span data-ttu-id="f9fc6-168">Klicka **på Bläddra**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-168">Click **Browse**.</span></span>

9. <span data-ttu-id="f9fc6-169">Navigera till platsen för den nedladdade filen från steg 4 ovan.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="f9fc6-170">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-170">Click **Next**.</span></span>
11. <span data-ttu-id="f9fc6-171">Konfigurera agenten med lämpliga exempel **(Ingen eller** **Alla filtyper).**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Bild av konfigurationsinställningar1](images/configmgr-config-settings.png)

12. <span data-ttu-id="f9fc6-173">Välj lämplig telemetri **(Normal eller** **Expedited)** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Bild på konfigurationsinställningar2](images/configmgr-telemetry.png)

14. <span data-ttu-id="f9fc6-175">Verifiera konfigurationen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-175">Verify the configuration, then click **Next**.</span></span>

     ![Bild på konfigurationsinställningar3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="f9fc6-177">Klicka **på** Stäng när guiden är klar.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="f9fc6-178">Högerklicka Microsoft Endpoint Configuration Manager Defender för slutpunktsprincip du just skapade i konsolen och välj **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Bild på konfigurationsinställningar4](images/configmgr-deploy.png)

17. <span data-ttu-id="f9fc6-180">På den högra panelen markerar du den tidigare skapade samlingen och klickar på **OK.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Bild på konfigurationsinställningar5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="f9fc6-182">Tidigare versioner av Windows (version Windows 7 och Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="f9fc6-183">Följ stegen nedan för att identifiera defender för slutpunktsarbetsyta och arbetsytenyckel, som krävs för registrering av tidigare versioner av Windows.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="f9fc6-184">På en Microsoft Defender Säkerhetscenter väljer du **Inställningar > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="f9fc6-185">Under Operativsystem väljer du **Windows 7 SP1 och 8.1.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="f9fc6-186">Kopiera **arbetsyte-ID** **och arbetsytenyckel** och spara dem.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="f9fc6-187">De kommer att användas senare i processen.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-187">They will be used later in the process.</span></span>

    ![Bild på onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="f9fc6-189">Installera Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="f9fc6-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="f9fc6-190">MMA stöds för närvarande (från och med januari 2019) på följande Windows operativsystem:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="f9fc6-191">Server-SKU:er: Windows Server 2008 SP1 eller nyare</span><span class="sxs-lookup"><span data-stu-id="f9fc6-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="f9fc6-192">Klient-SKU:er: Windows 7 SP1 och senare</span><span class="sxs-lookup"><span data-stu-id="f9fc6-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="f9fc6-193">MMA-agenten måste installeras på Windows enheter.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="f9fc6-194">För att kunna installera agenten måste vissa system ladda ned uppdateringen för kundupplevelse och diagnostisk [telemetri](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) för att kunna samla in data med MMA.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="f9fc6-195">Dessa systemversioner omfattar men kan inte begränsas till:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="f9fc6-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f9fc6-196">Windows 8.1</span></span>

    -   <span data-ttu-id="f9fc6-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f9fc6-197">Windows 7</span></span>

    -   <span data-ttu-id="f9fc6-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f9fc6-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="f9fc6-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f9fc6-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="f9fc6-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f9fc6-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="f9fc6-201">Mer specifikt Windows 7 SP1 måste följande korrigeringar installeras:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="f9fc6-202">Installera [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="f9fc6-203">Installera [antingen .NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) **eller** 
         [KB3154518.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="f9fc6-204">Installera inte båda på samma system.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="f9fc6-205">Om du använder en proxyserver för att ansluta till Internet kan du gå till avsnittet Konfigurera proxyinställningar.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="f9fc6-206">När den är klar bör du se onboarded endpoints i portalen inom en timme.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="f9fc6-207">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="f9fc6-207">Next generation protection</span></span> 
<span data-ttu-id="f9fc6-208">Microsoft Defender Antivirus är en inbyggd antimalwarelösning som ger nästa generations skydd för stationära datorer, bärbara datorer och servrar.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="f9fc6-209">I Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection \> \> antimalware-policyer** och väljer Skapa programprincip för **program mot skadlig programvara.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Bild på program mot skadlig programvara](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="f9fc6-211">Välj Schemalagda genomsökningar **,** Sökinställningar **,** Standardåtgärder **,** Realtidsskydd , **Undantagsinställningar,** Avancerat, Åsidosättningar av hot, **Molnskyddstjänst** och Säkerhetsintelligensuppdateringar och välj **OK.**   </span><span class="sxs-lookup"><span data-stu-id="f9fc6-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Bild av nästa generations skyddsfönster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="f9fc6-213">I vissa branscher eller vissa utvalda företagskunder kan ha specifika behov av hur Antivirus är konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="f9fc6-214">Snabbsökning kontra fullständig sökning och anpassad sökning</span><span class="sxs-lookup"><span data-stu-id="f9fc6-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="f9fc6-215">Mer information finns i Windows-säkerhet [konfigurationsramverket](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Bild av nästa generations skyddsfönster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Bild av nästa generations skyddsfönster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Bild av nästa generations skyddsfönster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Bild av nästa generations skyddsfönster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Bild av nästa generations skyddsfönster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Bild av nästa generations skyddsfönster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Bild av nästa generations skyddsfönster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Bild av nästa generations skyddsfönster9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="f9fc6-224">Högerklicka på den nyligen skapade programprincipen för program mot skadlig programvara och välj **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Bild av nästa generations skyddsfönster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="f9fc6-226">Rikta den nya program mot skadlig programvara till din Windows 10 och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Bild av nästa generations skyddsfönster11](images/configmgr-select-collection.png)

<span data-ttu-id="f9fc6-228">När du har slutfört den här uppgiften har du nu konfigurerat Windows Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="f9fc6-229">Minska attackytan</span><span class="sxs-lookup"><span data-stu-id="f9fc6-229">Attack surface reduction</span></span>
<span data-ttu-id="f9fc6-230">Minskning av attackytan hos Defender för Endpoint inkluderar funktionsuppsättningen som är tillgänglig under Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="f9fc6-231">ASR-regler (Attack Surface Reduction), kontrollerad mappåtkomst, nätverksskydd och sårbarhetsskydd.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="f9fc6-232">Alla dessa funktioner ger ett granskningsläge och ett blockläge.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="f9fc6-233">I granskningsläge påverkas inte slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="f9fc6-234">Allt som samlas in är ytterligare telemetri och gör den tillgänglig i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f9fc6-235">Syftet med en distribution är att stegvis flytta säkerhetskontroller till blockläge.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="f9fc6-236">Så här anger du ASR-regler i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="f9fc6-237">På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Bild på Microsoft Endpoint Configuration Manager konsol0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="f9fc6-239">Välj **Minska attackytan**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="f9fc6-240">Ange att regler **ska granskas** och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Bild på Microsoft Endpoint Configuration Manager konsol1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="f9fc6-242">Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager konsol2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="f9fc6-244">När principen har skapats klickar du på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-244">Once the policy is created click **Close**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Bild på Microsoft Endpoint Manager konsol1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="f9fc6-247">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Bild på Microsoft Endpoint Configuration Manager konsol4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="f9fc6-249">Rikta principen mot den nya Windows 10 och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Bild på Microsoft Endpoint Configuration Manager konsol5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="f9fc6-251">När du har slutfört den här uppgiften har du nu konfigurerat ASR-regler i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="f9fc6-252">Nedan följer ytterligare steg för att verifiera om ASR-regler tillämpas korrekt på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="f9fc6-253">(Det kan ta några minuter)</span><span class="sxs-lookup"><span data-stu-id="f9fc6-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="f9fc6-254">Från en webbläsare går du till <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="f9fc6-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="f9fc6-255">Välj **Konfigurationshantering** på menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="f9fc6-256">Klicka **på Gå till hantering av attackytor** i hanteringspanelen för attackytor.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Bild på hantering av attackytor](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="f9fc6-258">Klicka **på fliken** Konfiguration i rapporterna för minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="f9fc6-259">Den visar en översikt över asr-regler och status för ASR-regler på varje enhet.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![En skärmbild av rapporterna för minskning av attackytan1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="f9fc6-261">Klicka på varje enhet visar konfigurationsinformation för ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-261">Click each device shows configuration details of ASR rules.</span></span>

    ![En skärmbild av minskningsregler för attackytan2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="f9fc6-263">Mer [information finns i Optimera ASR-regeldistribution](/microsoft-365/security/defender-endpoint/configure-machines-asr)   och identifieringar.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="f9fc6-264">Ange nätverksskyddsregler i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="f9fc6-265">På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![En skärmbild System Center Konfigurationshanteraren1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="f9fc6-267">Välj **Nätverksskydd**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="f9fc6-268">Ange inställningen Granskning **och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![En skärmbild System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="f9fc6-270">Bekräfta den nya Exploit Guard-policyn genom att klicka **på Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![En skärmbild av Sårbarhet GUard-policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="f9fc6-272">Klicka på Stäng när principen har **skapats.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-272">Once the policy is created click on **Close**.</span></span>

    ![En skärmbild av Sårbarhet GUard-policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="f9fc6-274">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="f9fc6-276">Välj principen för den nya Windows 10 och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="f9fc6-278">När du har slutfört den här uppgiften har du nu konfigurerat nätverksskydd i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="f9fc6-279">Så här ställer du in regler för kontrollerad mappåtkomst i granskningsläge:</span><span class="sxs-lookup"><span data-stu-id="f9fc6-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="f9fc6-280">På Microsoft Endpoint Configuration Manager navigerar du till Översikt över tillgångar och **\> efterlevnad Endpoint Protection Windows Defender \> \> Sårbarhetsskydd** och **väljer Skapa sårbarhetspolicy.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="f9fc6-282">Välj **Reglerad mappåtkomst.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="f9fc6-283">Ange att konfigurationen ska **granskas och** klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="f9fc6-285">Bekräfta den nya Exploit Guard-policyn genom att klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="f9fc6-287">Klicka på Stäng när principen har **skapats.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-287">Once the policy is created click on **Close**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="f9fc6-289">Högerklicka på den nya principen och välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="f9fc6-291">Rikta principen mot den nya Windows 10 och klicka på **OK.**</span><span class="sxs-lookup"><span data-stu-id="f9fc6-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![En skärmbild av Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="f9fc6-293">Nu har du konfigurerat kontrollerad mappåtkomst i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="f9fc6-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="f9fc6-294">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="f9fc6-294">Related topic</span></span>
- [<span data-ttu-id="f9fc6-295">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f9fc6-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
