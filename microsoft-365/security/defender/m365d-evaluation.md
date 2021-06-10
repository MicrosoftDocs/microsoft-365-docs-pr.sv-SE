---
title: Microsoft 365 Defender
description: Konfigurera testlabb eller pilotmiljö i Microsoft 365 Defender för att prova och upplev säkerhetslösningen som utformats för att skydda enheter, identitet, data och program i organisationen.
keywords: Microsoft 365 Utvärderingsversion av Defender, prova Microsoft 365 Defender, utvärdera Microsoft 365 Defender, Microsoft 365 Defender utvärderingslabb, Microsoft 365 Defender pilot, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatisk undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933175"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="6c631-104">Skapa en Microsoft 365 Defender-testlabb eller pilotmiljö</span><span class="sxs-lookup"><span data-stu-id="6c631-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c631-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6c631-105">**Applies to:**</span></span>
- <span data-ttu-id="6c631-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c631-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="6c631-107">Den här guiden hjälper dig att arbeta i en labbmiljö med användare och grupper och hjälper dig sedan genom konfigurationen av funktionerna i Microsoft 365 Defender så att du kan efterlikna en hotattack och få ett meningsfullt utvärderingsresultat.</span><span class="sxs-lookup"><span data-stu-id="6c631-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="6c631-108">Syftet med att skapa den här testlabb- eller pilotmiljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="6c631-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="6c631-109">Upplev hur den här intelligenta säkerhetslösningen identifierar, förhindrar, automatiskt undersöker och svarar på avancerade hot som din organisation använder.</span><span class="sxs-lookup"><span data-stu-id="6c631-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="6c631-110">Du vägleds genom stegen för att starta din utvärdering Microsoft 365 Defender baserat på de rekommenderade distributionssökvägarna.</span><span class="sxs-lookup"><span data-stu-id="6c631-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6c631-111">Målet är att hjälpa dig att konfigurera säkerhetslösningen i en labmiljö med ett testkonto eller i en pilotmiljö i produktion med en fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="6c631-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="6c631-112">Förberedelse av utvärderingslabb eller pilotmiljö kan hjälpa dig att presentera säkerhetsåtgärdsanvändningsfall för beslutsfattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c631-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="6c631-113">När du har kört attack simuleringar och är nöjd med resultatet kan du helt distribuera och driftsätta det i organisationen med hjälp av Microsofts tekniska försäljare eller experter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c631-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6c631-114">I den här guiden får du hjälp med att:</span><span class="sxs-lookup"><span data-stu-id="6c631-114">This guide will help you:</span></span>
- <span data-ttu-id="6c631-115">Konfigurera din labserver och dina datorer</span><span class="sxs-lookup"><span data-stu-id="6c631-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="6c631-116">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="6c631-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6c631-117">Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6c631-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6c631-118">Konfigurera lokala principer för server och datorer</span><span class="sxs-lookup"><span data-stu-id="6c631-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="6c631-119">Imitera en hotattack för att generera en testhändelse eller avisering i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c631-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="6c631-120">För bästa resultat följer du labinstallationsanvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="6c631-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6c631-121">Distributionsfaser</span><span class="sxs-lookup"><span data-stu-id="6c631-121">Deployment phases</span></span>

