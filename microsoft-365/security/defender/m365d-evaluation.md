---
title: Microsoft 365 Defender
description: Konfigurera utvärderingslabb eller pilotmiljö i Microsoft 365 Defender för att prova och uppleva den säkerhetslösning som utformats för att skydda enheter, identitet, data och program i organisationen.
keywords: Utvärderingsversion av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection utvärderingslabb, Microsoft Threat Protection pilot, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enhet, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
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
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076657"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="bfde2-104">Skapa en testlabb- eller pilotmiljö med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bfde2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bfde2-105">**Applies to:**</span></span>
- <span data-ttu-id="bfde2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="bfde2-107">Den här guiden hjälper dig att arbeta i en labbmiljö med användare och grupper och hjälper dig sedan genom konfigurationen av funktionerna i Microsoft 365 Defender så att du kan efterlikna en hotattack och få ett meningsfullt utvärderingsresultat.</span><span class="sxs-lookup"><span data-stu-id="bfde2-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="bfde2-108">Syftet med att skapa den här testlabb- eller pilotmiljön är att illustrera de omfattande och integrerade Funktionerna i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bfde2-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="bfde2-109">Upplev hur den här intelligenta säkerhetslösningen identifierar, förhindrar, automatiskt undersöker och svarar på avancerade hot som din organisation använder.</span><span class="sxs-lookup"><span data-stu-id="bfde2-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="bfde2-110">Du vägleds genom stegen för att starta din utvärdering av Microsoft 365 Defender baserat på de rekommenderade distributionssökvägarna.</span><span class="sxs-lookup"><span data-stu-id="bfde2-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="bfde2-111">Målet är att hjälpa dig att konfigurera säkerhetslösningen i en labmiljö med ett testkonto eller i en pilotmiljö i produktion med en fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="bfde2-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="bfde2-112">Förberedelse av utvärderingslabb eller pilotmiljö kan hjälpa dig att presentera säkerhetsåtgärdsanvändningsfall för beslutsfattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bfde2-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="bfde2-113">När du har kört attack simuleringar och är nöjd med resultatet kan du helt distribuera och driftsätta det i organisationen med hjälp av Microsofts tekniska försäljare eller experter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bfde2-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="bfde2-114">I den här guiden får du hjälp med att:</span><span class="sxs-lookup"><span data-stu-id="bfde2-114">This guide will help you:</span></span>
- <span data-ttu-id="bfde2-115">Konfigurera din labserver och dina datorer</span><span class="sxs-lookup"><span data-stu-id="bfde2-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="bfde2-116">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="bfde2-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="bfde2-117">Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bfde2-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="bfde2-118">Konfigurera lokala principer för server och datorer</span><span class="sxs-lookup"><span data-stu-id="bfde2-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="bfde2-119">Imitera en hotattack för att generera en testhändelse eller avisering i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="bfde2-120">För bästa resultat följer du labinstallationsanvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="bfde2-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="bfde2-121">Distributionsfaser</span><span class="sxs-lookup"><span data-stu-id="bfde2-121">Deployment phases</span></span>

