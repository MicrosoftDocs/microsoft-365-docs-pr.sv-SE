---
title: Distribuera konfigurerbara inställningar i Microsoft Hanterat skrivbord
description: Distribuera och spåra konfigurerbara inställningsändringar i Microsoft Hanterat skrivbord.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, distribuera, fasad distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287807"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="e93c2-104">Distribuera och spåra konfigurerbara inställningar – Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="e93c2-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="e93c2-105">När du har gjort ändringar i inställningskategorierna och fasa in en distribution kan du på sidan Distributionsstatus börja distribuera inställningarna till grupper.</span><span class="sxs-lookup"><span data-stu-id="e93c2-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="e93c2-106">På den här sidan visas en sammanfattning av varje konfigurerbar inställning.</span><span class="sxs-lookup"><span data-stu-id="e93c2-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="e93c2-107">Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för distributionerna.</span><span class="sxs-lookup"><span data-stu-id="e93c2-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="e93c2-108">Distributionsstatus</span><span class="sxs-lookup"><span data-stu-id="e93c2-108">Deployment statuses</span></span>

<span data-ttu-id="e93c2-109">Det här är de statusar som visas för varje distribution.</span><span class="sxs-lookup"><span data-stu-id="e93c2-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="e93c2-110">Status</span><span class="sxs-lookup"><span data-stu-id="e93c2-110">Status</span></span> | <span data-ttu-id="e93c2-111">Förklaring</span><span class="sxs-lookup"><span data-stu-id="e93c2-111">Explanation</span></span>
--- | ---
<span data-ttu-id="e93c2-112">Distribuera</span><span class="sxs-lookup"><span data-stu-id="e93c2-112">Deploy</span></span> | <span data-ttu-id="e93c2-113">Ändringen väntar på att distribueras till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="e93c2-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="e93c2-114">Pågående</span><span class="sxs-lookup"><span data-stu-id="e93c2-114">In progress</span></span> | <span data-ttu-id="e93c2-115">Ändringen tillämpas på aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="e93c2-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="e93c2-116">Slutfört</span><span class="sxs-lookup"><span data-stu-id="e93c2-116">Complete</span></span> | <span data-ttu-id="e93c2-117">Ändringen slutfördes på alla aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="e93c2-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="e93c2-118">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="e93c2-118">Failed</span></span> | <span data-ttu-id="e93c2-119">Ändringen misslyckades på 10 procent av alla aktiva enheter i gruppen, så distributionen stoppades.</span><span class="sxs-lookup"><span data-stu-id="e93c2-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="e93c2-120">En supportbegäran öppnas automatiskt med Microsoft Hanterat skrivbord för att felsöka distributionen.</span><span class="sxs-lookup"><span data-stu-id="e93c2-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="e93c2-121">Återställd</span><span class="sxs-lookup"><span data-stu-id="e93c2-121">Reverted</span></span> | <span data-ttu-id="e93c2-122">Ändringen återställdes till den senaste ändringen som distribuerades till alla distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e93c2-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="e93c2-123">Distribuera ändringar</span><span class="sxs-lookup"><span data-stu-id="e93c2-123">Deploy changes</span></span>

<span data-ttu-id="e93c2-124">Vi kommer att visa bakgrundsbilden för skrivbordet i de här instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="e93c2-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="e93c2-125">När du har gjort en distribution distribuerar du ändringar från sidan Distributionsstatus.</span><span class="sxs-lookup"><span data-stu-id="e93c2-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="e93c2-126">**Distribuera ändringar**</span><span class="sxs-lookup"><span data-stu-id="e93c2-126">**To deploy changes**</span></span>

1. <span data-ttu-id="e93c2-127">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="e93c2-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="e93c2-128">Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e93c2-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="e93c2-129">Välj **den inställning** du vill distribuera i arbetsytan Distributionsstatus och välj sedan den distribution som ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="e93c2-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="e93c2-130">Välj **Distribuera** för att distribuera ändringen till någon av distributionsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="e93c2-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="e93c2-131">Den orange varningsikonen visar att det finns en tidigare grupp tillgänglig för distribution eftersom vi rekommenderar att distribuera den i ordning.</span><span class="sxs-lookup"><span data-stu-id="e93c2-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="e93c2-132">Vi rekommenderar att du distribuerar till distributionsgrupper i följande ordning: Testa först, snabbt och sedan bred.</span><span class="sxs-lookup"><span data-stu-id="e93c2-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="e93c2-133">När ändringarna är slutförda i varje grupp ändras statusen till **Slutförd.**</span><span class="sxs-lookup"><span data-stu-id="e93c2-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="e93c2-134">Återställ distribution</span><span class="sxs-lookup"><span data-stu-id="e93c2-134">Revert deployment</span></span>

<span data-ttu-id="e93c2-135">När du har distribuerat en ändring kan du återgå till **Distributionsstatus.**</span><span class="sxs-lookup"><span data-stu-id="e93c2-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="e93c2-136">När du återställer en ändring som **pågår eller** **Slutförd upphör** den aktuella distributionen.</span><span class="sxs-lookup"><span data-stu-id="e93c2-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="e93c2-137">Inställningen återgår till den senaste versionen som distribuerades till alla grupper.</span><span class="sxs-lookup"><span data-stu-id="e93c2-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="e93c2-138">Vi kommer att visa stegen för att återställa en ändring med hjälp av skrivbordsbakgrundsbilden som exempel.</span><span class="sxs-lookup"><span data-stu-id="e93c2-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="e93c2-139">**Om du vill återställa en ändring**</span><span class="sxs-lookup"><span data-stu-id="e93c2-139">**To revert a change**</span></span>

1. <span data-ttu-id="e93c2-140">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter</span><span class="sxs-lookup"><span data-stu-id="e93c2-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="e93c2-141">Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e93c2-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="e93c2-142">Välj **den inställning** du vill återställa i arbetsytan Distributionsstatus och välj sedan den stegade distributionen för att återställa.</span><span class="sxs-lookup"><span data-stu-id="e93c2-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="e93c2-143">Under **Behöver du återställa den här ändringen?** väljer du Återställ **distribution.**</span><span class="sxs-lookup"><span data-stu-id="e93c2-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="e93c2-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e93c2-144">Additional resources</span></span>

- [<span data-ttu-id="e93c2-145">Översikt över konfigurerbara inställningar</span><span class="sxs-lookup"><span data-stu-id="e93c2-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="e93c2-146">Referens för inställningar som kan konfigureras</span><span class="sxs-lookup"><span data-stu-id="e93c2-146">Configurable settings reference</span></span>](config-setting-ref.md) 
