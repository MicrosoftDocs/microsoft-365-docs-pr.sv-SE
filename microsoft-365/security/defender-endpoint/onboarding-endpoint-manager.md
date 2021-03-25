---
title: Introduktion med Microsoft Endpoint Manager
description: Lär dig hur du onboardar till Microsoft Defender för Endpoint med Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
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
ms.openlocfilehash: 9edcceca2f6cc7c2377eb388d7394a23dfbae99d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186263"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="d2d4b-104">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2d4b-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2d4b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2d4b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2d4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2d4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2d4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="d2d4b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d2d4b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2d4b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d2d4b-110">Den här artikeln är en del av distributionsguiden och fungerar som ett exempel på onboarding-metod.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="d2d4b-111">I ämnet [Planering](deployment-strategy.md) finns det flera metoder för att introducera enheter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="d2d4b-112">Det här avsnittet beskriver den molnbaserade arkitekturen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="d2d4b-113">![Bild av molnbaserad arkitektur ](images/cloud-native-architecture.png)
 *Diagram över miljöarkitekturer*</span><span class="sxs-lookup"><span data-stu-id="d2d4b-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="d2d4b-114">Defender för Endpoint har stöd för registrering av olika slutpunkter och verktyg, men den här artikeln täcker inte in dem.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="d2d4b-115">Mer information om allmän onboarding med andra distributionsverktyg och metoder som stöds finns i [Översikt över onboarding.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="d2d4b-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) är en lösningsplattform som ger en enhetlig plattform för flera tjänster.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="d2d4b-117">Den innehåller [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) för molnbaserad enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="d2d4b-118">Det här avsnittet leder användarna i:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-118">This topic guides users in:</span></span>
- <span data-ttu-id="d2d4b-119">Steg 1: Onboarding-enheter till tjänsten genom att skapa en grupp i Microsoft Endpoint Manager (MEM) för att tilldela konfigurationer på</span><span class="sxs-lookup"><span data-stu-id="d2d4b-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="d2d4b-120">Steg 2: Konfigurera Defender för slutpunktsfunktioner med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2d4b-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="d2d4b-121">Den här introduktionsvägledningen går igenom följande grundläggande steg som du måste vidta när du använder Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="d2d4b-122">Identifiera målenheter eller -användare</span><span class="sxs-lookup"><span data-stu-id="d2d4b-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="d2d4b-123">Skapa en Azure Active Directory-grupp (användare eller enhet)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="d2d4b-124">Skapa en konfigurationsprofil</span><span class="sxs-lookup"><span data-stu-id="d2d4b-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="d2d4b-125">I Microsoft Endpoint Manager hjälper vi dig att skapa en separat princip för varje funktion.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="d2d4b-126">Resurser</span><span class="sxs-lookup"><span data-stu-id="d2d4b-126">Resources</span></span>


