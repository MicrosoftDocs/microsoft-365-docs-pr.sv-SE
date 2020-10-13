---
title: Utvärdera Microsoft Hotskydd
description: Ställ in ett utvärderings labb för Microsoft Threat-skydd eller pilot miljö för att pröva och upplev säkerhets lösningen för att skydda enheter, identiteter, data och program i din organisation.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447125"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="c992c-104">Skapa ett test labb eller pilot miljö för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c992c-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c992c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c992c-105">**Applies to:**</span></span>
- <span data-ttu-id="c992c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c992c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c992c-107">Syftet med att skapa den här test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade hot Protection funktionerna i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c992c-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="c992c-108">Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har.</span><span class="sxs-lookup"><span data-stu-id="c992c-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="c992c-109">Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft Threat med de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="c992c-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c992c-110">Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="c992c-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="c992c-111">Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c992c-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="c992c-112">När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c992c-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c992c-113">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="c992c-113">This guide will help you:</span></span>
- <span data-ttu-id="c992c-114">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="c992c-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="c992c-115">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="c992c-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c992c-116">Konfigurera och konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c992c-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c992c-117">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="c992c-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c992c-118">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c992c-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="c992c-119">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="c992c-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c992c-120">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="c992c-120">Deployment phases</span></span>

<span data-ttu-id="c992c-121">Det finns tre faser i att skapa en test laboratorie miljö för Microsoft Threat Protection och distribuera det:</span><span class="sxs-lookup"><span data-stu-id="c992c-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="c992c-122">Fas</span><span class="sxs-lookup"><span data-stu-id="c992c-122">Phase</span></span> | <span data-ttu-id="c992c-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c992c-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="c992c-124">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c992c-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="c992c-125">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="c992c-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="c992c-126">Lär dig vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en utvärderings labb-eller pilot miljö:</span><span class="sxs-lookup"><span data-stu-id="c992c-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c992c-127">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="c992c-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c992c-128">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="c992c-128">- Environment considerations</span></span> <br><span data-ttu-id="c992c-129">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="c992c-129">- Access</span></span> <br><span data-ttu-id="c992c-130">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c992c-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c992c-131">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="c992c-131">- Configuration order</span></span>
|  <span data-ttu-id="c992c-132">![Fas 2: konfiguration](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="c992c-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="c992c-133">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="c992c-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="c992c-134">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera ett test labb för Microsoft Threat Protection eller pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="c992c-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="c992c-135">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="c992c-135">You'll be guided to:</span></span><br><br><span data-ttu-id="c992c-136">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="c992c-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c992c-137">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="c992c-137">- Configure domain</span></span><br><span data-ttu-id="c992c-138">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="c992c-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c992c-139">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="c992c-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="c992c-140">![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="c992c-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="c992c-141">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="c992c-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="c992c-142">Konfigurera varje slut punkter för skydd mot Microsoft Threat-och-inbyggt.</span><span class="sxs-lookup"><span data-stu-id="c992c-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="c992c-143">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="c992c-143">You'll be guided to:</span></span><br><br><span data-ttu-id="c992c-144">-Konfigurera Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c992c-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="c992c-145">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="c992c-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c992c-146">-Konfigurera Avancerat skydd för Azure</span><span class="sxs-lookup"><span data-stu-id="c992c-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="c992c-147">-Konfigurera Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c992c-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="c992c-148">I omfattning</span><span class="sxs-lookup"><span data-stu-id="c992c-148">In scope</span></span>

<span data-ttu-id="c992c-149">Följande aktiviteter är omfång för den här guiden:</span><span class="sxs-lookup"><span data-stu-id="c992c-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c992c-150">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c992c-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c992c-151">Konfigurera skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="c992c-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="c992c-152">Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot</span><span class="sxs-lookup"><span data-stu-id="c992c-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c992c-153">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="c992c-153">Configure domain</span></span>
    -   <span data-ttu-id="c992c-154">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="c992c-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c992c-155">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="c992c-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c992c-156">Konfigurera alla Microsoft Threat Protection-pelare baserat på bästa praxis</span><span class="sxs-lookup"><span data-stu-id="c992c-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="c992c-157">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c992c-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c992c-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c992c-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c992c-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c992c-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c992c-160">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c992c-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c992c-161">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="c992c-161">Out of scope</span></span>

<span data-ttu-id="c992c-162">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="c992c-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c992c-163">Konfiguration av lösningar från tredje part som kan integreras med Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c992c-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="c992c-164">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="c992c-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c992c-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c992c-165">Next step</span></span>
<span data-ttu-id="c992c-166">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c992c-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="c992c-167">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c992c-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="c992c-168">Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö</span><span class="sxs-lookup"><span data-stu-id="c992c-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