<span data-ttu-id="bfde2-122">Det finns tre faser i att skapa en testlabbmiljö med Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bfde2-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Distributionsfaser: förbereda, konfigurera, registrera](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="bfde2-124">Fas</span><span class="sxs-lookup"><span data-stu-id="bfde2-124">Phase</span></span> | <span data-ttu-id="bfde2-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bfde2-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="bfde2-126">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="bfde2-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="bfde2-127">Lär dig vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett testlabb eller pilotmiljö:</span><span class="sxs-lookup"><span data-stu-id="bfde2-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="bfde2-128">- Intressenter och av inloggning</span><span class="sxs-lookup"><span data-stu-id="bfde2-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="bfde2-129">- Att tänka på när det gäller miljön</span><span class="sxs-lookup"><span data-stu-id="bfde2-129">- Environment considerations</span></span> <br><span data-ttu-id="bfde2-130">- Access</span><span class="sxs-lookup"><span data-stu-id="bfde2-130">- Access</span></span> <br><span data-ttu-id="bfde2-131">- Azure Active Directory-konfiguration</span><span class="sxs-lookup"><span data-stu-id="bfde2-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="bfde2-132">- Konfigurationsordning</span><span class="sxs-lookup"><span data-stu-id="bfde2-132">- Configuration order</span></span>
|[<span data-ttu-id="bfde2-133">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="bfde2-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="bfde2-134">Ta de första stegen för att få åtkomst till Säkerhetscenter för Microsoft 365 för att konfigurera utvärderingslabb eller pilotmiljö för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bfde2-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="bfde2-135">Du vägleds till:</span><span class="sxs-lookup"><span data-stu-id="bfde2-135">You'll be guided to:</span></span><br><br><span data-ttu-id="bfde2-136">- Registrera dig för utvärderingsversionen av Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bfde2-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="bfde2-137">- Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="bfde2-137">- Configure domain</span></span><br><span data-ttu-id="bfde2-138">- Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="bfde2-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="bfde2-139">- Slutför installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="bfde2-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="bfde2-140">Fas 3: Konfigurera & onboard</span><span class="sxs-lookup"><span data-stu-id="bfde2-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="bfde2-141">Konfigurera varje Microsoft 365 Defender-klient och slutpunkter för onboard.</span><span class="sxs-lookup"><span data-stu-id="bfde2-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="bfde2-142">Du vägleds till:</span><span class="sxs-lookup"><span data-stu-id="bfde2-142">You'll be guided to:</span></span><br><br><span data-ttu-id="bfde2-143">- Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="bfde2-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="bfde2-144">- Konfigurera Microsoft Cloud App-säkerhet</span><span class="sxs-lookup"><span data-stu-id="bfde2-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="bfde2-145">- Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="bfde2-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="bfde2-146">- Konfigurera Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="bfde2-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="bfde2-147">När du har slutfört den här guiden skulle du ha identifierat de berörda intressenterna och de godkännanden som krävs, ha rätt åtkomstbehörighet, registrerat dig för utvärderingsversion, konfigurerade domäner och var och en av Microsoft 365 Defender-pelarna, och slutpunkterna kommer att introduceras till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="bfde2-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="bfde2-148">Viktiga funktioner</span><span class="sxs-lookup"><span data-stu-id="bfde2-148">Key capabilities</span></span>

<span data-ttu-id="bfde2-149">Microsoft 365 Defender har många funktioner, men det primära syftet med den här distributionsguiden är att komma igång med att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="bfde2-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="bfde2-150">Förutom introduktionen får du i den här vägledningen även hjälp att komma igång med följande funktioner.</span><span class="sxs-lookup"><span data-stu-id="bfde2-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="bfde2-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="bfde2-151">Capability</span></span> | <span data-ttu-id="bfde2-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bfde2-152">Description</span></span> 
:---|:---
<span data-ttu-id="bfde2-153">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="bfde2-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="bfde2-154">Hjälper dig att skydda hela Office 365-livningen mot dagens hot</span><span class="sxs-lookup"><span data-stu-id="bfde2-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="bfde2-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bfde2-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="bfde2-156">Identifierar och identifierar hot på komprometterade identiteter och skadliga Insider-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bfde2-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="bfde2-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bfde2-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="bfde2-158">Ger full insyn, styr dataresa och känner av cyberhot i molntjänster.</span><span class="sxs-lookup"><span data-stu-id="bfde2-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="bfde2-159">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bfde2-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="bfde2-160">Förhindrar, identifierar och tillhandahåller svarsfunktioner för avancerade hot med omfattande slutpunktssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="bfde2-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="bfde2-161">I omfattning</span><span class="sxs-lookup"><span data-stu-id="bfde2-161">In scope</span></span>

<span data-ttu-id="bfde2-162">Följande uppgifter omfattas av den här guiden:</span><span class="sxs-lookup"><span data-stu-id="bfde2-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="bfde2-163">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bfde2-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="bfde2-164">Konfigurera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="bfde2-165">Registrera dig för utvärderingsversionen av Microsoft 365 E5 eller använd din fullständiga licens om du kör en pilotversion</span><span class="sxs-lookup"><span data-stu-id="bfde2-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="bfde2-166">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="bfde2-166">Configure domain</span></span>
    -   <span data-ttu-id="bfde2-167">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="bfde2-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="bfde2-168">Slutföra installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="bfde2-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="bfde2-169">Konfigurera alla Microsoft 365 Defender-pelarpelare baserat på metodtips</span><span class="sxs-lookup"><span data-stu-id="bfde2-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="bfde2-170">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="bfde2-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="bfde2-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bfde2-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="bfde2-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bfde2-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="bfde2-173">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bfde2-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="bfde2-174">Inte begränsad</span><span class="sxs-lookup"><span data-stu-id="bfde2-174">Out of scope</span></span>

<span data-ttu-id="bfde2-175">Följande ingår inte i den här distributionsguiden:</span><span class="sxs-lookup"><span data-stu-id="bfde2-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="bfde2-176">Konfiguration av tredjepartslösningar som kan integreras med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="bfde2-177">Test av test vid test i produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="bfde2-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="bfde2-178">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bfde2-178">Next step</span></span>
<span data-ttu-id="bfde2-179">[Fas 1: Förbereda](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="bfde2-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="bfde2-180">Förbereda utvärderingslabb eller pilotmiljö med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfde2-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
