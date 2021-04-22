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
ms.openlocfilehash: ed2165c0102170256f50964180a550d8eccbce8c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932793"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="59b4c-104">Microsoft Defender för utvärderingslabb med slutpunkt</span><span class="sxs-lookup"><span data-stu-id="59b4c-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="59b4c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="59b4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="59b4c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="59b4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="59b4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59b4c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="59b4c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="59b4c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="59b4c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="59b4c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="59b4c-110">Att genomföra en omfattande utvärdering av säkerhetsprodukter kan vara en komplex process som kräver krångliga miljöer och enhetskonfigurationer innan en helslutsattack simulering kan utföras.</span><span class="sxs-lookup"><span data-stu-id="59b4c-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="59b4c-111">Till komplexiteten läggs utmaningen att spåra var simuleringsaktiviteter, varningar och resultat återspeglas under utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="59b4c-112">Utvärderingslabb med Microsoft Defender för slutpunkter är utformat för att eliminera komplexiteten i konfigurationen av enheter och miljöer så att du kan fokusera på att utvärdera plattformens funktioner, köra simuleringar och se funktionerna för skydd, identifiering och åtgärder i praktiken.</span><span class="sxs-lookup"><span data-stu-id="59b4c-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="59b4c-113">Med den förenklade uppsättningen kan du fokusera på att köra egna testscenarier och de färdiga simuleringarna och se hur Defender för Slutpunkt fungerar.</span><span class="sxs-lookup"><span data-stu-id="59b4c-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="59b4c-114">Du har full tillgång till plattformens kraftfulla funktioner, som automatiska undersökningar, avancerad sökning och hotanalys, så att du kan testa den omfattande skyddsstacken som Defender för Slutpunkt erbjuder.</span><span class="sxs-lookup"><span data-stu-id="59b4c-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="59b4c-115">Du kan lägga till Windows 10- eller Windows Server 2019-enheter som är förkonfigurerade så att de senaste os-versionerna och rätt säkerhetskomponenter och Office 2019 Standard är installerade.</span><span class="sxs-lookup"><span data-stu-id="59b4c-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="59b4c-116">Du kan även installera hot.</span><span class="sxs-lookup"><span data-stu-id="59b4c-116">You can also install threat simulators.</span></span> <span data-ttu-id="59b4c-117">Defender för Endpoint har samarbetat med branschledande simuleringsplattformar för hot som hjälper dig att testa Defender för Slutpunkt-funktioner utan att behöva lämna portalen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="59b4c-118">Installera det du föredrar, kör scenarier i utvärderingslabbet och se direkt hur plattformen fungerar – allt finns tillgängligt utan extra kostnad för dig.</span><span class="sxs-lookup"><span data-stu-id="59b4c-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="59b4c-119">Du får också praktisk tillgång till ett brett utbud av simuleringar som du kan komma åt och köra från simuleringskatalogen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="59b4c-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="59b4c-120">Before you begin</span></span>
<span data-ttu-id="59b4c-121">Du måste uppfylla licenskraven eller ha [utvärderingsåtkomst till](minimum-requirements.md#licensing-requirements) Microsoft Defender för Endpoint för att komma åt utvärderingslabbet.</span><span class="sxs-lookup"><span data-stu-id="59b4c-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="59b4c-122">Du måste ha **behörigheten Hantera säkerhetsinställningar** för att:</span><span class="sxs-lookup"><span data-stu-id="59b4c-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="59b4c-123">Skapa labbet</span><span class="sxs-lookup"><span data-stu-id="59b4c-123">Create the lab</span></span>
- <span data-ttu-id="59b4c-124">Skapa enheter</span><span class="sxs-lookup"><span data-stu-id="59b4c-124">Create devices</span></span>
- <span data-ttu-id="59b4c-125">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="59b4c-125">Reset password</span></span>
- <span data-ttu-id="59b4c-126">Skapa simuleringar</span><span class="sxs-lookup"><span data-stu-id="59b4c-126">Create simulations</span></span> 
 
<span data-ttu-id="59b4c-127">Om du har aktiverat rollbaserad åtkomstkontroll (RBAC) och skapat minst en datorgrupp, måste användarna ha åtkomst till Alla datorgrupper.</span><span class="sxs-lookup"><span data-stu-id="59b4c-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="59b4c-128">Mer information finns i Skapa [och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="59b4c-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="59b4c-129">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="59b4c-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="59b4c-130">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="59b4c-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="59b4c-131">Kom igång med labbet</span><span class="sxs-lookup"><span data-stu-id="59b4c-131">Get started with the lab</span></span>
<span data-ttu-id="59b4c-132">Du kan komma åt labbet från menyn.</span><span class="sxs-lookup"><span data-stu-id="59b4c-132">You can access the lab from the menu.</span></span> <span data-ttu-id="59b4c-133">I navigeringsmenyn väljer du **Utvärdering och självstudier > Utvärderingslabb.**</span><span class="sxs-lookup"><span data-stu-id="59b4c-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Bild på utvärderingslabb på menyn](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="59b4c-135">Beroende på vilken typ av miljöstruktur du väljer blir enheter tillgängliga under det angivna antalet timmar från aktiveringsdagen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="59b4c-136">Varje miljö etableras med ett begränsat antal testenheter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="59b4c-137">När du använt de etablerade enheterna tillhandahålls inga nya enheter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="59b4c-138">En borttagna enhet uppdaterar inte antalet tillgängliga testenhet.</span><span class="sxs-lookup"><span data-stu-id="59b4c-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="59b4c-139">Du kan inte längre använda labbet när resurserna har använts upp.</span><span class="sxs-lookup"><span data-stu-id="59b4c-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="59b4c-140">Den återställs inte eller uppdateras inte.</span><span class="sxs-lookup"><span data-stu-id="59b4c-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="59b4c-141">Vi rekommenderar att du använder resurserna noggrant. Labbresurserna är begränsade.</span><span class="sxs-lookup"><span data-stu-id="59b4c-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="59b4c-142">De återställs inte eller uppdateras inte.</span><span class="sxs-lookup"><span data-stu-id="59b4c-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="59b4c-143">Har du redan ett labb?</span><span class="sxs-lookup"><span data-stu-id="59b4c-143">Already have a lab?</span></span> <span data-ttu-id="59b4c-144">Se till att aktivera de nya hoten och ha aktiva enheter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="59b4c-145">Konfigurera utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="59b4c-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="59b4c-146">Välj Utvärderings- och **självstudiekurser**  >  **Utvärderingslabb** i navigeringsfönstret och välj sedan **Installationslabb.**</span><span class="sxs-lookup"><span data-stu-id="59b4c-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Bild på välkomstsidan för utvärderingslabb](images/evaluation-lab-setup.png)

