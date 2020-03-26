---
title: Microsoft 365 för företag – strategier för distribuering av grundläggande infrastruktur
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig några av sätten som du kan använda för att distribuera faserna i den grundläggande infrastrukturen för Microsoft 365 för företag.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811464"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="45613-103">Microsoft 365 för företag – strategier för distribuering av grundläggande infrastruktur</span><span class="sxs-lookup"><span data-stu-id="45613-103">Microsoft 365 for enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="45613-104">Det finns många sätt som du kan använda för att distribuera faserna i [den grundläggande infrastrukturen](deploy-foundation-infrastructure.md) för Microsoft 365 för företag och lansera funktioner, program och tjänster för dina användare.</span><span class="sxs-lookup"><span data-stu-id="45613-104">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 for enterprise and roll out its capabilities, software, and services to your users.</span></span> <span data-ttu-id="45613-105">Tänk på följande distributionsstrategier om du vill komma igång med projektledningen av det här jobbet, som kan vara stor och komplicerad beroende på hur stor din organisation är och dess befintliga infrastruktur:</span><span class="sxs-lookup"><span data-stu-id="45613-105">To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="45613-106">Seriell distribution</span><span class="sxs-lookup"><span data-stu-id="45613-106">Serial deployment</span></span>
- <span data-ttu-id="45613-107">Parallell distribution med ej överlappande användarlansering</span><span class="sxs-lookup"><span data-stu-id="45613-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="45613-108">Parallell distribution med överlappande användarlansering</span><span class="sxs-lookup"><span data-stu-id="45613-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="45613-109">Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen</span><span class="sxs-lookup"><span data-stu-id="45613-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="45613-110">Använd de här strategierna för att få förslag på hur du kan hantera det övergripande projektet och hur du snabbare kan använda affärsfördelarna med Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="45613-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 for enterprise.</span></span>

>[!Note]
><span data-ttu-id="45613-111">I den här artikeln beskrivs förutsättningar och förenklingar för att på ett konsekvent sätt beskriva distributionsstrategierna.</span><span class="sxs-lookup"><span data-stu-id="45613-111">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies.</span></span> <span data-ttu-id="45613-112">Dessa distributionsstrategier är allmänna och är inte avsedda att ange vissa tidsramar. De är inte heller avsedda att tillämpas för alla organisationer och situationer.</span><span class="sxs-lookup"><span data-stu-id="45613-112">These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="45613-113">Element i IT-projektledning för typiska företagsorganisationer</span><span class="sxs-lookup"><span data-stu-id="45613-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="45613-114">IT-infrastruktur omfattar både serverdelstjänster och lansering av nya eller förbättrade funktioner eller installerad programvara för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="45613-114">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users.</span></span> <span data-ttu-id="45613-115">IT-avdelningar distribuerar vanligtvis delar av en IT-infrastruktur på ett metodiskt sätt.</span><span class="sxs-lookup"><span data-stu-id="45613-115">IT departments typically deploy elements of an IT infrastructure in a methodical way.</span></span> <span data-ttu-id="45613-116">En metod för framgångsrik distribution av ett element i IT-infrastrukturen består av:</span><span class="sxs-lookup"><span data-stu-id="45613-116">One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="45613-117">En pilotlansering</span><span class="sxs-lookup"><span data-stu-id="45613-117">A pilot rollout</span></span> 

  <span data-ttu-id="45613-118">Den omfattar en första konfiguration av infrastruktur och lansering av en pilotuppsättning användare, tester och efterföljande ändringar av infrastrukturens konfiguration.</span><span class="sxs-lookup"><span data-stu-id="45613-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="45613-119">En användarlansering</span><span class="sxs-lookup"><span data-stu-id="45613-119">A user rollout</span></span>

  <span data-ttu-id="45613-120">Den omfattar lanseringen till resten av din organisation baserat på regioner, avdelningar, grupper eller andra typer av systematisk spridning av konfiguration eller programvara.</span><span class="sxs-lookup"><span data-stu-id="45613-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="45613-121">Uppsättningen användare som ingår i pilotlanseringen är inte desamma som ingår i användarlanseringen.</span><span class="sxs-lookup"><span data-stu-id="45613-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="45613-122">I den här artikeln används följande grafik för att åskådliggöra definitionerna:</span><span class="sxs-lookup"><span data-stu-id="45613-122">This article uses the following graphics to depict these definitions:</span></span> 

