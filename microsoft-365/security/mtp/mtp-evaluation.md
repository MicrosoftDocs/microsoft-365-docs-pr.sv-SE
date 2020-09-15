---
title: Utvärdera Microsoft Hotskydd
description: Ställ in din miljö för utvärderings labb för Microsoft Threat Protection för att testa hur den koordinerade hotets skydds lösningen som är avsedd att skydda enheter, identitet, data och program kan hjälpa din organisation
keywords: Utvärderings version av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, cyberterrorism Security, Avancerat hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649967"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="03ab9-104">Skapa en test laboratorie miljö för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="03ab9-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="03ab9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="03ab9-105">**Applies to:**</span></span>
- <span data-ttu-id="03ab9-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="03ab9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="03ab9-107">Syftet med att skapa den här test laboratorie miljön är att illustrera de omfattande, integrerade och smarta funktionerna i Microsoft Threat Protection i identifiering, förebyggande åtgärder och svar som du kan använda i din organisation.</span><span class="sxs-lookup"><span data-stu-id="03ab9-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="03ab9-108">Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft Threat med de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="03ab9-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="03ab9-109">Målet är att hjälpa dig att konfigurera de integrerade tjänsterna för Microsoft Threat Protection i en labb miljö eller som ett POC (proof of Concept) när du presenterar besluts fattarna hos säkerhets lösningen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="03ab9-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="03ab9-110">När du är klar med dina attacker, automatiserade undersökningar och svar och är nöjd med resultatet kan du distribuera det i produktions miljön med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="03ab9-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="03ab9-111">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="03ab9-111">This guide will help you:</span></span>
- <span data-ttu-id="03ab9-112">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="03ab9-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="03ab9-113">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="03ab9-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="03ab9-114">Konfigurera och konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="03ab9-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="03ab9-115">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="03ab9-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="03ab9-116">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="03ab9-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="03ab9-117">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="03ab9-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="03ab9-118">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="03ab9-118">Deployment phases</span></span>

<span data-ttu-id="03ab9-119">Det finns tre faser i att skapa en test laboratorie miljö för Microsoft Threat Protection och distribuera det:</span><span class="sxs-lookup"><span data-stu-id="03ab9-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="03ab9-120">Fas</span><span class="sxs-lookup"><span data-stu-id="03ab9-120">Phase</span></span> | <span data-ttu-id="03ab9-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="03ab9-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="03ab9-122">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="03ab9-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="03ab9-123">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="03ab9-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="03ab9-124">Lär dig vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en test laboratorie miljö:</span><span class="sxs-lookup"><span data-stu-id="03ab9-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="03ab9-125">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="03ab9-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="03ab9-126">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="03ab9-126">- Environment considerations</span></span> <br><span data-ttu-id="03ab9-127">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="03ab9-127">- Access</span></span> <br><span data-ttu-id="03ab9-128">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="03ab9-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="03ab9-129">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="03ab9-129">- Configuration order</span></span>
|  <span data-ttu-id="03ab9-130">![Fas 2: konfiguration](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="03ab9-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="03ab9-131">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="03ab9-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="03ab9-132">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb miljön för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="03ab9-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="03ab9-133">Du ska vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="03ab9-133">You will be guided to:</span></span><br><br><span data-ttu-id="03ab9-134">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="03ab9-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="03ab9-135">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="03ab9-135">- Configure domain</span></span><br><span data-ttu-id="03ab9-136">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="03ab9-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="03ab9-137">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="03ab9-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="03ab9-138">![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="03ab9-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="03ab9-139">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="03ab9-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="03ab9-140">Konfigurera varje slut punkter för skydd mot Microsoft Threat-och-inbyggt.</span><span class="sxs-lookup"><span data-stu-id="03ab9-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="03ab9-141">Du ska vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="03ab9-141">You will be guided to:</span></span><br><br><span data-ttu-id="03ab9-142">-Konfigurera Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="03ab9-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="03ab9-143">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="03ab9-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="03ab9-144">-Konfigurera Avancerat skydd för Azure</span><span class="sxs-lookup"><span data-stu-id="03ab9-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="03ab9-145">-Konfigurera Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="03ab9-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="03ab9-146">I omfattning</span><span class="sxs-lookup"><span data-stu-id="03ab9-146">In scope</span></span>

<span data-ttu-id="03ab9-147">Följande är i omfattning för utvärderings versionen av test laboratoriet:</span><span class="sxs-lookup"><span data-stu-id="03ab9-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="03ab9-148">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="03ab9-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="03ab9-149">Konfigurera skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="03ab9-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="03ab9-150">Registrera dig för Microsoft 365 E5-utvärderings versionen</span><span class="sxs-lookup"><span data-stu-id="03ab9-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="03ab9-151">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="03ab9-151">Configure domain</span></span>
    -   <span data-ttu-id="03ab9-152">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="03ab9-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="03ab9-153">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="03ab9-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="03ab9-154">Konfigurera alla Microsoft Threat Protection-pelare baserat på bästa praxis</span><span class="sxs-lookup"><span data-stu-id="03ab9-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="03ab9-155">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="03ab9-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="03ab9-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="03ab9-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="03ab9-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="03ab9-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="03ab9-158">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="03ab9-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="03ab9-159">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="03ab9-159">Out of scope</span></span>

<span data-ttu-id="03ab9-160">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="03ab9-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="03ab9-161">Konfiguration av lösningar från tredje part som kan integreras med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="03ab9-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="03ab9-162">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="03ab9-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="03ab9-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="03ab9-163">Next step</span></span>
<span data-ttu-id="03ab9-164">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="03ab9-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="03ab9-165">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="03ab9-165">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="03ab9-166">Förbereda en miljö för utvärderings labb för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="03ab9-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