2. <span data-ttu-id="59b4c-148">Beroende på dina utvärderingsbehov kan du välja att konfigurera en miljö med färre enheter under en längre period eller fler enheter under kortare tid.</span><span class="sxs-lookup"><span data-stu-id="59b4c-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="59b4c-149">Välj önskad labkonfiguration och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![Bild på konfigurationsalternativ för lab](images/lab-creation-page.png) 


3. <span data-ttu-id="59b4c-151">(Valfritt) Du kan välja att installera hot i labbet.</span><span class="sxs-lookup"><span data-stu-id="59b4c-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Bild på agent för installation av installation](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="59b4c-153">Först måste du godkänna och godkänna användningsvillkoren och informationsdelningssatserna.</span><span class="sxs-lookup"><span data-stu-id="59b4c-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="59b4c-154">Välj den simulering av hot som du vill använda och ange din information.</span><span class="sxs-lookup"><span data-stu-id="59b4c-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="59b4c-155">Du kan också välja att installera hot vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="59b4c-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="59b4c-156">Om du väljer att installera simuleringsagenter för hot under installationen av lab får du fördelen med att ha dem installerade på de enheter du lägger till.</span><span class="sxs-lookup"><span data-stu-id="59b4c-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Bild på sammanfattningssida](images/lab-setup-summary.png)

