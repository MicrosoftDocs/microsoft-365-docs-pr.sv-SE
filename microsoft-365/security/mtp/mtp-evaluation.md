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
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846490"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="a5bd0-104">Skapa en test labb-eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5bd0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5bd0-105">**Applies to:**</span></span>
- <span data-ttu-id="a5bd0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a5bd0-107">Syftet med att skapa test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="a5bd0-108">Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="a5bd0-109">Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft 365 Defender baserat på de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="a5bd0-110">Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="a5bd0-111">Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="a5bd0-112">När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="a5bd0-113">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-113">This guide will help you:</span></span>
- <span data-ttu-id="a5bd0-114">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="a5bd0-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="a5bd0-115">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="a5bd0-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="a5bd0-116">Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slut punkt och säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="a5bd0-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a5bd0-117">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="a5bd0-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="a5bd0-118">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="a5bd0-119">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="a5bd0-120">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="a5bd0-120">Deployment phases</span></span>

<span data-ttu-id="a5bd0-121">Det finns tre faser i att skapa en test labbs miljö för Microsoft 365 Defender och distribuera den:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="a5bd0-122">Fas</span><span class="sxs-lookup"><span data-stu-id="a5bd0-122">Phase</span></span> | <span data-ttu-id="a5bd0-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5bd0-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="a5bd0-124">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a5bd0-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="a5bd0-125">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="a5bd0-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="a5bd0-126">Läs om vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett prov labb eller en pilot miljö:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="a5bd0-127">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="a5bd0-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="a5bd0-128">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="a5bd0-128">- Environment considerations</span></span> <br><span data-ttu-id="a5bd0-129">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="a5bd0-129">- Access</span></span> <br><span data-ttu-id="a5bd0-130">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a5bd0-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="a5bd0-131">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="a5bd0-131">- Configuration order</span></span>
|  <span data-ttu-id="a5bd0-132">![Fas 2: konfiguration](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="a5bd0-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="a5bd0-133">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="a5bd0-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="a5bd0-134">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb för Microsoft 365 Defender eller pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="a5bd0-135">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-135">You'll be guided to:</span></span><br><br><span data-ttu-id="a5bd0-136">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="a5bd0-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="a5bd0-137">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="a5bd0-137">- Configure domain</span></span><br><span data-ttu-id="a5bd0-138">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="a5bd0-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="a5bd0-139">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="a5bd0-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="a5bd0-140">![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="a5bd0-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="a5bd0-141">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="a5bd0-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="a5bd0-142">Konfigurera varje slut punkter för Microsoft 365 Defender pelare och inbyggda.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="a5bd0-143">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-143">You'll be guided to:</span></span><br><br><span data-ttu-id="a5bd0-144">-Konfigurera Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="a5bd0-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="a5bd0-145">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="a5bd0-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="a5bd0-146">-Konfigurera Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="a5bd0-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="a5bd0-147">-Konfigurera Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="a5bd0-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="a5bd0-148">I omfattning</span><span class="sxs-lookup"><span data-stu-id="a5bd0-148">In scope</span></span>

<span data-ttu-id="a5bd0-149">Följande aktiviteter är omfång för den här guiden:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="a5bd0-150">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a5bd0-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="a5bd0-151">Konfigurera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="a5bd0-152">Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot</span><span class="sxs-lookup"><span data-stu-id="a5bd0-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="a5bd0-153">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="a5bd0-153">Configure domain</span></span>
    -   <span data-ttu-id="a5bd0-154">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="a5bd0-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="a5bd0-155">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="a5bd0-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="a5bd0-156">Konfigurera alla Microsoft 365 Defender-pelare baserat på metod tips</span><span class="sxs-lookup"><span data-stu-id="a5bd0-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="a5bd0-157">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="a5bd0-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="a5bd0-158">Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="a5bd0-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="a5bd0-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a5bd0-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="a5bd0-160">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="a5bd0-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="a5bd0-161">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="a5bd0-161">Out of scope</span></span>

<span data-ttu-id="a5bd0-162">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="a5bd0-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="a5bd0-163">Konfiguration av lösningar från tredje part som kan integreras med Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="a5bd0-164">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="a5bd0-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="a5bd0-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a5bd0-165">Next step</span></span>
<span data-ttu-id="a5bd0-166">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a5bd0-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="a5bd0-167">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="a5bd0-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="a5bd0-168">Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5bd0-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