<span data-ttu-id="6c631-122">Det finns tre faser i att skapa en Microsoft 365 Defender testlabbmiljö.</span><span class="sxs-lookup"><span data-stu-id="6c631-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Distributionsfaser: förbereda, konfigurera, registrera](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="6c631-124">Fas</span><span class="sxs-lookup"><span data-stu-id="6c631-124">Phase</span></span> | <span data-ttu-id="6c631-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c631-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="6c631-126">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="6c631-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="6c631-127">Lär dig vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett testlabb eller pilotmiljö:</span><span class="sxs-lookup"><span data-stu-id="6c631-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="6c631-128">- Intressenter och av inloggning</span><span class="sxs-lookup"><span data-stu-id="6c631-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6c631-129">- Att tänka på när det gäller miljön</span><span class="sxs-lookup"><span data-stu-id="6c631-129">- Environment considerations</span></span> <br><span data-ttu-id="6c631-130">- Access</span><span class="sxs-lookup"><span data-stu-id="6c631-130">- Access</span></span> <br><span data-ttu-id="6c631-131">- Azure Active Directory konfiguration</span><span class="sxs-lookup"><span data-stu-id="6c631-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6c631-132">- Konfigurationsordning</span><span class="sxs-lookup"><span data-stu-id="6c631-132">- Configuration order</span></span>
|[<span data-ttu-id="6c631-133">Fas 2: Installation</span><span class="sxs-lookup"><span data-stu-id="6c631-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="6c631-134">Ta de första stegen för att komma Microsoft 365 Säkerhetscenter för att konfigurera testlabb eller pilotmiljö Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6c631-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="6c631-135">Du vägleds till:</span><span class="sxs-lookup"><span data-stu-id="6c631-135">You'll be guided to:</span></span><br><br><span data-ttu-id="6c631-136">- Registrera dig för Microsoft 365 E5 utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="6c631-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6c631-137">- Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="6c631-137">- Configure domain</span></span><br><span data-ttu-id="6c631-138">- Tilldela Microsoft 365 E5 licenser</span><span class="sxs-lookup"><span data-stu-id="6c631-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6c631-139">- Slutför installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="6c631-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="6c631-140">Fas 3: Konfigurera & onboard</span><span class="sxs-lookup"><span data-stu-id="6c631-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="6c631-141">Konfigurera varje Microsoft 365 Defender-klient och slutpunkter för onboard.</span><span class="sxs-lookup"><span data-stu-id="6c631-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="6c631-142">Du vägleds till:</span><span class="sxs-lookup"><span data-stu-id="6c631-142">You'll be guided to:</span></span><br><br><span data-ttu-id="6c631-143">- Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6c631-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="6c631-144">- Konfigurera Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6c631-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6c631-145">- Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="6c631-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="6c631-146">- Konfigurera Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6c631-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="6c631-147">När du har slutfört den här guiden skulle du ha identifierat de berörda intressenterna och de godkännanden som krävs, ha rätt åtkomstbehörighet, registrerat dig för utvärderingsversion, konfigurerade domäner och var och en av Microsoft 365 Defender-pelarna, och slutpunkterna kommer att introduceras till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6c631-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="6c631-148">Viktiga funktioner</span><span class="sxs-lookup"><span data-stu-id="6c631-148">Key capabilities</span></span>

<span data-ttu-id="6c631-149">Även Microsoft 365 Defender har många funktioner är det primära syftet med den här distributionsguiden att komma igång med att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="6c631-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="6c631-150">Förutom introduktionen får du i den här vägledningen även hjälp att komma igång med följande funktioner.</span><span class="sxs-lookup"><span data-stu-id="6c631-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="6c631-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="6c631-151">Capability</span></span> | <span data-ttu-id="6c631-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c631-152">Description</span></span> 
:---|:---
<span data-ttu-id="6c631-153">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6c631-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="6c631-154">Hjälper till att Office 365 hela ditt liv mot dagens hot</span><span class="sxs-lookup"><span data-stu-id="6c631-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="6c631-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6c631-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="6c631-156">Identifierar och identifierar hot på komprometterade identiteter och skadliga Insider-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6c631-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="6c631-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6c631-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="6c631-158">Ger full insyn, styr dataresa och känner av cyberhot i molntjänster.</span><span class="sxs-lookup"><span data-stu-id="6c631-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="6c631-159">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c631-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="6c631-160">Förhindrar, identifierar och tillhandahåller svarsfunktioner för avancerade hot med omfattande slutpunktssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="6c631-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="6c631-161">I omfattning</span><span class="sxs-lookup"><span data-stu-id="6c631-161">In scope</span></span>

<span data-ttu-id="6c631-162">Följande uppgifter omfattas av den här guiden:</span><span class="sxs-lookup"><span data-stu-id="6c631-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="6c631-163">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c631-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6c631-164">Konfigurera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c631-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="6c631-165">Registrera dig för Microsoft 365 E5 eller använd din fullständiga licens om du kör ett pilottest</span><span class="sxs-lookup"><span data-stu-id="6c631-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="6c631-166">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="6c631-166">Configure domain</span></span>
    -   <span data-ttu-id="6c631-167">Tilldela Microsoft 365 E5 licenser</span><span class="sxs-lookup"><span data-stu-id="6c631-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6c631-168">Slutföra installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="6c631-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6c631-169">Konfigurera alla Microsoft 365 Defender-pelarna baserat på metodtips</span><span class="sxs-lookup"><span data-stu-id="6c631-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="6c631-170">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6c631-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="6c631-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6c631-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="6c631-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6c631-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6c631-173">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c631-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6c631-174">Inte begränsad</span><span class="sxs-lookup"><span data-stu-id="6c631-174">Out of scope</span></span>

<span data-ttu-id="6c631-175">Följande ingår inte i den här distributionsguiden:</span><span class="sxs-lookup"><span data-stu-id="6c631-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6c631-176">Konfiguration av tredjepartslösningar som kan integreras med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c631-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="6c631-177">Test av test vid test i produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="6c631-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6c631-178">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6c631-178">Next step</span></span>
<span data-ttu-id="6c631-179">[Fas 1: Förbereda](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="6c631-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="6c631-180">Förbereda din Microsoft 365 Defender-testlabb eller pilotmiljö</span><span class="sxs-lookup"><span data-stu-id="6c631-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
