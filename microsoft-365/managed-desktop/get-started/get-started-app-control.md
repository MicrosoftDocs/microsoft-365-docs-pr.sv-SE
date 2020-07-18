---
title: Komma igång med appkontroll
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170741"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="57015-103">Komma igång med appkontroll</span><span class="sxs-lookup"><span data-stu-id="57015-103">Get started with app control</span></span>

<span data-ttu-id="57015-104">Innan du aktiverar appkontroll i din miljö bör du granska och förstå [hur Microsoft Managed Desktop implementerar den](../service-description/app-control.md) och dina roller och ansvarsområden.</span><span class="sxs-lookup"><span data-stu-id="57015-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="57015-105">Microsoft Managed Desktop förenklar appkontrollen genom att ta hand om de mer utmanande aspekterna av att få en säker basprincip.</span><span class="sxs-lookup"><span data-stu-id="57015-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="57015-106">IT-administratörerna måste fortfarande testa dina appar i testringen och granska loggarna för varningar eller fel.</span><span class="sxs-lookup"><span data-stu-id="57015-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="57015-107">Om en app behöver ett undantag kan du lämna in en begäran eller microsoft managed desktop-drift kan, beroende på vem som identifierar den först.</span><span class="sxs-lookup"><span data-stu-id="57015-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="57015-108">Inledande distribution av appar</span><span class="sxs-lookup"><span data-stu-id="57015-108">Initial deployment of apps</span></span>

<span data-ttu-id="57015-109">När du distribuerar appar första gången måste Microsoft Managed Desktop bedöma deras aktuella beteende.</span><span class="sxs-lookup"><span data-stu-id="57015-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="57015-110">De exakta stegen för att aktivera appkontroll beror på om enheter redan har distribuerats i din miljö.</span><span class="sxs-lookup"><span data-stu-id="57015-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="57015-111">Enheter som redan används</span><span class="sxs-lookup"><span data-stu-id="57015-111">Devices already in use</span></span>

<span data-ttu-id="57015-112">Om du redan har minst en Microsoft Managed Desktop-enhet i bruk gör du så här:</span><span class="sxs-lookup"><span data-stu-id="57015-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="57015-113">Öppna en tjänstbiljett med Microsoft Managed Desktop Operations som begär att vi aktiverar appkontroll.</span><span class="sxs-lookup"><span data-stu-id="57015-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="57015-114">Åtgärder distribuerar en [granskningsprincip](../service-description/app-control.md#audit-policy) till alla enheter.</span><span class="sxs-lookup"><span data-stu-id="57015-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="57015-115">[Testa dina program](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) för att se om någon skulle blockeras.</span><span class="sxs-lookup"><span data-stu-id="57015-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="57015-116">Om ett program skulle blockeras öppnar du en [undertecknarbegäran](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="57015-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="57015-117">När du har slutfört din testning (oavsett resultat), meddela Åtgärder, notera eventuella väntande undertecknare förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="57015-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="57015-118">Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:</span><span class="sxs-lookup"><span data-stu-id="57015-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="57015-119">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="57015-119">Deployment group</span></span>  |<span data-ttu-id="57015-120">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="57015-120">Policy type</span></span>  |<span data-ttu-id="57015-121">Timing</span><span class="sxs-lookup"><span data-stu-id="57015-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="57015-122">Test</span><span class="sxs-lookup"><span data-stu-id="57015-122">Test</span></span>     |  <span data-ttu-id="57015-123">Revision</span><span class="sxs-lookup"><span data-stu-id="57015-123">Audit</span></span>       |  <span data-ttu-id="57015-124">Dag 0</span><span class="sxs-lookup"><span data-stu-id="57015-124">Day 0</span></span>       |
|<span data-ttu-id="57015-125">Första</span><span class="sxs-lookup"><span data-stu-id="57015-125">First</span></span>     | <span data-ttu-id="57015-126">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-126">Enforced</span></span>        | <span data-ttu-id="57015-127">Dag 1</span><span class="sxs-lookup"><span data-stu-id="57015-127">Day 1</span></span>        |
|<span data-ttu-id="57015-128">Snabb</span><span class="sxs-lookup"><span data-stu-id="57015-128">Fast</span></span>     | <span data-ttu-id="57015-129">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-129">Enforced</span></span>        |  <span data-ttu-id="57015-130">Dag 3</span><span class="sxs-lookup"><span data-stu-id="57015-130">Day 3</span></span>       |
|<span data-ttu-id="57015-131">Bred</span><span class="sxs-lookup"><span data-stu-id="57015-131">Broad</span></span>     | <span data-ttu-id="57015-132">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-132">Enforced</span></span>        |  <span data-ttu-id="57015-133">Dag 7</span><span class="sxs-lookup"><span data-stu-id="57015-133">Day 7</span></span>       |

<span data-ttu-id="57015-134">Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="57015-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="57015-135">Enheter som ännu inte används</span><span class="sxs-lookup"><span data-stu-id="57015-135">Devices not yet in use</span></span>

<span data-ttu-id="57015-136">Om du ännu inte har några enheter i bruk öppnar du en tjänstbiljett med Microsoft Managed Desktop Operations som begär att vi aktiverar appkontroll.</span><span class="sxs-lookup"><span data-stu-id="57015-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="57015-137">Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:</span><span class="sxs-lookup"><span data-stu-id="57015-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="57015-138">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="57015-138">Deployment group</span></span>  |<span data-ttu-id="57015-139">Typ av princip</span><span class="sxs-lookup"><span data-stu-id="57015-139">Policy type</span></span>  |<span data-ttu-id="57015-140">Timing</span><span class="sxs-lookup"><span data-stu-id="57015-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="57015-141">Test</span><span class="sxs-lookup"><span data-stu-id="57015-141">Test</span></span>     |  <span data-ttu-id="57015-142">Revision</span><span class="sxs-lookup"><span data-stu-id="57015-142">Audit</span></span>       |  <span data-ttu-id="57015-143">Dag 0</span><span class="sxs-lookup"><span data-stu-id="57015-143">Day 0</span></span>       |
|<span data-ttu-id="57015-144">Första</span><span class="sxs-lookup"><span data-stu-id="57015-144">First</span></span>     | <span data-ttu-id="57015-145">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-145">Enforced</span></span>        | <span data-ttu-id="57015-146">Dag 1</span><span class="sxs-lookup"><span data-stu-id="57015-146">Day 1</span></span>        |
|<span data-ttu-id="57015-147">Snabb</span><span class="sxs-lookup"><span data-stu-id="57015-147">Fast</span></span>     | <span data-ttu-id="57015-148">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-148">Enforced</span></span>        |  <span data-ttu-id="57015-149">Dag 3</span><span class="sxs-lookup"><span data-stu-id="57015-149">Day 3</span></span>       |
|<span data-ttu-id="57015-150">Bred</span><span class="sxs-lookup"><span data-stu-id="57015-150">Broad</span></span>     | <span data-ttu-id="57015-151">Verkställas</span><span class="sxs-lookup"><span data-stu-id="57015-151">Enforced</span></span>        |  <span data-ttu-id="57015-152">Dag 7</span><span class="sxs-lookup"><span data-stu-id="57015-152">Day 7</span></span>       |

<span data-ttu-id="57015-153">Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.</span><span class="sxs-lookup"><span data-stu-id="57015-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

