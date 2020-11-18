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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130886"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="93ba2-104">Skapa en test labb-eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93ba2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="93ba2-105">**Applies to:**</span></span>
- <span data-ttu-id="93ba2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="93ba2-107">Syftet med att skapa test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="93ba2-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="93ba2-108">Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har.</span><span class="sxs-lookup"><span data-stu-id="93ba2-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="93ba2-109">Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft 365 Defender baserat på de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="93ba2-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="93ba2-110">Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="93ba2-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="93ba2-111">Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93ba2-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="93ba2-112">När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="93ba2-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="93ba2-113">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="93ba2-113">This guide will help you:</span></span>
- <span data-ttu-id="93ba2-114">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="93ba2-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="93ba2-115">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="93ba2-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="93ba2-116">Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slut punkt och säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="93ba2-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="93ba2-117">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="93ba2-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="93ba2-118">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="93ba2-119">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="93ba2-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="93ba2-120">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="93ba2-120">Deployment phases</span></span>

<span data-ttu-id="93ba2-121">Det finns tre faser i att skapa en test labbs miljö för Microsoft 365 Defender och distribuera den:</span><span class="sxs-lookup"><span data-stu-id="93ba2-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Distributions faser: förbereda, konfigurera, inbyggt](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="93ba2-123">Fas</span><span class="sxs-lookup"><span data-stu-id="93ba2-123">Phase</span></span> | <span data-ttu-id="93ba2-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="93ba2-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="93ba2-125">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="93ba2-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="93ba2-126">Läs om vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett prov labb eller en pilot miljö:</span><span class="sxs-lookup"><span data-stu-id="93ba2-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="93ba2-127">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="93ba2-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="93ba2-128">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="93ba2-128">- Environment considerations</span></span> <br><span data-ttu-id="93ba2-129">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="93ba2-129">- Access</span></span> <br><span data-ttu-id="93ba2-130">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="93ba2-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="93ba2-131">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="93ba2-131">- Configuration order</span></span>
|[<span data-ttu-id="93ba2-132">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="93ba2-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="93ba2-133">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb för Microsoft 365 Defender eller pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="93ba2-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="93ba2-134">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="93ba2-134">You'll be guided to:</span></span><br><br><span data-ttu-id="93ba2-135">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="93ba2-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="93ba2-136">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="93ba2-136">- Configure domain</span></span><br><span data-ttu-id="93ba2-137">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="93ba2-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="93ba2-138">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="93ba2-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="93ba2-139">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="93ba2-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="93ba2-140">Konfigurera varje slut punkter för Microsoft 365 Defender pelare och inbyggda.</span><span class="sxs-lookup"><span data-stu-id="93ba2-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="93ba2-141">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="93ba2-141">You'll be guided to:</span></span><br><br><span data-ttu-id="93ba2-142">-Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="93ba2-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="93ba2-143">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="93ba2-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="93ba2-144">-Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="93ba2-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="93ba2-145">-Konfigurera Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="93ba2-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="93ba2-146">I omfattning</span><span class="sxs-lookup"><span data-stu-id="93ba2-146">In scope</span></span>

<span data-ttu-id="93ba2-147">Följande aktiviteter är omfång för den här guiden:</span><span class="sxs-lookup"><span data-stu-id="93ba2-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="93ba2-148">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="93ba2-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="93ba2-149">Konfigurera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="93ba2-150">Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot</span><span class="sxs-lookup"><span data-stu-id="93ba2-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="93ba2-151">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="93ba2-151">Configure domain</span></span>
    -   <span data-ttu-id="93ba2-152">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="93ba2-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="93ba2-153">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="93ba2-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="93ba2-154">Konfigurera alla Microsoft 365 Defender-pelare baserat på metod tips</span><span class="sxs-lookup"><span data-stu-id="93ba2-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="93ba2-155">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="93ba2-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="93ba2-156">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="93ba2-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="93ba2-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="93ba2-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="93ba2-158">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="93ba2-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="93ba2-159">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="93ba2-159">Out of scope</span></span>

<span data-ttu-id="93ba2-160">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="93ba2-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="93ba2-161">Konfiguration av lösningar från tredje part som kan integreras med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="93ba2-162">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="93ba2-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="93ba2-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="93ba2-163">Next step</span></span>
<span data-ttu-id="93ba2-164">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="93ba2-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="93ba2-165">Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ba2-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