5.  <span data-ttu-id="59b4c-158">Granska sammanfattningen och välj **Installationslabb**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="59b4c-159">När labinstallationen är klar kan du lägga till enheter och köra simuleringar.</span><span class="sxs-lookup"><span data-stu-id="59b4c-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="59b4c-160">Lägg till enheter</span><span class="sxs-lookup"><span data-stu-id="59b4c-160">Add devices</span></span>
<span data-ttu-id="59b4c-161">När du lägger till en enhet i din miljö konfigurerar Defender för Endpoint en välkonfigurerad enhet med anslutningsinformation.</span><span class="sxs-lookup"><span data-stu-id="59b4c-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="59b4c-162">Du kan lägga till Windows 10- eller Windows Server 2019-enheter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="59b4c-163">Enheten konfigureras med den senaste versionen av operativsystemet och Office 2019 Standard samt med andra appar som Java, Python och SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="59b4c-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="59b4c-164">Behöver du fler enheter i labbet?</span><span class="sxs-lookup"><span data-stu-id="59b4c-164">Need more devices in your lab?</span></span> <span data-ttu-id="59b4c-165">Skicka ett supportbegäran om du vill att din begäran ska granskas av Defender för Endpoint-teamet.</span><span class="sxs-lookup"><span data-stu-id="59b4c-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="59b4c-166">Om du väljer att lägga till en hotbild under installationen av lab kommer alla enheter att ha hotagent installerad på de enheter som du lägger till.</span><span class="sxs-lookup"><span data-stu-id="59b4c-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="59b4c-167">Enheten introduceras automatiskt i din klientorganisation med de rekommenderade Windows-säkerhetskomponenterna påslagna och i granskningsläge – utan ansträngning från din sida.</span><span class="sxs-lookup"><span data-stu-id="59b4c-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="59b4c-168">Följande säkerhetskomponenter är förkonfigurerade i testenheterna:</span><span class="sxs-lookup"><span data-stu-id="59b4c-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="59b4c-169">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="59b4c-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="59b4c-170">Blockera vid första synen</span><span class="sxs-lookup"><span data-stu-id="59b4c-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="59b4c-171">Kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="59b4c-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="59b4c-172">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="59b4c-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="59b4c-173">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="59b4c-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="59b4c-174">Potentiellt oönskad identifiering av program</span><span class="sxs-lookup"><span data-stu-id="59b4c-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="59b4c-175">Molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="59b4c-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="59b4c-176">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="59b4c-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="59b4c-177">Microsoft Defender Antivirus är aktiverat (inte i granskningsläge).</span><span class="sxs-lookup"><span data-stu-id="59b4c-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="59b4c-178">Om Microsoft Defender Antivirus blockerar dig från att köra din simulering kan du inaktivera realtidsskydd på enheten via Windows-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="59b4c-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="59b4c-179">Mer information finns i [Konfigurera alltid-på-skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="59b4c-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="59b4c-180">Inställningar för automatisk undersökning beror på klientorganisationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="59b4c-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="59b4c-181">Den konfigureras som standard semi-automatiserad.</span><span class="sxs-lookup"><span data-stu-id="59b4c-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="59b4c-182">Mer information finns i [Översikt över automatiserade undersökningar.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="59b4c-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="59b4c-183">Anslutningen till testenheterna görs med RDP.</span><span class="sxs-lookup"><span data-stu-id="59b4c-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="59b4c-184">Kontrollera att dina brandväggsinställningar tillåter RDP-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="59b4c-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="59b4c-185">Välj Lägg till enhet på **instrumentpanelen.**</span><span class="sxs-lookup"><span data-stu-id="59b4c-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="59b4c-186">Välj vilken typ av enhet du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="59b4c-186">Choose the type of device to add.</span></span> <span data-ttu-id="59b4c-187">Du kan välja att lägga till Windows 10 eller Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="59b4c-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Bild på labkonfiguration med enhetsalternativ](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="59b4c-189">Om något går fel med processen för att skapa enhet får du ett meddelande och du måste skicka en ny begäran.</span><span class="sxs-lookup"><span data-stu-id="59b4c-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="59b4c-190">Om enheten skapas utan fel räknas den inte in i den totala tillåtna kvoten.</span><span class="sxs-lookup"><span data-stu-id="59b4c-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="59b4c-191">Anslutningsinformationen visas.</span><span class="sxs-lookup"><span data-stu-id="59b4c-191">The connection details are displayed.</span></span> <span data-ttu-id="59b4c-192">Välj **Kopiera** för att spara lösenordet för enheten.</span><span class="sxs-lookup"><span data-stu-id="59b4c-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="59b4c-193">Lösenordet visas bara en gång.</span><span class="sxs-lookup"><span data-stu-id="59b4c-193">The password is only displayed once.</span></span> <span data-ttu-id="59b4c-194">Se till att spara den för senare användning.</span><span class="sxs-lookup"><span data-stu-id="59b4c-194">Be sure to save it for later use.</span></span>

    ![Bild på enhet som lagts till med anslutningsinformation](images/add-machine-eval-lab.png)

4. <span data-ttu-id="59b4c-196">Enhetsuppsättningen startar.</span><span class="sxs-lookup"><span data-stu-id="59b4c-196">Device set up begins.</span></span> <span data-ttu-id="59b4c-197">Det kan ta upp till cirka 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="59b4c-198">Se status för testenheter, risk- och exponeringsnivåer och status för installationerna genom att välja **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Bild på fliken Enheter](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="59b4c-200">I kolumnen **Förnamnsstatus** kan du hovra över informationsikonen för att få information om installationsstatus för en agent.</span><span class="sxs-lookup"><span data-stu-id="59b4c-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="59b4c-201">Simulera attackscenarier</span><span class="sxs-lookup"><span data-stu-id="59b4c-201">Simulate attack scenarios</span></span>
<span data-ttu-id="59b4c-202">Använd testenheterna för att köra egna attack simuleringar genom att ansluta till dem.</span><span class="sxs-lookup"><span data-stu-id="59b4c-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="59b4c-203">Du kan simulera attackscenarier med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="59b4c-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="59b4c-204">[Attackscenarierna "Gör det själv"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="59b4c-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="59b4c-205">Hotbild</span><span class="sxs-lookup"><span data-stu-id="59b4c-205">Threat simulators</span></span>

<span data-ttu-id="59b4c-206">Du kan också använda [Avancerad sökning för](advanced-hunting-query-language.md) att söka efter data och [hotanalyser för](threat-analytics.md) att visa rapporter om nya hot.</span><span class="sxs-lookup"><span data-stu-id="59b4c-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="59b4c-207">Gör det själv-attackscenarier</span><span class="sxs-lookup"><span data-stu-id="59b4c-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="59b4c-208">Om du letar efter en färdig simulering kan du använda våra ["Gör det själv"-attackscenarier](https://securitycenter.windows.com/tutorials).</span><span class="sxs-lookup"><span data-stu-id="59b4c-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="59b4c-209">De här skripten är säkra, har dokumenterats och är enkla att använda.</span><span class="sxs-lookup"><span data-stu-id="59b4c-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="59b4c-210">De här scenarierna återspeglar Defender för Slutpunkt-funktioner och går igenom undersökningsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="59b4c-211">Anslutningen till testenheterna görs med RDP.</span><span class="sxs-lookup"><span data-stu-id="59b4c-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="59b4c-212">Kontrollera att dina brandväggsinställningar tillåter RDP-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="59b4c-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="59b4c-213">Anslut till din enhet och kör en attack simulering genom att välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Bild på anslutningsknappen för testenheter](images/test-machine-table.png)

2. <span data-ttu-id="59b4c-215">Spara RDP-filen och starta den genom att välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Bild av anslutning till fjärrskrivbord](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="59b4c-217">Om du inte har en kopia av lösenordet sparats vid den första  installationen kan du återställa lösenordet genom att välja Återställ lösenord på menyn: Bild på ![ återställa lösenord](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="59b4c-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="59b4c-218">Enheten ändrar statusen till "Kör återställning av lösenord", och sedan får du det nya lösenordet om några minuter.</span><span class="sxs-lookup"><span data-stu-id="59b4c-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="59b4c-219">Ange det lösenord som visades när enheten skapades.</span><span class="sxs-lookup"><span data-stu-id="59b4c-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![Bild av fönstret för att ange autentiseringsuppgifter](images/enter-password.png)

4. <span data-ttu-id="59b4c-221">Kör Do-it-yourself-attack simuleringar på enheten.</span><span class="sxs-lookup"><span data-stu-id="59b4c-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="59b4c-222">Hotscenarier</span><span class="sxs-lookup"><span data-stu-id="59b4c-222">Threat simulator scenarios</span></span>
<span data-ttu-id="59b4c-223">Om du valde att installera någon av de hot som stöds under labinstallationen kan du köra de inbyggda simuleringarna på utvärderingslabbenheterna.</span><span class="sxs-lookup"><span data-stu-id="59b4c-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="59b4c-224">Att köra simuleringar av hot med tredjepartsplattformar är ett bra sätt att utvärdera Microsoft Defender för Slutpunktsfunktionerna i en labmiljö.</span><span class="sxs-lookup"><span data-stu-id="59b4c-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="59b4c-225">Innan du kan köra simuleringar ser du till att följande krav uppfylls:</span><span class="sxs-lookup"><span data-stu-id="59b4c-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="59b4c-226">Enheter måste läggas till i utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="59b4c-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="59b4c-227">Hot måste installeras i utvärderingslabb</span><span class="sxs-lookup"><span data-stu-id="59b4c-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="59b4c-228">Välj Skapa simulering i **portalen**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="59b4c-229">Välj ett hot.</span><span class="sxs-lookup"><span data-stu-id="59b4c-229">Select a threat simulator.</span></span>

    ![Bild av hotmarkering](images/select-simulator.png)

3. <span data-ttu-id="59b4c-231">Välj en simulering eller titta igenom simuleringsgalleriet och bläddra igenom de tillgängliga simuleringarna.</span><span class="sxs-lookup"><span data-stu-id="59b4c-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="59b4c-232">Du kan gå till simuleringsgalleriet från:</span><span class="sxs-lookup"><span data-stu-id="59b4c-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="59b4c-233">Huvudpanelen för utvärdering i panelen **för simuleringsöversikt** eller</span><span class="sxs-lookup"><span data-stu-id="59b4c-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="59b4c-234">Genom att navigera från navigeringsfönstret **Utvärdering och självstudiekurser**  >  **om simulering &** och sedan välja **Simuleringskatalog**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="59b4c-235">Välj de enheter där du vill köra simuleringen på.</span><span class="sxs-lookup"><span data-stu-id="59b4c-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="59b4c-236">Välj **Skapa simulering**.</span><span class="sxs-lookup"><span data-stu-id="59b4c-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="59b4c-237">Visa förloppet för en simulering genom att välja **fliken Simuleringar.** Visa simuleringstillståndet, aktiva aviseringar och annan information.</span><span class="sxs-lookup"><span data-stu-id="59b4c-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Bild på simuleringsfliken](images/simulations-tab.png)
    
<span data-ttu-id="59b4c-239">När du har kört din simulering rekommenderar vi att du går igenom labbförloppet och utforskar Microsoft Defender för Endpoint orsakade en automatiserad **undersökning och åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="59b4c-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="59b4c-240">Ta en kontroll över bevisen som samlas in och analyseras av funktionen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="59b4c-241">Sök efter attackbevis genom avancerad sökning med hjälp av det avancerade frågespråket och den obearbetade telemetrin, och ta en titta på några av de hot som beskrivs i hotanalyser världen över.</span><span class="sxs-lookup"><span data-stu-id="59b4c-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="59b4c-242">Simuleringsgalleriet</span><span class="sxs-lookup"><span data-stu-id="59b4c-242">Simulation gallery</span></span>
<span data-ttu-id="59b4c-243">Microsoft Defender för Endpoint har samarbetat med olika simuleringsplattformar för hot för att ge dig bekväm åtkomst till att testa plattformens funktioner direkt från portalen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="59b4c-244">Visa alla tillgängliga simuleringar genom att gå till Simuleringar och **självstudiekurser**  >  **för simuleringskatalogen** på menyn.</span><span class="sxs-lookup"><span data-stu-id="59b4c-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="59b4c-245">En lista över simuleringsagenter från tredje part som stöds visas och specifika typer av simuleringar tillsammans med detaljerade beskrivningar ges i katalogen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="59b4c-246">Du kan enkelt köra alla tillgängliga simuleringar direkt från katalogen.</span><span class="sxs-lookup"><span data-stu-id="59b4c-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![Bild på simuleringskatalog](images/simulations-catalog.png)

<span data-ttu-id="59b4c-248">Varje simulering levereras med en detaljerad beskrivning av attackscenariot och referenser som MITRE-attacktekniker som används och exempel på avancerade sökfrågor du kör.</span><span class="sxs-lookup"><span data-stu-id="59b4c-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="59b4c-249">**Exempel:** 
 ![ Bild på beskrivning av simulering1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="59b4c-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Bild på beskrivning av simulering2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="59b4c-251">Utvärderingsrapport</span><span class="sxs-lookup"><span data-stu-id="59b4c-251">Evaluation report</span></span>
<span data-ttu-id="59b4c-252">Labrapporterna sammanfattar resultaten av simuleringarna på enheterna.</span><span class="sxs-lookup"><span data-stu-id="59b4c-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Bild av utvärderingsrapporten](images/eval-report.png)

<span data-ttu-id="59b4c-254">Du kommer snabbt att kunna se:</span><span class="sxs-lookup"><span data-stu-id="59b4c-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="59b4c-255">Incidenter som utlöstes</span><span class="sxs-lookup"><span data-stu-id="59b4c-255">Incidents that were triggered</span></span>
- <span data-ttu-id="59b4c-256">Genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="59b4c-256">Generated alerts</span></span>
- <span data-ttu-id="59b4c-257">Utvärderingar av exponeringsnivå</span><span class="sxs-lookup"><span data-stu-id="59b4c-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="59b4c-258">Observerade hotkategorier</span><span class="sxs-lookup"><span data-stu-id="59b4c-258">Threat categories observed</span></span>
- <span data-ttu-id="59b4c-259">Identifiera källor</span><span class="sxs-lookup"><span data-stu-id="59b4c-259">Detection sources</span></span>
- <span data-ttu-id="59b4c-260">Automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="59b4c-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="59b4c-261">Ge feedback</span><span class="sxs-lookup"><span data-stu-id="59b4c-261">Provide feedback</span></span>
<span data-ttu-id="59b4c-262">Din feedback hjälper oss att bli bättre i din miljö mot avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="59b4c-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="59b4c-263">Dela din upplevelse och intryck från produktfunktioner och utvärderingsresultat.</span><span class="sxs-lookup"><span data-stu-id="59b4c-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="59b4c-264">Berätta vad du tycker genom att välja **Ge feedback.**</span><span class="sxs-lookup"><span data-stu-id="59b4c-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Bild på feedback](images/send-us-feedback-eval-lab.png)
