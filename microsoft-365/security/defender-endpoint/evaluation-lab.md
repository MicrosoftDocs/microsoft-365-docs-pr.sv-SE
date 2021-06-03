---
title: Microsoft Defender för utvärderingslabb med slutpunkt
description: Läs mer om Microsoft Defender för slutpunktsfunktioner, kör attackspel och se hur det förhindrar, identifierar och åtgärdar hot.
keywords: utvärdera Microsoft Defender för slutpunkt, utvärdering, lab, simulering, windows 10, windows server 2019, utvärderingslabb
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
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6ef1d3dbc111e5d10bf4d3c42dfd08e5e9d63e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730645"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="8ebc7-104">Microsoft Defender för utvärderingslabb med slutpunkt</span><span class="sxs-lookup"><span data-stu-id="8ebc7-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ebc7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ebc7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ebc7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8ebc7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ebc7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8ebc7-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8ebc7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ebc7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="8ebc7-110">Att genomföra en omfattande utvärdering av säkerhetsprodukter kan vara en komplex process som kräver krångliga miljöer och enhetskonfigurationer innan en helslutsattack simulering kan utföras.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="8ebc7-111">Till komplexiteten läggs utmaningen att spåra var simuleringsaktiviteter, varningar och resultat återspeglas under utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="8ebc7-112">Utvärderingslabb med Microsoft Defender för slutpunkter är utformat för att eliminera komplexiteten i konfigurationen av enheter och miljöer så att du kan fokusera på att utvärdera plattformens funktioner, köra simuleringar och se funktionerna för skydd, identifiering och åtgärder i praktiken.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="8ebc7-113">Med den förenklade uppsättningen kan du fokusera på att köra egna testscenarier och de färdiga simuleringarna och se hur Defender för Slutpunkt fungerar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="8ebc7-114">Du har full tillgång till plattformens kraftfulla funktioner, som automatiska undersökningar, avancerad sökning och hotanalys, så att du kan testa den omfattande skyddsstacken som Defender för Slutpunkt erbjuder.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="8ebc7-115">Du kan lägga till Windows 10 eller Windows Server 2019-enheter som är förkonfigurerade att ha de senaste OS-versionerna och rätt säkerhetskomponenter på plats samt Office 2019 Standard installerat.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="8ebc7-116">Du kan även installera hot.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-116">You can also install threat simulators.</span></span> <span data-ttu-id="8ebc7-117">Defender för Endpoint har samarbetat med branschledande simuleringsplattformar för hot som hjälper dig att testa Defender för Slutpunkt-funktioner utan att behöva lämna portalen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="8ebc7-118">Installera det du föredrar, kör scenarier i utvärderingslabbet och se direkt hur plattformen fungerar – allt finns tillgängligt utan extra kostnad för dig.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="8ebc7-119">Du får också praktisk tillgång till ett brett utbud av simuleringar som du kan komma åt och köra från simuleringskatalogen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="8ebc7-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="8ebc7-120">Before you begin</span></span>
<span data-ttu-id="8ebc7-121">Du måste uppfylla licenskraven eller ha [utvärderingsåtkomst till](minimum-requirements.md#licensing-requirements) Microsoft Defender för Endpoint för att komma åt utvärderingslabbet.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="8ebc7-122">Du måste ha **behörigheten Hantera säkerhetsinställningar** för att:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="8ebc7-123">Skapa labbet</span><span class="sxs-lookup"><span data-stu-id="8ebc7-123">Create the lab</span></span>
- <span data-ttu-id="8ebc7-124">Skapa enheter</span><span class="sxs-lookup"><span data-stu-id="8ebc7-124">Create devices</span></span>
- <span data-ttu-id="8ebc7-125">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="8ebc7-125">Reset password</span></span>
- <span data-ttu-id="8ebc7-126">Skapa simuleringar</span><span class="sxs-lookup"><span data-stu-id="8ebc7-126">Create simulations</span></span> 
 
<span data-ttu-id="8ebc7-127">Om du har aktiverat rollbaserad åtkomstkontroll (RBAC) och skapat minst en datorgrupp, måste användarna ha åtkomst till Alla datorgrupper.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="8ebc7-128">Mer information finns i Skapa [och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8ebc7-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="8ebc7-129">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8ebc7-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ebc7-130">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="8ebc7-131">Kom igång med labbet</span><span class="sxs-lookup"><span data-stu-id="8ebc7-131">Get started with the lab</span></span>
<span data-ttu-id="8ebc7-132">Du kan komma åt labbet från menyn.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-132">You can access the lab from the menu.</span></span> <span data-ttu-id="8ebc7-133">I navigeringsmenyn väljer du **Utvärdering och självstudier > Utvärderingslabb.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Bild på utvärderingslabb på menyn](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="8ebc7-135">Beroende på vilken typ av miljöstruktur du väljer blir enheter tillgängliga under det angivna antalet timmar från aktiveringsdagen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="8ebc7-136">Varje miljö etableras med ett begränsat antal testenheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="8ebc7-137">När du har använt de etablerade enheterna och tagit bort dem kan du begära fler enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="8ebc7-138">Du kan begära labbresurser en gång i månaden.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="8ebc7-139">Har du redan ett labb?</span><span class="sxs-lookup"><span data-stu-id="8ebc7-139">Already have a lab?</span></span> <span data-ttu-id="8ebc7-140">Se till att aktivera de nya hoten och ha aktiva enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="8ebc7-141">Konfigurera utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="8ebc7-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="8ebc7-142">Välj Utvärderings- och **självstudiekurser**  >  **Utvärderingslabb** i navigeringsfönstret och välj sedan **Installationslabb.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Bild på välkomstsidan för utvärderingslabb](images/evaluation-lab-setup.png)

2. <span data-ttu-id="8ebc7-144">Beroende på dina utvärderingsbehov kan du välja att konfigurera en miljö med färre enheter under en längre period eller fler enheter under kortare tid.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="8ebc7-145">Välj önskad labkonfiguration och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![Bild på konfigurationsalternativ för lab](images/lab-creation-page.png) 


3. <span data-ttu-id="8ebc7-147">(Valfritt) Du kan välja att installera hot i labbet.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Bild på agent för installation av installation](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="8ebc7-149">Först måste du godkänna och godkänna användningsvillkoren och informationsdelningssatserna.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="8ebc7-150">Välj den simulering av hot som du vill använda och ange din information.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="8ebc7-151">Du kan också välja att installera hot vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="8ebc7-152">Om du väljer att installera simuleringsagenter för hot under installationen av lab får du fördelen med att ha dem installerade på de enheter du lägger till.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Bild på sammanfattningssida](images/lab-setup-summary.png)