![Grafiken som visar definitionerna av pilot- och användarlansering](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="45613-124">Skuggan för grafiken som visar användarlanseringen anger procentsatsen i din organisation från 0 % till 100 % som använder en strukturerad eller metodisk metod, t. ex. grupper, avdelningar eller regioner.</span><span class="sxs-lookup"><span data-stu-id="45613-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="45613-125">Distributionsstrategier</span><span class="sxs-lookup"><span data-stu-id="45613-125">Deployment strategies</span></span>

<span data-ttu-id="45613-126">Överväg följande distributionsstrategier:</span><span class="sxs-lookup"><span data-stu-id="45613-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="45613-127">Seriell distribution</span><span class="sxs-lookup"><span data-stu-id="45613-127">Serial deployment</span></span>
- <span data-ttu-id="45613-128">Parallell distribution med ej överlappande användarlansering</span><span class="sxs-lookup"><span data-stu-id="45613-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="45613-129">Parallell distribution med överlappande användarlansering</span><span class="sxs-lookup"><span data-stu-id="45613-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="45613-130">Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen</span><span class="sxs-lookup"><span data-stu-id="45613-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="45613-131">Seriell distribution</span><span class="sxs-lookup"><span data-stu-id="45613-131">Serial deployment</span></span>

<span data-ttu-id="45613-132">Vid seriell distribution slutför du en fas helt och ser till att fasen distribueras till 100 % till alla dina användare innan du går vidare till nästa fas.</span><span class="sxs-lookup"><span data-stu-id="45613-132">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one.</span></span> <span data-ttu-id="45613-133">Här är några anledningar till varför det kan vara bra att distribuera på det här sättet:</span><span class="sxs-lookup"><span data-stu-id="45613-133">Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="45613-134">Riskhantering</span><span class="sxs-lookup"><span data-stu-id="45613-134">Risk mitigation</span></span>
- <span data-ttu-id="45613-135">Resursbegränsningar</span><span class="sxs-lookup"><span data-stu-id="45613-135">Resourcing constraints</span></span>
- <span data-ttu-id="45613-136">Finansieringscykler för IT-avdelningen</span><span class="sxs-lookup"><span data-stu-id="45613-136">IT department funding cycles</span></span>
- <span data-ttu-id="45613-137">IT-teknikberoenden</span><span class="sxs-lookup"><span data-stu-id="45613-137">IT technology dependencies</span></span>
- <span data-ttu-id="45613-138">Företagets förändringshantering och slutanvändares resistens</span><span class="sxs-lookup"><span data-stu-id="45613-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="45613-139">I det här Gantt-schemat visas en förenklad seriell distribution av fas 2–6 av den grundläggande infrastrukturen för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="45613-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 for enterprise.</span></span>

![Seriell distribution av fas 2–6 av den grundläggande infrastrukturen](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="45613-141">För att förenkla diskussionen och exemplet måste samtliga fas- och distributionssegment i varje fas pågå lika länge.</span><span class="sxs-lookup"><span data-stu-id="45613-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="45613-142">Fas 1: Nätverk för den grundläggande infrastrukturen för Microsoft 365 för företag är en fas som endast berör IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="45613-142">Phase 1: Networking of the Microsoft 365 for enterprise Foundation Infrastructure is an IT department-only phase.</span></span> <span data-ttu-id="45613-143">Användare drar nytta av fördelarna med optimerad anslutning till Microsofts molnresurser men de behöver inte göra något för att få den.</span><span class="sxs-lookup"><span data-stu-id="45613-143">Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="45613-144">Här följer en förenklad pilotupplevelse för användare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="45613-145">I december behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-145">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-146">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-146">(Identity)</span></span>
- <span data-ttu-id="45613-147">I mars får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-147">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-148">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-148">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-149">I juni får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-149">In June, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-150">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-150">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-151">I september får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-152">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-152">(Mobile device management)</span></span>
- <span data-ttu-id="45613-153">I december får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-153">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-154">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-154">(Information protection)</span></span>

<span data-ttu-id="45613-155">Resultatet är en takt på 90 dagar mellan på varandra följande pilotlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="45613-156">Här följer en förenklad upplevelse för slutanvändare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="45613-157">I januari behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-157">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-158">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-158">(Identity)</span></span>
- <span data-ttu-id="45613-159">I april får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-159">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-160">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-160">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-161">I juli får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-161">In July, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-162">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-162">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-163">I oktober får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-164">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-164">(Mobile device management)</span></span>
- <span data-ttu-id="45613-165">I januari efterföljande år får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-165">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-166">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-166">(Information protection)</span></span>

<span data-ttu-id="45613-167">Resultatet är en takt på 90 dagar mellan på varandra följande användarlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="45613-168">Nackdelen med den här distributionsstrategin är att det kan ta lång tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="45613-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 for enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="45613-169">Parallell distribution med ej överlappande användarlansering (Parallell 1)</span><span class="sxs-lookup"><span data-stu-id="45613-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="45613-170">För den här distributionsstrategin startar du pilotlanseringen för nästa fas under sista delen av användarlanseringen för den aktuella fasen.</span><span class="sxs-lookup"><span data-stu-id="45613-170">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
<span data-ttu-id="45613-171">Här är distributionen av faserna 2–6 när pilotlanseringen inleds då användarlanseringen av föregående fas avslutas.</span><span class="sxs-lookup"><span data-stu-id="45613-171">Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![Den parallella distributionen av faserna 2–6 med ej överlappande användarlansering](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="45613-173">Slutresultatet är att användarlansering för den aktuella fasen slutförs i hela organisationen innan nästa påbörjas.</span><span class="sxs-lookup"><span data-stu-id="45613-173">The end result is that user rollout for the current phase completes across your organization before the next one starts.</span></span> <span data-ttu-id="45613-174">Användare som inte deltar i pilotlanseringar hanterar inte lanseringar av flera faser samtidigt, men pilotlanseringar görs parallellt med användarlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-174">Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="45613-175">Här följer en förenklad pilotupplevelse för användare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="45613-176">I december behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-176">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-177">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-177">(Identity)</span></span>
- <span data-ttu-id="45613-178">I februari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-178">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-179">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-179">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-180">I april får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-180">In April, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-181">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-181">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-182">I juni får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-183">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-183">(Mobile device management)</span></span>
- <span data-ttu-id="45613-184">I augusti får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-184">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-185">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-185">(Information protection)</span></span>

<span data-ttu-id="45613-186">Resultatet är en takt på 60 dagar mellan på varandra följande pilotlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="45613-187">Här följer en förenklad upplevelse för slutanvändare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="45613-188">I januari behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-188">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-189">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-189">(Identity)</span></span>
- <span data-ttu-id="45613-190">I mars får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-190">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-191">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-191">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-192">I maj får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-192">In May, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-193">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-193">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-194">I juli får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-195">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-195">(Mobile device management)</span></span>
- <span data-ttu-id="45613-196">I september får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-196">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-197">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-197">(Information protection)</span></span>

<span data-ttu-id="45613-198">Resultatet är en takt på 60 dagar mellan på varandra följande användarlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="45613-199">Fördelen med den här distributionsstrategin är att det kan ta kortare tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag, utan att IT-avdelningen och användare behöver hantera flera lanseringar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="45613-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="45613-200">Parallell distribution med överlappande användarlansering (Parallell 2)</span><span class="sxs-lookup"><span data-stu-id="45613-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="45613-201">För den här distributionsstrategin startar du:</span><span class="sxs-lookup"><span data-stu-id="45613-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="45613-202">Pilotlanseringen för nästa fas under sista delen av användarlanseringen för den aktuella fasen.</span><span class="sxs-lookup"><span data-stu-id="45613-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="45613-203">Användarlansering av nästa fas under användarlanseringen av den aktuella fasen på ett sätt som gör att inga användare hanterar lanseringar av flera faser samtidigt.</span><span class="sxs-lookup"><span data-stu-id="45613-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="45613-204">Det här förutsätter att du lanserar varje fas av den grundläggande infrastrukturen på samma sätt genom att använda regioner, avdelningar eller andra indelningar.</span><span class="sxs-lookup"><span data-stu-id="45613-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="45613-205">Här är en förenklad jämförelse mellan de olika distributionsstrategierna.</span><span class="sxs-lookup"><span data-stu-id="45613-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![Den parallella distributionen av faserna 2–6 med överlappande användarlansering](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="45613-207">Slutresultatet är:</span><span class="sxs-lookup"><span data-stu-id="45613-207">The end result is that:</span></span>

- <span data-ttu-id="45613-208">Pilotlanseringar går från en fas till nästa utan pauser.</span><span class="sxs-lookup"><span data-stu-id="45613-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="45613-209">Användarlansering för en fas börjar innan användarlanseringen av föregående fas slutförs, men ingen enskild användare får mer än en fas lanserad samtidigt.</span><span class="sxs-lookup"><span data-stu-id="45613-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="45613-210">Här följer en förenklad pilotupplevelse för användare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="45613-211">I december behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-211">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-212">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-212">(Identity)</span></span>
- <span data-ttu-id="45613-213">I januari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-213">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-214">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-214">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-215">I februari får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-215">In February, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-216">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-216">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-217">I mars får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-218">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-218">(Mobile device management)</span></span>
- <span data-ttu-id="45613-219">I april får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-219">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-220">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-220">(Information protection)</span></span>

<span data-ttu-id="45613-221">Resultatet är en takt på 30 dagar mellan på varandra följande pilotlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="45613-222">Här följer en förenklad upplevelse för slutanvändare som exempel:</span><span class="sxs-lookup"><span data-stu-id="45613-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="45613-223">I januari behöver jag använda min smartphone för MFA.</span><span class="sxs-lookup"><span data-stu-id="45613-223">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="45613-224">(Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-224">(Identity)</span></span>
- <span data-ttu-id="45613-225">I februari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="45613-225">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="45613-226">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-226">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-227">I mars får jag Office 365 ProPlus installerat, som ersätter Office 2013.</span><span class="sxs-lookup"><span data-stu-id="45613-227">In March, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="45613-228">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-228">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-229">I april får jag principer för enhetsregistrering, appar och enheter.</span><span class="sxs-lookup"><span data-stu-id="45613-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="45613-230">(Hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-230">(Mobile device management)</span></span>
- <span data-ttu-id="45613-231">I maj får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument.</span><span class="sxs-lookup"><span data-stu-id="45613-231">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="45613-232">(Informationsskydd)</span><span class="sxs-lookup"><span data-stu-id="45613-232">(Information protection)</span></span>

<span data-ttu-id="45613-233">Resultatet är en takt på 30 dagar mellan på varandra följande användarlanseringar.</span><span class="sxs-lookup"><span data-stu-id="45613-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="45613-234">Fördelen med den här distributionsstrategin är att det kan ta ännu kortare tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag, och slutanvändare behöver fortfarande inte hantera flera lanseringar samtidigt.</span><span class="sxs-lookup"><span data-stu-id="45613-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="45613-235">Användare får dock inte någon paus mellan på varandra följande steg.</span><span class="sxs-lookup"><span data-stu-id="45613-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="45613-236">Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen</span><span class="sxs-lookup"><span data-stu-id="45613-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="45613-237">För mindre organisationer som kan komprimera faserna 2–6 till ett enda distributionssegment ser den resulterande distributionen ut så här:</span><span class="sxs-lookup"><span data-stu-id="45613-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="45613-239">IT-avdelningen konfigurerar infrastrukturen för faserna 2–6 och lanserar sedan för pilotanvändarna för att kontrollera funktioner från slutpunkt till slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="45613-239">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality.</span></span> <span data-ttu-id="45613-240">Pilotanvändare får till exempel alla de här funktionerna på samma gång:</span><span class="sxs-lookup"><span data-stu-id="45613-240">For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="45613-241">MFA och andra identitetsfunktioner (Identitet)</span><span class="sxs-lookup"><span data-stu-id="45613-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="45613-242">Windows 10 Enterprise på Windows-enheter (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="45613-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="45613-243">Office 365 ProPlus för Office-paketet (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="45613-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="45613-244">Principer för appar och enheter (hantering av mobila enheter)</span><span class="sxs-lookup"><span data-stu-id="45613-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="45613-245">Azure Information Protection-klienten installeras och utbildning sker om hur man lägger till etiketter i dokument (Informationsskydd).</span><span class="sxs-lookup"><span data-stu-id="45613-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="45613-246">När pilotlanseringen har avslutats inleds användarlanseringen när varje användare får alla funktioner samtidigt.</span><span class="sxs-lookup"><span data-stu-id="45613-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="45613-247">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="45613-247">Next step</span></span>

<span data-ttu-id="45613-248">Inled din distribution av Microsoft 365 för företag med den [grundläggande infrastrukturen](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="45613-248">Start your deployment of Microsoft 365 for enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
