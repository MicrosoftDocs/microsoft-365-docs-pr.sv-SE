---
title: Utvärdera Microsoft 365 Defender
description: Ställ in utvärderings labb eller pilot miljö för Microsoft 365 Defender för att pröva och upplev säkerhets lösningen för att skydda enheter, identiteter, data och program i organisationen.
keywords: Utvärderings version av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection pilot, cyberterrorism Security, Avancerat, beständigt hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, händelser, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659646"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="7513d-104">Skapa en test labb-eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7513d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7513d-105">**Applies to:**</span></span>
- <span data-ttu-id="7513d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="7513d-107">Med den här guiden får du hjälp att arbeta i en labb miljö med användare och grupper och vägleder dig genom konfigureringen av funktionerna i Microsoft 365 Defender så att du kan efterlikna en hotet-attack och få ett meningsfullt prov.</span><span class="sxs-lookup"><span data-stu-id="7513d-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="7513d-108">Syftet med att skapa test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="7513d-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="7513d-109">Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har.</span><span class="sxs-lookup"><span data-stu-id="7513d-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="7513d-110">Du vägleds genom stegen för att starta utvärderings versionen av Microsoft 365 Defender baserat på de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="7513d-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="7513d-111">Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="7513d-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="7513d-112">Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7513d-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="7513d-113">När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7513d-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="7513d-114">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="7513d-114">This guide will help you:</span></span>
- <span data-ttu-id="7513d-115">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="7513d-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="7513d-116">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="7513d-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="7513d-117">Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slut punkt och säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="7513d-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="7513d-118">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="7513d-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="7513d-119">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="7513d-120">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7513d-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="7513d-121">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="7513d-121">Deployment phases</span></span>

<span data-ttu-id="7513d-122">Det finns tre faser i att skapa en test laboratorie miljö för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7513d-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Distributions faser: förbereda, konfigurera, inbyggt](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="7513d-124">Fas</span><span class="sxs-lookup"><span data-stu-id="7513d-124">Phase</span></span> | <span data-ttu-id="7513d-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7513d-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="7513d-126">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="7513d-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="7513d-127">Läs om vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett prov labb eller en pilot miljö:</span><span class="sxs-lookup"><span data-stu-id="7513d-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="7513d-128">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="7513d-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="7513d-129">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="7513d-129">- Environment considerations</span></span> <br><span data-ttu-id="7513d-130">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="7513d-130">- Access</span></span> <br><span data-ttu-id="7513d-131">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7513d-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="7513d-132">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="7513d-132">- Configuration order</span></span>
|[<span data-ttu-id="7513d-133">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="7513d-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="7513d-134">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb för Microsoft 365 Defender eller pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="7513d-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="7513d-135">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="7513d-135">You'll be guided to:</span></span><br><br><span data-ttu-id="7513d-136">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="7513d-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="7513d-137">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="7513d-137">- Configure domain</span></span><br><span data-ttu-id="7513d-138">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="7513d-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="7513d-139">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="7513d-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="7513d-140">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="7513d-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="7513d-141">Konfigurera varje slut punkter för Microsoft 365 Defender pelare och inbyggda.</span><span class="sxs-lookup"><span data-stu-id="7513d-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="7513d-142">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="7513d-142">You'll be guided to:</span></span><br><br><span data-ttu-id="7513d-143">-Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7513d-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="7513d-144">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="7513d-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="7513d-145">-Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="7513d-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="7513d-146">-Konfigurera Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="7513d-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="7513d-147">När du har fyllt i den här guiden hade du identifierat berörda intressenter och godkännanden, som krävs för att få rätt åtkomst behörighet, registrerat dig för utvärderings versionen, konfigurerade domäner och alla Microsoft 365 Defender-träd och dina slut punkter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7513d-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="7513d-148">Viktiga funktioner</span><span class="sxs-lookup"><span data-stu-id="7513d-148">Key capabilities</span></span>

<span data-ttu-id="7513d-149">Även om Microsoft 365 Defender tillhandahåller många funktioner är det primära syftet med den här distributions guiden att komma igång med att starta enheter.</span><span class="sxs-lookup"><span data-stu-id="7513d-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="7513d-150">Förutom att börja använda den här vägledningen får du följande funktioner.</span><span class="sxs-lookup"><span data-stu-id="7513d-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="7513d-151">Funktion</span><span class="sxs-lookup"><span data-stu-id="7513d-151">Capability</span></span> | <span data-ttu-id="7513d-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7513d-152">Description</span></span> 
:---|:---
<span data-ttu-id="7513d-153">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7513d-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7513d-154">Skyddar hela din Office 365-envrionment från dagens hot</span><span class="sxs-lookup"><span data-stu-id="7513d-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="7513d-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7513d-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7513d-156">Identifierar och identifierar hot om komprometterade identiteter och skadliga Insider-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7513d-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="7513d-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7513d-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="7513d-158">Ger omfattande synlighet, styr data resor och upptäck Cyberthreats i moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="7513d-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="7513d-159">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7513d-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="7513d-160">Skyddar, identifierar och ger svar på avancerade hot med omfattande slut punkts säkerhet.</span><span class="sxs-lookup"><span data-stu-id="7513d-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="7513d-161">I omfattning</span><span class="sxs-lookup"><span data-stu-id="7513d-161">In scope</span></span>

<span data-ttu-id="7513d-162">Följande aktiviteter är omfång för den här guiden:</span><span class="sxs-lookup"><span data-stu-id="7513d-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="7513d-163">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7513d-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="7513d-164">Konfigurera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="7513d-165">Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot</span><span class="sxs-lookup"><span data-stu-id="7513d-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="7513d-166">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="7513d-166">Configure domain</span></span>
    -   <span data-ttu-id="7513d-167">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="7513d-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="7513d-168">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="7513d-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="7513d-169">Konfigurera alla Microsoft 365 Defender-pelare baserat på metod tips</span><span class="sxs-lookup"><span data-stu-id="7513d-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="7513d-170">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7513d-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="7513d-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7513d-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="7513d-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7513d-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="7513d-173">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7513d-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="7513d-174">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="7513d-174">Out of scope</span></span>

<span data-ttu-id="7513d-175">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="7513d-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="7513d-176">Konfiguration av lösningar från tredje part som kan integreras med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="7513d-177">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="7513d-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="7513d-178">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7513d-178">Next step</span></span>
<span data-ttu-id="7513d-179">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="7513d-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="7513d-180">Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7513d-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