<span data-ttu-id="d2d4b-127">Här är de länkar du behöver för resten av processen:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="d2d4b-128">MEM-portal</span><span class="sxs-lookup"><span data-stu-id="d2d4b-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="d2d4b-129">Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="d2d4b-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="d2d4b-130">Intune-säkerhetsbaslinjer</span><span class="sxs-lookup"><span data-stu-id="d2d4b-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="d2d4b-131">Mer information om Microsoft Endpoint Manager finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="d2d4b-132">Microsoft Endpoint Manager-sida</span><span class="sxs-lookup"><span data-stu-id="d2d4b-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="d2d4b-133">Blogginlägg om intune och ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="d2d4b-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="d2d4b-134">Introduktionsvideo om MEM</span><span class="sxs-lookup"><span data-stu-id="d2d4b-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="d2d4b-135">Steg 1: Introducera enheter genom att skapa en grupp i MEM för att tilldela konfigurationer på</span><span class="sxs-lookup"><span data-stu-id="d2d4b-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="d2d4b-136">Identifiera målenheter eller -användare</span><span class="sxs-lookup"><span data-stu-id="d2d4b-136">Identify target devices or users</span></span>
<span data-ttu-id="d2d4b-137">I det här avsnittet skapar vi en testgrupp där du kan tilldela dina konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="d2d4b-138">Intune använder Azure Active Directory-grupper (Azure AD) för att hantera enheter och användare.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="d2d4b-139">Som Intune-administratör kan du konfigurera grupper så att de passar organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="d2d4b-140">Mer information finns i Lägga [till grupper för att ordna användare och enheter.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="d2d4b-141">Skapa en grupp</span><span class="sxs-lookup"><span data-stu-id="d2d4b-141">Create a group</span></span>

1.  <span data-ttu-id="d2d4b-142">Öppna MEM-portalen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="d2d4b-143">Öppna **Grupper > Ny grupp.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-144">![Bild av Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="d2d4b-145">Ange information och skapa en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-146">![Bild av Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="d2d4b-147">Lägg till testanvändaren eller testenheten.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="d2d4b-148">I fönstret **Grupper > Alla grupper** öppnar du den nya gruppen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="d2d4b-149">Välj  **Medlemmar > Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="d2d4b-150">Leta reda på testanvändaren eller enheten och markera den.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-151">![Bild av Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="d2d4b-152">Testgruppen har nu en medlem att testa.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="d2d4b-153">Steg 2: Skapa konfigurationsprinciper för att konfigurera Microsoft Defender för Endpoint-funktioner</span><span class="sxs-lookup"><span data-stu-id="d2d4b-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="d2d4b-154">I följande avsnitt ska du skapa ett antal konfigurationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="d2d4b-155">Först finns en konfigurationsprincip för att välja vilka grupper av användare eller enheter som ska introduceras i Defender för Slutpunkt:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="d2d4b-156">Identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d2d4b-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="d2d4b-157">Sedan fortsätter du genom att skapa flera olika typer av slutpunktssäkerhetsprinciper:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="d2d4b-158">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="d2d4b-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="d2d4b-159">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="d2d4b-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="d2d4b-160">Identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d2d4b-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="d2d4b-161">Öppna MEM-portalen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="d2d4b-162">Gå till **Slutpunktssäkerhet > identifiering och svar av slutpunkt.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="d2d4b-163">Klicka på **Skapa profil.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-164">![Bild på Microsoft Endpoint Manager-portalen4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="d2d4b-165">Under **Plattform väljer du Windows 10 och senare, Profil – Identifiering av slutpunkt och svar > Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="d2d4b-166">Ange ett namn och en beskrivning och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-167">![Bild på Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="d2d4b-168">Välj inställningar efter behov och välj sedan  **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-169">![Bild av Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2d4b-170">I den här instansen har det här fyllts i automatiskt eftersom Defender för Slutpunkt redan har integrerats med Intune.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="d2d4b-171">Mer information om integrering finns i Aktivera [Microsoft Defender för slutpunkt i Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="d2d4b-172">Följande bild visar ett exempel på vad som visas när Microsoft Defender för Slutpunkt inte är integrerat med Intune:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Bild på Microsoft Endpoint Manager-portalen7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="d2d4b-174">Lägg till omfattningstaggar om det behövs och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-175">![Bild av Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="d2d4b-176">Lägg till testgrupp genom att **klicka på Välj grupper som ska ingå** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-177">![Bild av Microsoft Endpoint Manager-portalen9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="d2d4b-178">Granska och acceptera och välj sedan  **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-179">![Bild av Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="d2d4b-180">Du kan visa din slutförda princip.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-181">![Bild av Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="d2d4b-182">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="d2d4b-182">Next-generation protection</span></span>

1.  <span data-ttu-id="d2d4b-183">Öppna MEM-portalen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="d2d4b-184">Gå till **Slutpunktssäkerhet > Antivirus > Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-185">![Bild av Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="d2d4b-186">Välj **Plattform – Windows 10 och senare – Windows och Profil – Microsoft Defender Antivirus > Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="d2d4b-187">Ange namn och beskrivning och välj sedan  **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-188">![Bild av Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="d2d4b-189">På sidan **Konfigurationsinställningar:** Ange de konfigurationer du behöver för Microsoft Defender Antivirus (molnskydd, undantag, Real-Time skydd och åtgärd).</span><span class="sxs-lookup"><span data-stu-id="d2d4b-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-190">![Bild av Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="d2d4b-191">Lägg till omfattningstaggar om det behövs och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-192">![Bild av Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="d2d4b-193">Välj de grupper du vill inkludera, tilldela till testgruppen och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-194">![Bild av Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="d2d4b-195">Granska och skapa och välj sedan  **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-196">![Bild av Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="d2d4b-197">Konfigurationsprincipen som du har skapat visas.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-198">![Bild av Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="d2d4b-199">Minskning av attackytan – regler för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="d2d4b-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="d2d4b-200">Öppna MEM-portalen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="d2d4b-201">Gå till **Slutpunktssäkerhet > minska attackytan**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="d2d4b-202">Välj  **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="d2d4b-203">Välj **plattform – Windows 10 och senare – Profil – minskningsregler för attackytor > Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-204">![Bild av Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="d2d4b-205">Ange ett namn och en beskrivning och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-206">![Bild av Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="d2d4b-207">På sidan **Konfigurationsinställningar:** Ange de konfigurationer du behöver för att minska attackytan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2d4b-208">Vi kommer att konfigurera alla minskningsregler för attackytor till Granskning.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="d2d4b-209">Mer information finns i Regler [för att minska attackytan](attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="d2d4b-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-210">![Bild av Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="d2d4b-211">Lägg till omfattningstaggar efter behov och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-212">![Bild av Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="d2d4b-213">Välj de grupper du vill inkludera och tilldela till testgruppen och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-214">![Bild av Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="d2d4b-215">Granska informationen och välj sedan  **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-216">![Bild av Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="d2d4b-217">Visa principen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-218">![Bild av Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="d2d4b-219">Minskning av attackytan – webbskydd</span><span class="sxs-lookup"><span data-stu-id="d2d4b-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="d2d4b-220">Öppna MEM-portalen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="d2d4b-221">Gå till **Slutpunktssäkerhet > minska attackytan**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="d2d4b-222">Välj  **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="d2d4b-223">Välj **Windows 10 och senare – Webbskydd > Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-224">![Bild av Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="d2d4b-225">Ange ett namn och en beskrivning och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-226">![Bild av Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="d2d4b-227">På sidan **Konfigurationsinställningar:** Ange de konfigurationer som krävs för webbskydd och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2d4b-228">Vi konfigurerar webbskydd för blockering.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="d2d4b-229">Mer information finns i [Webbskydd](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d2d4b-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-230">![Bild av Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="d2d4b-231">Lägg **till omfattningstaggar efter behov > Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d2d4b-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-232">![Bild av Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="d2d4b-233">Välj **Tilldela för att testa > Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-234">![Bild av Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="d2d4b-235">Välj **Granska och skapa > skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-236">![Bild av Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="d2d4b-237">Visa principen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-238">![Bild av Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="d2d4b-239">Verifiera konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="d2d4b-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="d2d4b-240">Bekräfta att principer har tillämpats</span><span class="sxs-lookup"><span data-stu-id="d2d4b-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="d2d4b-241">När konfigurationsprincipen har tilldelats tar det lite tid att tillämpa den.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="d2d4b-242">Mer information om tidsinställningar finns [i Intune-konfigurationsinformation.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="d2d4b-243">Bekräfta att konfigurationsprincipen har använts på testenheten genom att följa följande process för varje konfigurationsprincip.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="d2d4b-244">Öppna MEM-portalen och navigera till relevant princip som visas i stegen ovan.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="d2d4b-245">I följande exempel visas nästa generations skyddsinställningar.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-246">[![Bild av Microsoft Endpoint Manager portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="d2d4b-247">Välj **Konfigurationsprincip för** att visa principstatusen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-248">[![Bild av Microsoft Endpoint Manager portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="d2d4b-249">Välj  **Enhetsstatus** om du vill se statusen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-250">[![Bild av Microsoft Endpoint Manager portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="d2d4b-251">Välj  **Användarstatus** om du vill se statusen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-252">[![Bild av Microsoft Endpoint Manager portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="d2d4b-253">Välj  **Status per inställning för** att visa statusen.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="d2d4b-254">Den här vyn är mycket användbar om du vill identifiera inställningar som står i konflikt med en annan princip.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-255">[![Bild av Microsoft Endpoint Manager portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="d2d4b-256">Identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d2d4b-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="d2d4b-257">Innan du använder konfigurationen bör inte tjänsten Defender för Endpoint Protection startas.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-258">[![Bild på panelen Tjänster1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="d2d4b-259">När konfigurationen har tillämpats ska tjänsten Defender för Endpoint Protection startas.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-260">[![Bild på panelen Tjänster2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="d2d4b-261">När tjänsterna körs på enheten visas den i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-262">[![Bild på Microsoft Defender Säkerhetscenter ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="d2d4b-263">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="d2d4b-263">Next-generation protection</span></span>

1.  <span data-ttu-id="d2d4b-264">Innan du använder principen på en testenhet bör du kunna hantera inställningarna manuellt enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-265">![Bild på inställning sida1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="d2d4b-266">När principen har tillämpats bör du inte kunna hantera inställningarna manuellt.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2d4b-267">I följande bild **visas Aktivera moln levererat skydd** och Aktivera **realtidsskydd** som hanterat.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d2d4b-268">![Bild på inställning sida2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="d2d4b-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="d2d4b-269">Minskning av attackytan – regler för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="d2d4b-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="d2d4b-270">Innan du tillämpar principen på en testenhet, penna ett PowerShell-fönster och skriv `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="d2d4b-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="d2d4b-271">Det bör svara med följande rader utan innehåll:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="d2d4b-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="d2d4b-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="d2d4b-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Bild på kommandorad1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="d2d4b-276">När du har tillämpat principen på en testenhet öppnar du en PowerShell-windows och skriver `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="d2d4b-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="d2d4b-277">Det bör svara med följande rader med innehåll enligt nedan:</span><span class="sxs-lookup"><span data-stu-id="d2d4b-277">This should respond with the following lines with content as shown below:</span></span>

    ![Bild på kommandorad2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="d2d4b-279">Minskning av attackytan – webbskydd</span><span class="sxs-lookup"><span data-stu-id="d2d4b-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="d2d4b-280">Öppna ett PowerShell-fönster på testenheten och skriv `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="d2d4b-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="d2d4b-281">Det bör svara med en nolla enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-281">This should respond with a 0 as shown below.</span></span>

    ![Bild på kommandorad3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="d2d4b-283">När du har tillämpat principen öppnar du en PowerShell-windows och skriver `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="d2d4b-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="d2d4b-284">Detta bör svara med en 1:a (1) som visas nedan.</span><span class="sxs-lookup"><span data-stu-id="d2d4b-284">This should respond with a 1 as shown below.</span></span>

    ![Bild på kommandorad4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
