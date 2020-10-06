---
title: Utvärdera Microsoft Hotskydd
description: Ställ in ett utvärderings labb för Microsoft Threat-skydd eller pilot miljö för att testa hur den koordinerade hotets skydds lösningen som är avsedd att skydda enheter, identiteter, data och program kan hjälpa din organisation
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368065"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="b8338-104">Skapa ett test labb eller pilot miljö för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8338-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8338-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b8338-105">**Applies to:**</span></span>
- <span data-ttu-id="b8338-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8338-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b8338-107">Syftet med att skapa utvärderings laboratoriet eller pilot miljön är att illustrera de omfattande, integrerade och intelligenta funktionerna i Microsoft Threat Protection i identifiering, förebyggande åtgärder och svar som du kan använda i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b8338-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="b8338-108">Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft Threat med de rekommenderade distributions vägarna.</span><span class="sxs-lookup"><span data-stu-id="b8338-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b8338-109">Målet är att hjälpa dig att konfigurera den integrerade hot skydds tjänsten i en labb miljö när du använder ett utvärderings konto eller i en pilot miljö i produktionen när du använder en fullständig licens.</span><span class="sxs-lookup"><span data-stu-id="b8338-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="b8338-110">Vilka resultat som kommer att vara användbara när det gäller säkerhets åtgärds användnings fall för besluts fattarna om säkerhets lösning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b8338-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="b8338-111">När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b8338-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b8338-112">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="b8338-112">This guide will help you:</span></span>
- <span data-ttu-id="b8338-113">Konfigurera labb Server och datorer</span><span class="sxs-lookup"><span data-stu-id="b8338-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="b8338-114">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="b8338-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b8338-115">Konfigurera och konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b8338-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b8338-116">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="b8338-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="b8338-117">Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8338-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="b8338-118">Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="b8338-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b8338-119">Distributions faser</span><span class="sxs-lookup"><span data-stu-id="b8338-119">Deployment phases</span></span>

<span data-ttu-id="b8338-120">Det finns tre faser i att skapa en test laboratorie miljö för Microsoft Threat Protection och distribuera det:</span><span class="sxs-lookup"><span data-stu-id="b8338-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="b8338-121">Fas</span><span class="sxs-lookup"><span data-stu-id="b8338-121">Phase</span></span> | <span data-ttu-id="b8338-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b8338-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b8338-123">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b8338-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="b8338-124">Fas 1: förbereda</span><span class="sxs-lookup"><span data-stu-id="b8338-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b8338-125">Lär dig vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en utvärderings labb-eller pilot miljö:</span><span class="sxs-lookup"><span data-stu-id="b8338-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="b8338-126">-Intressenter och utloggning</span><span class="sxs-lookup"><span data-stu-id="b8338-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b8338-127">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="b8338-127">- Environment considerations</span></span> <br><span data-ttu-id="b8338-128">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="b8338-128">- Access</span></span> <br><span data-ttu-id="b8338-129">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8338-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b8338-130">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="b8338-130">- Configuration order</span></span>
|  <span data-ttu-id="b8338-131">![Fas 2: konfiguration](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b8338-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b8338-132">Fas 2: konfiguration</span><span class="sxs-lookup"><span data-stu-id="b8338-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b8338-133">Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera ett test labb för Microsoft Threat Protection eller pilot miljö.</span><span class="sxs-lookup"><span data-stu-id="b8338-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="b8338-134">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="b8338-134">You'll be guided to:</span></span><br><br><span data-ttu-id="b8338-135">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="b8338-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b8338-136">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="b8338-136">- Configure domain</span></span><br><span data-ttu-id="b8338-137">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="b8338-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b8338-138">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="b8338-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="b8338-139">![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b8338-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b8338-140">Steg 3: Konfigurera & inbyggt</span><span class="sxs-lookup"><span data-stu-id="b8338-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b8338-141">Konfigurera varje slut punkter för skydd mot Microsoft Threat-och-inbyggt.</span><span class="sxs-lookup"><span data-stu-id="b8338-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="b8338-142">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="b8338-142">You'll be guided to:</span></span><br><br><span data-ttu-id="b8338-143">-Konfigurera Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b8338-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="b8338-144">-Konfigurera säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="b8338-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b8338-145">-Konfigurera Avancerat skydd för Azure</span><span class="sxs-lookup"><span data-stu-id="b8338-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="b8338-146">-Konfigurera Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b8338-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="b8338-147">I omfattning</span><span class="sxs-lookup"><span data-stu-id="b8338-147">In scope</span></span>

<span data-ttu-id="b8338-148">Följande aktiviteter är omfång för den här guiden:</span><span class="sxs-lookup"><span data-stu-id="b8338-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="b8338-149">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8338-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b8338-150">Konfigurera skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="b8338-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="b8338-151">Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot</span><span class="sxs-lookup"><span data-stu-id="b8338-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="b8338-152">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="b8338-152">Configure domain</span></span>
    -   <span data-ttu-id="b8338-153">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="b8338-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b8338-154">Slutföra installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="b8338-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b8338-155">Konfigurera alla Microsoft Threat Protection-pelare baserat på bästa praxis</span><span class="sxs-lookup"><span data-stu-id="b8338-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="b8338-156">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b8338-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b8338-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8338-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b8338-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b8338-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b8338-159">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b8338-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b8338-160">Utanför omfattning</span><span class="sxs-lookup"><span data-stu-id="b8338-160">Out of scope</span></span>

<span data-ttu-id="b8338-161">Den här distributions guiden följer inte med:</span><span class="sxs-lookup"><span data-stu-id="b8338-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b8338-162">Konfiguration av lösningar från tredje part som kan integreras med Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8338-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="b8338-163">Test av inträngda i produktions miljön</span><span class="sxs-lookup"><span data-stu-id="b8338-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b8338-164">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b8338-164">Next step</span></span>
<span data-ttu-id="b8338-165">![Fas 1: förbereda](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b8338-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="b8338-166">[Fas 1: förbereda](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="b8338-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="b8338-167">Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö</span><span class="sxs-lookup"><span data-stu-id="b8338-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
