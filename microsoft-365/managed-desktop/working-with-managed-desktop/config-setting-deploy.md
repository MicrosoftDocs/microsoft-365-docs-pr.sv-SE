---
title: Distribuera konfigurerbara inställningar på Microsoft Managed Desktop
description: Distribuera och spåra ändringar som kan konfigureras i Microsoft hanterat skriv bord.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, distribution, stegvis distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104540"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="d1248-104">Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1248-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="d1248-105">När du har gjort ändringar i inställnings kategorierna och scen en distribution kan du använda sidan för distributions status för att börja distribuera dina inställningar till grupper.</span><span class="sxs-lookup"><span data-stu-id="d1248-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="d1248-106">På den här sidan visas en sammanfattning av varje konfigurerbar inställning.</span><span class="sxs-lookup"><span data-stu-id="d1248-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="d1248-107">Genom att öppna en inställnings kategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.</span><span class="sxs-lookup"><span data-stu-id="d1248-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="d1248-108">Distributions status</span><span class="sxs-lookup"><span data-stu-id="d1248-108">Deployment statuses</span></span> 

<span data-ttu-id="d1248-109">Dessa status värden visas för varje distribution.</span><span class="sxs-lookup"><span data-stu-id="d1248-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="d1248-110">Status</span><span class="sxs-lookup"><span data-stu-id="d1248-110">Status</span></span>  | <span data-ttu-id="d1248-111">Förklaring</span><span class="sxs-lookup"><span data-stu-id="d1248-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="d1248-112">Distribuera</span><span class="sxs-lookup"><span data-stu-id="d1248-112">Deploy</span></span> | <span data-ttu-id="d1248-113">Din ändring väntar på att distribueras till den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="d1248-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="d1248-114">Pågår</span><span class="sxs-lookup"><span data-stu-id="d1248-114">In progress</span></span> | <span data-ttu-id="d1248-115">Ändringen tillämpas på aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="d1248-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="d1248-116">Kunna</span><span class="sxs-lookup"><span data-stu-id="d1248-116">Complete</span></span> | <span data-ttu-id="d1248-117">Ändringen slutförd på alla aktiva enheter i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="d1248-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="d1248-118">Misslyckades</span><span class="sxs-lookup"><span data-stu-id="d1248-118">Failed</span></span> | <span data-ttu-id="d1248-119">Ändringen misslyckades på 10 procent av aktiva enheter i gruppen, så distributionen stoppades.</span><span class="sxs-lookup"><span data-stu-id="d1248-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="d1248-120">En supportbegäran öppnas automatiskt med Microsoft hanterade Skriv bords åtgärder för att felsöka distributionen.</span><span class="sxs-lookup"><span data-stu-id="d1248-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="d1248-121">Återställt</span><span class="sxs-lookup"><span data-stu-id="d1248-121">Reverted</span></span> | <span data-ttu-id="d1248-122">Ändringen återfördes till den senaste ändringen som lyckades distribueras till alla distributions grupper.</span><span class="sxs-lookup"><span data-stu-id="d1248-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="d1248-123">Distribuera ändringar</span><span class="sxs-lookup"><span data-stu-id="d1248-123">Deploy changes</span></span>

<span data-ttu-id="d1248-124">Vi kommer att Visa Skriv bords bakgrund i dessa instruktioner.</span><span class="sxs-lookup"><span data-stu-id="d1248-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="d1248-125">När du har mellanlagrat en distribution distribueras ändringarna från sidan distributions status.</span><span class="sxs-lookup"><span data-stu-id="d1248-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="d1248-126">**Distribuera ändringar**</span><span class="sxs-lookup"><span data-stu-id="d1248-126">**To deploy changes**</span></span>

1. <span data-ttu-id="d1248-127">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="d1248-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="d1248-128">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="d1248-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="d1248-129">I arbets ytan **distributions status** väljer du den inställning du vill distribuera och väljer sedan den stegvisa distribution som ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="d1248-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="d1248-130">Välj **distribuera** för att distribuera ändringen till en av distributions grupperna.</span><span class="sxs-lookup"><span data-stu-id="d1248-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="d1248-131">Varnings ikonen för Orange visar att en tidigare grupp är tillgänglig för distribution eftersom den är rekommenderad för att bli uppkopplad.</span><span class="sxs-lookup"><span data-stu-id="d1248-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="d1248-132">Vi rekommenderar att du distribuerar till distributions grupper i den här ordningen: testa, första, snabba och sedan breda.</span><span class="sxs-lookup"><span data-stu-id="d1248-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="d1248-133">När ändringar är slutförda i varje grupp ändras statusen till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="d1248-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="d1248-134">Återställ distribution</span><span class="sxs-lookup"><span data-stu-id="d1248-134">Revert deployment</span></span>

<span data-ttu-id="d1248-135">När du har distribuerat en ändring kan du återgå från **distributions status**.</span><span class="sxs-lookup"><span data-stu-id="d1248-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="d1248-136">När du återställer en ändring som **pågår** eller **slutförs**stoppar den aktuella distributionen.</span><span class="sxs-lookup"><span data-stu-id="d1248-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="d1248-137">Inställningen återställs till den senaste versionen som distribueras till alla grupper.</span><span class="sxs-lookup"><span data-stu-id="d1248-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="d1248-138">Vi visar stegen för att återställa en ändring med hjälp av Skriv bords bakgrunds bilden som ett exempel.</span><span class="sxs-lookup"><span data-stu-id="d1248-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="d1248-139">**Så här återställer du en ändring**</span><span class="sxs-lookup"><span data-stu-id="d1248-139">**To revert a change**</span></span>
1. <span data-ttu-id="d1248-140">Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**</span><span class="sxs-lookup"><span data-stu-id="d1248-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="d1248-141">Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="d1248-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="d1248-142">I arbets ytan **distributions status** väljer du den inställning som du vill återställa och väljer sedan den stegvisa distribution som du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="d1248-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="d1248-143">Under **behöver du återställa den här ändringen?** väljer du **Återställ distribution**.</span><span class="sxs-lookup"><span data-stu-id="d1248-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="d1248-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d1248-144">Additional resources</span></span>
- [<span data-ttu-id="d1248-145">Inställningar för konfigurerings bara översikt</span><span class="sxs-lookup"><span data-stu-id="d1248-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="d1248-146">Referens för inställningar som kan konfigureras</span><span class="sxs-lookup"><span data-stu-id="d1248-146">Configurable settings reference</span></span>](config-setting-ref.md) 
