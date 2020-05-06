---
title: Utvärdera Microsofts hotskydd
description: Konfigurera testlabbetamiljön för Microsoft Threat Protection för att prova hur den samordnade hotskyddslösningen som utformats för att skydda enheter, identitet, data och program kan hjälpa din organisation
keywords: Microsoft Threat Protection rättegång, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection utvärdering lab, cybersäkerhet, avancerade ihållande hot, företagssäkerhet, enheter, enhet, identitet, användare, data, applikationer, incidenter, automatiserad undersökning och reparation, avancerad jakt
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049645"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="41cca-104">Skapa en testlabbmiljö för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41cca-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="41cca-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="41cca-105">**Applies to:**</span></span>
- <span data-ttu-id="41cca-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="41cca-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="41cca-107">Syftet med att skapa den här testlabbetsmiljön är att illustrera de omfattande, integrerade och intelligenta funktionerna i Microsoft Threat Protection i identifiering, förebyggande, undersökning och svar som du kan använda i din organisation.</span><span class="sxs-lookup"><span data-stu-id="41cca-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="41cca-108">Den här guiden tar dig igenom stegen för att starta microsoft threat protection-utvärderingen baserat på de rekommenderade distributionsvägarna.</span><span class="sxs-lookup"><span data-stu-id="41cca-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="41cca-109">Målet är att hjälpa dig att konfigurera integrerade Microsoft Threat Protection-tjänster i en labbmiljö eller som ett proof of concept (POC) när du presenterar för beslutsfattare för säkerhetslösningar i din organisation.</span><span class="sxs-lookup"><span data-stu-id="41cca-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="41cca-110">När du är klar med att köra dina attacksimuleringar, automatisk undersökning och svar och är nöjda med resultaten kan du distribuera den i din produktionsmiljö med hjälp av Microsoft Technical Sales Professionals eller experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="41cca-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="41cca-111">Den här guiden hjälper dig:</span><span class="sxs-lookup"><span data-stu-id="41cca-111">This guide will help you:</span></span>
- <span data-ttu-id="41cca-112">Konfigurera labbservern och datorerna</span><span class="sxs-lookup"><span data-stu-id="41cca-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="41cca-113">Konfigurera Active Directory med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="41cca-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="41cca-114">Konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41cca-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="41cca-115">Konfigurera lokala principer för servern och datorerna</span><span class="sxs-lookup"><span data-stu-id="41cca-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="41cca-116">Härma en hotattack för att generera en testincident eller en varning i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41cca-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="41cca-117">För bästa resultat, följ instruktionerna för labbinställningar så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="41cca-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="41cca-118">Distributionsfaser</span><span class="sxs-lookup"><span data-stu-id="41cca-118">Deployment phases</span></span>

<span data-ttu-id="41cca-119">Det finns tre faser i att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den:</span><span class="sxs-lookup"><span data-stu-id="41cca-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="41cca-120">Fas</span><span class="sxs-lookup"><span data-stu-id="41cca-120">Phase</span></span> | <span data-ttu-id="41cca-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="41cca-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="41cca-122">![Fas 1: Förbered](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="41cca-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="41cca-123">Fas 1: Förbered</span><span class="sxs-lookup"><span data-stu-id="41cca-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="41cca-124">Läs om vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en testlabbetamiljö:</span><span class="sxs-lookup"><span data-stu-id="41cca-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="41cca-125">- Intressenter och signering</span><span class="sxs-lookup"><span data-stu-id="41cca-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="41cca-126">- Miljöhänsyn</span><span class="sxs-lookup"><span data-stu-id="41cca-126">- Environment considerations</span></span> <br><span data-ttu-id="41cca-127">- Tillgång</span><span class="sxs-lookup"><span data-stu-id="41cca-127">- Access</span></span> <br><span data-ttu-id="41cca-128">- Azure Active Directory-konfiguration</span><span class="sxs-lookup"><span data-stu-id="41cca-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="41cca-129">- Konfigurationsordning</span><span class="sxs-lookup"><span data-stu-id="41cca-129">- Configuration order</span></span>
|  <span data-ttu-id="41cca-130">![Fas 2: Installation](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="41cca-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="41cca-131">Fas 2: Installation</span><span class="sxs-lookup"><span data-stu-id="41cca-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="41cca-132">Gör de första stegen för att komma åt Microsoft 365 Security Center för att konfigurera testlabbeta Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="41cca-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="41cca-133">Du kommer att guidas till:</span><span class="sxs-lookup"><span data-stu-id="41cca-133">You will be guided to:</span></span><br><br><span data-ttu-id="41cca-134">- Registrera dig för Testversionen av Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="41cca-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="41cca-135">- Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="41cca-135">- Configure domain</span></span><br><span data-ttu-id="41cca-136">- Tilldela Microsoft 365 E5 licenser</span><span class="sxs-lookup"><span data-stu-id="41cca-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="41cca-137">- Slutför installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="41cca-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="41cca-138">![Fas 3: Konfigurera & ombord](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="41cca-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="41cca-139">Fas 3: Konfigurera & ombord</span><span class="sxs-lookup"><span data-stu-id="41cca-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="41cca-140">Konfigurera varje Microsoft Threat Protection-pelare och inbyggda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="41cca-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="41cca-141">Du kommer att guidas till:</span><span class="sxs-lookup"><span data-stu-id="41cca-141">You will be guided to:</span></span><br><br><span data-ttu-id="41cca-142">- Konfigurera avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="41cca-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="41cca-143">- Konfigurera Säkerhet för Microsoft Cloud-appar</span><span class="sxs-lookup"><span data-stu-id="41cca-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="41cca-144">- Konfigurera Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41cca-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="41cca-145">- Konfigurera Microsoft Defender avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="41cca-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="41cca-146">I omfattning</span><span class="sxs-lookup"><span data-stu-id="41cca-146">In scope</span></span>

<span data-ttu-id="41cca-147">Följande är i omfattning för den här testlabbets miljöguide:</span><span class="sxs-lookup"><span data-stu-id="41cca-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="41cca-148">Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41cca-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="41cca-149">Konfigurera Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="41cca-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="41cca-150">Registrera dig för Testversionen av Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="41cca-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="41cca-151">Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="41cca-151">Configure domain</span></span>
    -   <span data-ttu-id="41cca-152">Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="41cca-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="41cca-153">Slutföra installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="41cca-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="41cca-154">Konfigurera alla Microsoft Threat Protection-pelare baserat på metodtips</span><span class="sxs-lookup"><span data-stu-id="41cca-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="41cca-155">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="41cca-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="41cca-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="41cca-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="41cca-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41cca-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="41cca-158">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="41cca-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="41cca-159">Utanför räckvidden</span><span class="sxs-lookup"><span data-stu-id="41cca-159">Out of scope</span></span>

<span data-ttu-id="41cca-160">Följande är utanför omfattningen av den här distributionsguiden:</span><span class="sxs-lookup"><span data-stu-id="41cca-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="41cca-161">Konfiguration av tredjepartslösningar som kan integreras med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="41cca-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="41cca-162">Penetrationstestning i produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="41cca-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="41cca-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="41cca-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="41cca-164">![Fas 1: Förbered](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="41cca-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="41cca-165">Fas 1: Förbered</span><span class="sxs-lookup"><span data-stu-id="41cca-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="41cca-166">Förbereda microsofts labbmiljö för utvärdering av hotskydd</span><span class="sxs-lookup"><span data-stu-id="41cca-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
