---
title: Distribuera konfigurerbara inställningar på Microsoft Managed Desktop
description: Distribuera och spåra konfigurerbara inställningar i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, distribuera, iscensatt distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806450"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="f5a5d-104">Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f5a5d-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="f5a5d-105">När du har gjort ändringar i inställningskategorierna och arrangerat en distribution kan du med sidan Distributionsstatus börja distribuera inställningarna till grupper.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="f5a5d-106">På den här sidan visas en sammanfattning av varje konfigurerbar inställning.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="f5a5d-107">Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="f5a5d-108">Distributionsstatus</span><span class="sxs-lookup"><span data-stu-id="f5a5d-108">Deployment statuses</span></span> 

<span data-ttu-id="f5a5d-109">Det här är statusarna som visas för varje distribution.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="f5a5d-110">Status</span><span class="sxs-lookup"><span data-stu-id="f5a5d-110">Status</span></span>  | <span data-ttu-id="f5a5d-111">Förklaring</span><span class="sxs-lookup"><span data-stu-id="f5a5d-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="f5a5d-112">Distribuera</span><span class="sxs-lookup"><span data-stu-id="f5a5d-112">Deploy</span></span> | <span data-ttu-id="f5a5d-113">Ändringen väntar på att distribueras till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="f5a5d-114">Pågående</span><span class="sxs-lookup"><span data-stu-id="f5a5d-114">In progress</span></span> | <span data-ttu-id="f5a5d-115">Ändringen tillämpas på aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="f5a5d-116">Komplett</span><span class="sxs-lookup"><span data-stu-id="f5a5d-116">Complete</span></span> | <span data-ttu-id="f5a5d-117">Ändringen slutfördes på alla aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="f5a5d-118">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="f5a5d-118">Failed</span></span> | <span data-ttu-id="f5a5d-119">Ändringen misslyckades på 10 procent av aktiva enheter i gruppen, så distributionen stoppades.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="f5a5d-120">En supportbegäran öppnas automatiskt med Microsoft Managed Desktop-åtgärder för att felsöka distributionen.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="f5a5d-121">Återgick</span><span class="sxs-lookup"><span data-stu-id="f5a5d-121">Reverted</span></span> | <span data-ttu-id="f5a5d-122">Ändringen återgick till den senaste ändringen som har distribuerats till alla distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="f5a5d-123">Distribuera ändringar</span><span class="sxs-lookup"><span data-stu-id="f5a5d-123">Deploy changes</span></span>

<span data-ttu-id="f5a5d-124">Vi visar skrivbordsbakgrundsbild i dessa instruktioner.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="f5a5d-125">När du har genomfört en distribution distribuerar du ändringar från sidan Distributionsstatus.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="f5a5d-126">**Så här distribuerar du ändringar**</span><span class="sxs-lookup"><span data-stu-id="f5a5d-126">**To deploy changes**</span></span>

1. <span data-ttu-id="f5a5d-127">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="f5a5d-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="f5a5d-128">Under **Inställningar**väljer du **Konfigurerbar**.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="f5a5d-129">I **arbetsytan distributionsstatus** väljer du den inställning som du vill distribuera och väljer sedan den stegvisa distributionsom ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="f5a5d-130">Välj **Distribuera** om du vill distribuera ändringen till en av distributionsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="f5a5d-131">Ikonen för orange varning anger att det finns en tidigare grupp tillgänglig för distribution eftersom det rekommenderas att distribueras i ordning.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="f5a5d-132">![Arbetsyta för distributionsstatus.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-132">![Deployment status workspace.</span></span> <span data-ttu-id="f5a5d-133">Fönstret Betrodda platser till höger.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="f5a5d-134">I avsnittet Distributionsgrupper finns tre kolumner: distributionsgrupper, enheter och status.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="f5a5d-135">I statuskolumnen markeras "distribution".](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="f5a5d-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="f5a5d-136">Vi rekommenderar att du distribuerar till distributionsgrupper i den här ordningen: Testa, Först, Snabb och sedan Bred.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="f5a5d-137">När ändringarna är slutförda i varje grupp ändras statusen till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![Arbetsyta för distributionsstatus med kolumner för datumuppdaterade, version, test, först, snabb och bred.](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="f5a5d-140">Återställ distributionen</span><span class="sxs-lookup"><span data-stu-id="f5a5d-140">Revert deployment</span></span>

<span data-ttu-id="f5a5d-141">När du har distribuerat en ändring kan du återgå från **distributionsstatus**.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="f5a5d-142">När du återställer en ändring som **pågår** eller **är slutförd**stoppas den aktuella distributionen.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="f5a5d-143">Inställningen återgår till den senaste versionen som distribuerades till alla grupper.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="f5a5d-144">Vi visar stegen för att återställa en ändring med bakgrundsbilden Skrivbord som exempel.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="f5a5d-145">**Så här återställer du en ändring**</span><span class="sxs-lookup"><span data-stu-id="f5a5d-145">**To revert a change**</span></span>
1. <span data-ttu-id="f5a5d-146">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="f5a5d-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="f5a5d-147">Under **Inställningar**väljer du **Konfigurerbar**.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="f5a5d-148">I **arbetsytan distributionsstatus** väljer du den inställning du vill återställa och väljer sedan den stegvisa distributionen som ska återställas.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="f5a5d-149">Under **Behöver du återställa den här ändringen?** väljer du Återställ **distribution**.</span><span class="sxs-lookup"><span data-stu-id="f5a5d-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Arbetsyta för distributionsstatus.](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="f5a5d-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f5a5d-153">Additional resources</span></span>
- [<span data-ttu-id="f5a5d-154">Översikt över konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="f5a5d-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="f5a5d-155">Referens för konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="f5a5d-155">Configurable settings reference</span></span>](config-setting-ref.md) 
