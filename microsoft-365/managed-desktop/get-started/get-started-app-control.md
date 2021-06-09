---
title: Kom igång med appens kontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430465"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="0f35e-103">Kom igång med appens kontroll</span><span class="sxs-lookup"><span data-stu-id="0f35e-103">Get started with app control</span></span>

<span data-ttu-id="0f35e-104">Innan du aktiverar appkontrollen i din miljö bör du granska och förstå [hur Microsoft Hanterat skrivbord](../service-description/app-control.md) implementerar den samt dina roller och ansvarsområden.</span><span class="sxs-lookup"><span data-stu-id="0f35e-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="0f35e-105">Microsoft Hanterat skrivbord förenklar appstyrningen genom att ta hand om de svårare aspekterna med att få en säker grundprincip.</span><span class="sxs-lookup"><span data-stu-id="0f35e-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="0f35e-106">IT-administratörerna måste fortfarande testa apparna i testringen och granska loggarna för eventuella varningar eller fel.</span><span class="sxs-lookup"><span data-stu-id="0f35e-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="0f35e-107">Om en app behöver ett undantag kan du arkivera en begäran eller välja Microsoft Hanterat skrivbord Åtgärd kan vara beroende på vem som identifierar den först.</span><span class="sxs-lookup"><span data-stu-id="0f35e-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="0f35e-108">Första distribution av appar</span><span class="sxs-lookup"><span data-stu-id="0f35e-108">Initial deployment of apps</span></span>

<span data-ttu-id="0f35e-109">När du först distribuerar appar Microsoft Hanterat skrivbord utvärdera deras aktuella beteende.</span><span class="sxs-lookup"><span data-stu-id="0f35e-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="0f35e-110">De exakta stegen för att aktivera appkontroll beror på om enheter redan har distribuerats i din miljö.</span><span class="sxs-lookup"><span data-stu-id="0f35e-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="0f35e-111">Enheter som ännu inte används</span><span class="sxs-lookup"><span data-stu-id="0f35e-111">Devices not yet in use</span></span>

<span data-ttu-id="0f35e-112">Om du inte redan har några enheter som används kan du öppna ett service ticket with Microsoft Hanterat skrivbord Operations och begära att vi aktiverar appkontroll.</span><span class="sxs-lookup"><span data-stu-id="0f35e-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="0f35e-113">Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:</span><span class="sxs-lookup"><span data-stu-id="0f35e-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="0f35e-114">Distributions grupp</span><span class="sxs-lookup"><span data-stu-id="0f35e-114">Deployment group</span></span>  |<span data-ttu-id="0f35e-115">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="0f35e-115">Policy type</span></span>  |<span data-ttu-id="0f35e-116">Tidsinställning</span><span class="sxs-lookup"><span data-stu-id="0f35e-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0f35e-117">Test</span><span class="sxs-lookup"><span data-stu-id="0f35e-117">Test</span></span>     |  <span data-ttu-id="0f35e-118">Granskning</span><span class="sxs-lookup"><span data-stu-id="0f35e-118">Audit</span></span>       |  <span data-ttu-id="0f35e-119">Dag 0</span><span class="sxs-lookup"><span data-stu-id="0f35e-119">Day 0</span></span>       |
|<span data-ttu-id="0f35e-120">Första</span><span class="sxs-lookup"><span data-stu-id="0f35e-120">First</span></span>     | <span data-ttu-id="0f35e-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-121">Enforced</span></span>        | <span data-ttu-id="0f35e-122">Dag 1</span><span class="sxs-lookup"><span data-stu-id="0f35e-122">Day 1</span></span>        |
|<span data-ttu-id="0f35e-123">Snabbt</span><span class="sxs-lookup"><span data-stu-id="0f35e-123">Fast</span></span>     | <span data-ttu-id="0f35e-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-124">Enforced</span></span>        |  <span data-ttu-id="0f35e-125">Dag 2</span><span class="sxs-lookup"><span data-stu-id="0f35e-125">Day 2</span></span>       |
|<span data-ttu-id="0f35e-126">Bred</span><span class="sxs-lookup"><span data-stu-id="0f35e-126">Broad</span></span>     | <span data-ttu-id="0f35e-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-127">Enforced</span></span>        |  <span data-ttu-id="0f35e-128">Dag 3</span><span class="sxs-lookup"><span data-stu-id="0f35e-128">Day 3</span></span>       |

<span data-ttu-id="0f35e-129">Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="0f35e-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="0f35e-130">Enheter som redan används</span><span class="sxs-lookup"><span data-stu-id="0f35e-130">Devices already in use</span></span>

<span data-ttu-id="0f35e-131">Om du redan har minst en Microsoft Hanterat skrivbord enhet som används gör du så här:</span><span class="sxs-lookup"><span data-stu-id="0f35e-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="0f35e-132">Öppna ett tjänst ticket with Microsoft Hanterat skrivbord Operations requesting that we turn on app control.</span><span class="sxs-lookup"><span data-stu-id="0f35e-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="0f35e-133">Åtgärder kommer att distribuera [en granskningsprincip](../service-description/app-control.md#audit-policy) på alla enheter.</span><span class="sxs-lookup"><span data-stu-id="0f35e-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="0f35e-134">[Testa dina program](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) för att se om några skulle blockeras.</span><span class="sxs-lookup"><span data-stu-id="0f35e-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="0f35e-135">Om ett program skulle blockeras öppnar du en [undertecknarbegäran.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="0f35e-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="0f35e-136">När du har slutfört testningen (oavsett resultat), meddelar du Åtgärder, med information om väntande signeringsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="0f35e-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="0f35e-137">Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:</span><span class="sxs-lookup"><span data-stu-id="0f35e-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="0f35e-138">Distributions grupp</span><span class="sxs-lookup"><span data-stu-id="0f35e-138">Deployment group</span></span>  |<span data-ttu-id="0f35e-139">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="0f35e-139">Policy type</span></span>  |<span data-ttu-id="0f35e-140">Tidsinställning</span><span class="sxs-lookup"><span data-stu-id="0f35e-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0f35e-141">Test</span><span class="sxs-lookup"><span data-stu-id="0f35e-141">Test</span></span>     |  <span data-ttu-id="0f35e-142">Granskning</span><span class="sxs-lookup"><span data-stu-id="0f35e-142">Audit</span></span>       |  <span data-ttu-id="0f35e-143">Dag 0</span><span class="sxs-lookup"><span data-stu-id="0f35e-143">Day 0</span></span>       |
|<span data-ttu-id="0f35e-144">Första</span><span class="sxs-lookup"><span data-stu-id="0f35e-144">First</span></span>     | <span data-ttu-id="0f35e-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-145">Enforced</span></span>        | <span data-ttu-id="0f35e-146">Dag 1</span><span class="sxs-lookup"><span data-stu-id="0f35e-146">Day 1</span></span>        |
|<span data-ttu-id="0f35e-147">Snabbt</span><span class="sxs-lookup"><span data-stu-id="0f35e-147">Fast</span></span>     | <span data-ttu-id="0f35e-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-148">Enforced</span></span>        |  <span data-ttu-id="0f35e-149">Pausad, distribuerad på begäran</span><span class="sxs-lookup"><span data-stu-id="0f35e-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="0f35e-150">Bred</span><span class="sxs-lookup"><span data-stu-id="0f35e-150">Broad</span></span>     | <span data-ttu-id="0f35e-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="0f35e-151">Enforced</span></span>        |  <span data-ttu-id="0f35e-152">Pausad, distribuerad på begäran</span><span class="sxs-lookup"><span data-stu-id="0f35e-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="0f35e-153">Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="0f35e-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



