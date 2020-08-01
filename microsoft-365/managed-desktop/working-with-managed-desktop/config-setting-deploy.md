---
title: Distribuera konfigurerbara inställningar i Microsoft Managed Desktop
description: Distribuera och spåra konfigurerbara inställningsändringar i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, distribution, mellanlagd distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530265"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="ac222-104">Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ac222-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="ac222-105">När du har gjort ändringar i inställningskategorierna och arrangera en distribution kan du på sidan Distributionsstatus börja distribuera dina inställningar till grupper.</span><span class="sxs-lookup"><span data-stu-id="ac222-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="ac222-106">På den här sidan visas en sammanfattning av varje konfigurerbar inställning.</span><span class="sxs-lookup"><span data-stu-id="ac222-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="ac222-107">Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.</span><span class="sxs-lookup"><span data-stu-id="ac222-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="ac222-108">Distributionsstatus</span><span class="sxs-lookup"><span data-stu-id="ac222-108">Deployment statuses</span></span> 

<span data-ttu-id="ac222-109">Det här är de statusar som visas för varje distribution.</span><span class="sxs-lookup"><span data-stu-id="ac222-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="ac222-110">Status</span><span class="sxs-lookup"><span data-stu-id="ac222-110">Status</span></span>  | <span data-ttu-id="ac222-111">Förklaring</span><span class="sxs-lookup"><span data-stu-id="ac222-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="ac222-112">Distribuera</span><span class="sxs-lookup"><span data-stu-id="ac222-112">Deploy</span></span> | <span data-ttu-id="ac222-113">Ändringen väntar på att distribueras till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="ac222-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="ac222-114">Pågår</span><span class="sxs-lookup"><span data-stu-id="ac222-114">In progress</span></span> | <span data-ttu-id="ac222-115">Ändringen tillämpas på aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="ac222-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="ac222-116">Komplett</span><span class="sxs-lookup"><span data-stu-id="ac222-116">Complete</span></span> | <span data-ttu-id="ac222-117">Ändringen slutfördes på alla aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="ac222-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="ac222-118">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="ac222-118">Failed</span></span> | <span data-ttu-id="ac222-119">Ändringen misslyckades på en 10 procent av aktiva enheter i gruppen, så distributionen stoppades.</span><span class="sxs-lookup"><span data-stu-id="ac222-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="ac222-120">En supportbegäran öppnas automatiskt med Microsoft Managed Desktop-åtgärder för att felsöka distributionen.</span><span class="sxs-lookup"><span data-stu-id="ac222-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="ac222-121">Återgick</span><span class="sxs-lookup"><span data-stu-id="ac222-121">Reverted</span></span> | <span data-ttu-id="ac222-122">Ändringen återställdes till den senaste ändringen som har distribuerats till alla distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ac222-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="ac222-123">Distribuera ändringar</span><span class="sxs-lookup"><span data-stu-id="ac222-123">Deploy changes</span></span>

<span data-ttu-id="ac222-124">Vi visar skrivbordsbakgrundsbild i de här instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="ac222-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="ac222-125">När du har iscensatt en distribution distribuerar du ändringar från statussidan för distribution.</span><span class="sxs-lookup"><span data-stu-id="ac222-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="ac222-126">**Så här distribuerar du ändringar**</span><span class="sxs-lookup"><span data-stu-id="ac222-126">**To deploy changes**</span></span>

1. <span data-ttu-id="ac222-127">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="ac222-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="ac222-128">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="ac222-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="ac222-129">I **distributionsstatusarbetsytan** väljer du den inställning som du vill distribuera och väljer sedan den stegvisa distributionen som ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="ac222-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="ac222-130">Välj **Distribuera om** du vill distribuera ändringen till en av distributionsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="ac222-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="ac222-131">Den orangea varningsikonen anger att det finns en tidigare grupp tillgänglig för distribution eftersom det rekommenderas att distribueras i ordning.</span><span class="sxs-lookup"><span data-stu-id="ac222-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="ac222-132">![Arbetsyta för distributionsstatus.</span><span class="sxs-lookup"><span data-stu-id="ac222-132">![Deployment status workspace.</span></span> <span data-ttu-id="ac222-133">Fönstret Betrodda platser till höger.</span><span class="sxs-lookup"><span data-stu-id="ac222-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="ac222-134">I avsnittet Distributionsgrupper finns tre kolumner: distributionsgrupper, enheter och status.</span><span class="sxs-lookup"><span data-stu-id="ac222-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="ac222-135">I statuskolumnen markeras "deploy".](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="ac222-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="ac222-136">Vi rekommenderar distribution till distributionsgrupper i den här ordningen: Testa, Först, Snabbt och sedan Brett.</span><span class="sxs-lookup"><span data-stu-id="ac222-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="ac222-137">När ändringarna är slutförd i varje grupp ändras statusen till **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="ac222-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![Arbetsyta för distributionsstatus med kolumner för datumupptror, version, test, först, snabbt och brett.](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="ac222-140">Återställa distributionen</span><span class="sxs-lookup"><span data-stu-id="ac222-140">Revert deployment</span></span>

<span data-ttu-id="ac222-141">När du har distribuerat en ändring kan du återgå från **distributionsstatus**.</span><span class="sxs-lookup"><span data-stu-id="ac222-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="ac222-142">När du återställer en ändring som **pågår** eller **Slutför**stoppas den aktuella distributionen.</span><span class="sxs-lookup"><span data-stu-id="ac222-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="ac222-143">Inställningen återgår till den senaste versionen som distribuerades till alla grupper.</span><span class="sxs-lookup"><span data-stu-id="ac222-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="ac222-144">Vi visar stegen för att återställa en ändring med bakgrundsbilden Skrivbord som ett exempel.</span><span class="sxs-lookup"><span data-stu-id="ac222-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="ac222-145">**Så här återställer du en ändring**</span><span class="sxs-lookup"><span data-stu-id="ac222-145">**To revert a change**</span></span>
1. <span data-ttu-id="ac222-146">Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="ac222-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="ac222-147">Under **Inställningar**väljer du **Konfigurera .**</span><span class="sxs-lookup"><span data-stu-id="ac222-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="ac222-148">I **distributionsstatusarbetsytan** väljer du den inställning som du vill återställa och väljer sedan den stegvisa distributionen för att återgå.</span><span class="sxs-lookup"><span data-stu-id="ac222-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="ac222-149">Välj Återställ **distributionen**under **Behöver du återställa den här ändringen?**</span><span class="sxs-lookup"><span data-stu-id="ac222-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Arbetsyta för distributionsstatus.](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="ac222-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ac222-153">Additional resources</span></span>
- [<span data-ttu-id="ac222-154">Översikt över konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="ac222-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="ac222-155">Referens för inställningar som kan konfigureras</span><span class="sxs-lookup"><span data-stu-id="ac222-155">Configurable settings reference</span></span>](config-setting-ref.md) 