5.  <span data-ttu-id="8ebc7-154">Granska sammanfattningen och välj **Installationslabb**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="8ebc7-155">När labinstallationen är klar kan du lägga till enheter och köra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="8ebc7-156">Lägg till enheter</span><span class="sxs-lookup"><span data-stu-id="8ebc7-156">Add devices</span></span>
<span data-ttu-id="8ebc7-157">När du lägger till en enhet i din miljö konfigurerar Defender för Endpoint en välkonfigurerad enhet med anslutningsinformation.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="8ebc7-158">Du kan lägga Windows 10 eller Windows Server 2019-enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="8ebc7-159">Enheten konfigureras med den senaste versionen av operativsystemet och Office 2019 Standard samt andra appar som Java, Python och SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="8ebc7-160">Om du väljer att lägga till en hotbild under installationen av lab kommer alla enheter att ha hotagent installerad på de enheter som du lägger till.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="8ebc7-161">Enheten introduceras automatiskt i din klientorganisation med de rekommenderade Windows och i granskningsläge – utan ansträngning från din sida.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="8ebc7-162">Följande säkerhetskomponenter är förkonfigurerade i testenheterna:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-162">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="8ebc7-163">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="8ebc7-163">Attack surface reduction</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="8ebc7-164">Blockera vid första synen</span><span class="sxs-lookup"><span data-stu-id="8ebc7-164">Block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ebc7-165">Kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="8ebc7-165">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="8ebc7-166">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="8ebc7-166">Exploit protection</span></span>](enable-exploit-protection.md)
- [<span data-ttu-id="8ebc7-167">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="8ebc7-167">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="8ebc7-168">Potentiellt oönskad identifiering av program</span><span class="sxs-lookup"><span data-stu-id="8ebc7-168">Potentially unwanted application detection</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ebc7-169">Moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="8ebc7-169">Cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ebc7-170">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="8ebc7-170">Microsoft Defender SmartScreen</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="8ebc7-171">Microsoft Defender Antivirus kommer att vara aktiverat (inte i granskningsläge).</span><span class="sxs-lookup"><span data-stu-id="8ebc7-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="8ebc7-172">Om Microsoft Defender Antivirus hindrar dig från att köra din simulering kan du inaktivera realtidsskydd på enheten via Windows-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="8ebc7-173">Mer information finns i [Konfigurera alltid-på-skydd](configure-real-time-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc7-173">For more information, see [Configure always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="8ebc7-174">Inställningar för automatisk undersökning beror på klientorganisationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="8ebc7-175">Den konfigureras som standard semi-automatiserad.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="8ebc7-176">Mer information finns i [Översikt över automatiserade undersökningar.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="8ebc7-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="8ebc7-177">Anslutningen till testenheterna görs med RDP.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="8ebc7-178">Kontrollera att dina brandväggsinställningar tillåter RDP-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="8ebc7-179">Välj Lägg till enhet på **instrumentpanelen.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="8ebc7-180">Välj vilken typ av enhet du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-180">Choose the type of device to add.</span></span> <span data-ttu-id="8ebc7-181">Du kan välja att lägga till Windows 10 eller Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Bild på labkonfiguration med enhetsalternativ](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="8ebc7-183">Om något går fel med processen för att skapa enhet får du ett meddelande och du måste skicka en ny begäran.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="8ebc7-184">Om enheten skapas utan fel räknas den inte in i den totala tillåtna kvoten.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="8ebc7-185">Anslutningsinformationen visas.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-185">The connection details are displayed.</span></span> <span data-ttu-id="8ebc7-186">Välj **Kopiera** för att spara lösenordet för enheten.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8ebc7-187">Lösenordet visas bara en gång.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-187">The password is only displayed once.</span></span> <span data-ttu-id="8ebc7-188">Se till att spara den för senare användning.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-188">Be sure to save it for later use.</span></span>

    ![Bild på enhet som lagts till med anslutningsinformation](images/add-machine-eval-lab.png)

4. <span data-ttu-id="8ebc7-190">Enhetsuppsättningen startar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-190">Device set up begins.</span></span> <span data-ttu-id="8ebc7-191">Det kan ta upp till cirka 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="8ebc7-192">Se status för testenheter, risk- och exponeringsnivåer och status för installationerna genom att välja **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Bild på fliken Enheter](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="8ebc7-194">I kolumnen **Förnamnsstatus** kan du hovra över informationsikonen för att få information om installationsstatus för en agent.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="8ebc7-195">Begär för fler enheter</span><span class="sxs-lookup"><span data-stu-id="8ebc7-195">Request for more devices</span></span>
<span data-ttu-id="8ebc7-196">När alla befintliga enheter används och tas bort kan du begära ytterligare enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="8ebc7-197">Du kan begära labbresurser en gång i månaden.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="8ebc7-198">På instrumentpanelen för utvärderingslabb väljer **du Begär för fler enheter.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![Bild på begäran för fler enheter](images/request-more-devices.png)

2. <span data-ttu-id="8ebc7-200">Välj din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="8ebc7-201">Skicka begäran.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-201">Submit the request.</span></span> 

<span data-ttu-id="8ebc7-202">När begäran har skickats visas en grön bekräftelsebanderoll och datumet för den senaste inskickade överföringen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="8ebc7-203">Du hittar statusen för din begäran på **fliken Användaråtgärder,** som kommer att godkännas efter bara några timmar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="8ebc7-204">När de begärda enheterna har godkänts läggs de till i labbet och du kan skapa fler enheter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="8ebc7-205">Glöm inte att se vårt simuleringsbibliotek för att få ut mer av ditt lab.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="8ebc7-206">Simulera attackscenarier</span><span class="sxs-lookup"><span data-stu-id="8ebc7-206">Simulate attack scenarios</span></span>
<span data-ttu-id="8ebc7-207">Använd testenheterna för att köra egna attack simuleringar genom att ansluta till dem.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="8ebc7-208">Du kan simulera attackscenarier med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="8ebc7-209">[Attackscenarierna "Gör det själv"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="8ebc7-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="8ebc7-210">Hotbild</span><span class="sxs-lookup"><span data-stu-id="8ebc7-210">Threat simulators</span></span>

<span data-ttu-id="8ebc7-211">Du kan också använda [Avancerad sökning för](advanced-hunting-overview.md) att söka efter data och [hotanalyser för](threat-analytics.md) att visa rapporter om nya hot.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-211">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="8ebc7-212">Gör det själv-attackscenarier</span><span class="sxs-lookup"><span data-stu-id="8ebc7-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="8ebc7-213">Om du letar efter en färdig simulering kan du använda våra ["Gör det själv"-attackscenarier](https://securitycenter.windows.com/tutorials).</span><span class="sxs-lookup"><span data-stu-id="8ebc7-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="8ebc7-214">De här skripten är säkra, har dokumenterats och är enkla att använda.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="8ebc7-215">De här scenarierna återspeglar Defender för Slutpunkt-funktioner och går igenom undersökningsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="8ebc7-216">Anslutningen till testenheterna görs med RDP.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="8ebc7-217">Kontrollera att dina brandväggsinställningar tillåter RDP-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="8ebc7-218">Anslut till din enhet och köra en attack simulering genom att **välja Anslut**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Bild på anslutningsknappen för testenheter](images/test-machine-table.png)

2. <span data-ttu-id="8ebc7-220">Spara RDP-filen och starta den genom att välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Bild av anslutning till fjärrskrivbord](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="8ebc7-222">Om du inte har en kopia av lösenordet sparats vid den första  installationen kan du återställa lösenordet genom att välja Återställ lösenord på menyn: Bild på ![ återställa lösenord](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="8ebc7-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="8ebc7-223">Enheten ändrar statusen till "Kör återställning av lösenord", och sedan får du det nya lösenordet om några minuter.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="8ebc7-224">Ange det lösenord som visades när enheten skapades.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![Bild av fönstret för att ange autentiseringsuppgifter](images/enter-password.png)

4. <span data-ttu-id="8ebc7-226">Kör Do-it-yourself-attack simuleringar på enheten.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="8ebc7-227">Hotscenarier</span><span class="sxs-lookup"><span data-stu-id="8ebc7-227">Threat simulator scenarios</span></span>
<span data-ttu-id="8ebc7-228">Om du valde att installera någon av de hot som stöds under labinstallationen kan du köra de inbyggda simuleringarna på utvärderingslabbenheterna.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="8ebc7-229">Att köra simuleringar av hot med tredjepartsplattformar är ett bra sätt att utvärdera Microsoft Defender för Slutpunktsfunktionerna i en labmiljö.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="8ebc7-230">Innan du kan köra simuleringar ser du till att följande krav uppfylls:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="8ebc7-231">Enheter måste läggas till i utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="8ebc7-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="8ebc7-232">Hot måste installeras i utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="8ebc7-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="8ebc7-233">Välj Skapa simulering i **portalen**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="8ebc7-234">Välj ett hot.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-234">Select a threat simulator.</span></span>

    ![Bild av hotmarkering](images/select-simulator.png)

3. <span data-ttu-id="8ebc7-236">Välj en simulering eller titta igenom simuleringsgalleriet och bläddra igenom de tillgängliga simuleringarna.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="8ebc7-237">Du kan gå till simuleringsgalleriet från:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="8ebc7-238">Huvudpanelen för utvärdering i panelen **för simuleringsöversikt** eller</span><span class="sxs-lookup"><span data-stu-id="8ebc7-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="8ebc7-239">Genom att navigera från navigeringsfönstret **Utvärdering och självstudiekurser**  >  **om simulering &** och sedan välja **Simuleringskatalog**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="8ebc7-240">Välj de enheter där du vill köra simuleringen på.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="8ebc7-241">Välj **Skapa simulering**.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="8ebc7-242">Visa förloppet för en simulering genom att välja **fliken Simuleringar.** Visa simuleringstillståndet, aktiva aviseringar och annan information.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Bild på simuleringsfliken](images/simulations-tab.png)
    
<span data-ttu-id="8ebc7-244">När du har kört din simulering rekommenderar vi att du går igenom labbförloppet och utforskar Microsoft Defender för Endpoint orsakade en automatiserad **undersökning och åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="8ebc7-245">Ta en kontroll över bevisen som samlas in och analyseras av funktionen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="8ebc7-246">Sök efter attackbevis genom avancerad sökning med hjälp av det avancerade frågespråket och den obearbetade telemetrin, och ta en titta på några av de hot som beskrivs i hotanalyser världen över.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="8ebc7-247">Simuleringsgalleriet</span><span class="sxs-lookup"><span data-stu-id="8ebc7-247">Simulation gallery</span></span>
<span data-ttu-id="8ebc7-248">Microsoft Defender för Endpoint har samarbetat med olika simuleringsplattformar för hot för att ge dig bekväm åtkomst till att testa plattformens funktioner direkt från portalen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="8ebc7-249">Visa alla tillgängliga simuleringar genom att gå till Simuleringar och **självstudiekurser**  >  **för simuleringskatalogen** på menyn.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="8ebc7-250">En lista över simuleringsagenter från tredje part som stöds visas och specifika typer av simuleringar tillsammans med detaljerade beskrivningar ges i katalogen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="8ebc7-251">Du kan enkelt köra alla tillgängliga simuleringar direkt från katalogen.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![Bild på simuleringskatalog](images/simulations-catalog.png)

<span data-ttu-id="8ebc7-253">Varje simulering levereras med en detaljerad beskrivning av attackscenariot och referenser som MITRE-attacktekniker som används och exempel på avancerade sökfrågor du kör.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="8ebc7-254">**Exempel:** 
 ![ Bild på beskrivning av simulering1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="8ebc7-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Bild på beskrivning av simulering2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="8ebc7-256">Utvärderingsrapport</span><span class="sxs-lookup"><span data-stu-id="8ebc7-256">Evaluation report</span></span>
<span data-ttu-id="8ebc7-257">Labrapporterna sammanfattar resultaten av simuleringarna på enheterna.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Bild av utvärderingsrapporten](images/eval-report.png)

<span data-ttu-id="8ebc7-259">Du kommer snabbt att kunna se:</span><span class="sxs-lookup"><span data-stu-id="8ebc7-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="8ebc7-260">Incidenter som utlöstes</span><span class="sxs-lookup"><span data-stu-id="8ebc7-260">Incidents that were triggered</span></span>
- <span data-ttu-id="8ebc7-261">Genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="8ebc7-261">Generated alerts</span></span>
- <span data-ttu-id="8ebc7-262">Utvärderingar av exponeringsnivå</span><span class="sxs-lookup"><span data-stu-id="8ebc7-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="8ebc7-263">Observerade hotkategorier</span><span class="sxs-lookup"><span data-stu-id="8ebc7-263">Threat categories observed</span></span>
- <span data-ttu-id="8ebc7-264">Identifiera källor</span><span class="sxs-lookup"><span data-stu-id="8ebc7-264">Detection sources</span></span>
- <span data-ttu-id="8ebc7-265">Automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="8ebc7-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="8ebc7-266">Ge feedback</span><span class="sxs-lookup"><span data-stu-id="8ebc7-266">Provide feedback</span></span>
<span data-ttu-id="8ebc7-267">Din feedback hjälper oss att bli bättre i din miljö mot avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="8ebc7-268">Dela din upplevelse och intryck från produktfunktioner och utvärderingsresultat.</span><span class="sxs-lookup"><span data-stu-id="8ebc7-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="8ebc7-269">Berätta vad du tycker genom att välja **Ge feedback.**</span><span class="sxs-lookup"><span data-stu-id="8ebc7-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Bild på feedback](images/send-us-feedback-eval-lab.png)
