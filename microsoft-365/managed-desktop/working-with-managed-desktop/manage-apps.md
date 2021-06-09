---
title: Hantera appar i Microsoft Hanterat skrivbord
description: Information om hur du uppdaterar verksamhetsbaserade appar som distribueras till Microsoft Hanterat skrivbord enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812928"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="be83d-104">Hantera branschspecifika appar på Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="be83d-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="be83d-105">Det finns några olika sätt att hantera programuppdateringar för appar som du har introducerat för Microsoft Hanterat skrivbord och distribuerat till dina Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="be83d-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="be83d-106">Du kan göra appuppdateringar i Microsoft Hanterat skrivbord portal eller Intune.</span><span class="sxs-lookup"><span data-stu-id="be83d-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="be83d-107">Uppdatera verksamhetsbaserade appar i Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="be83d-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="be83d-108">**Så här uppdaterar du dina verksamhetsbaserade appar i Microsoft Hanterat skrivbord portalen**</span><span class="sxs-lookup"><span data-stu-id="be83d-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="be83d-109">Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="be83d-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="be83d-110">Under **Lager** väljer du **Appar**.</span><span class="sxs-lookup"><span data-stu-id="be83d-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="be83d-111">Välj det program du vill uppdatera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be83d-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="be83d-112">Under **Hantera** väljer du **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="be83d-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="be83d-113">Klicka **på Programpaketfil** och bläddra sedan för att ladda upp en ny programpaketfil.</span><span class="sxs-lookup"><span data-stu-id="be83d-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="be83d-114">Välj **Programpaketsfil**.</span><span class="sxs-lookup"><span data-stu-id="be83d-114">Select **App package file**.</span></span>
7. <span data-ttu-id="be83d-115">Välj mappikonen och bläddra till den uppdaterade programfilens plats.</span><span class="sxs-lookup"><span data-stu-id="be83d-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="be83d-116">Välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="be83d-116">Select **Open**.</span></span> <span data-ttu-id="be83d-117">Programinformationen uppdateras med paketinformationen.</span><span class="sxs-lookup"><span data-stu-id="be83d-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="be83d-118">Kontrollera att **programversionen återspeglar** det uppdaterade programpaketet.</span><span class="sxs-lookup"><span data-stu-id="be83d-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="be83d-119">Det uppdaterade programmet distribueras till användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="be83d-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="be83d-120">Uppdatera verksamhetsbaserade appar i Intune</span><span class="sxs-lookup"><span data-stu-id="be83d-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="be83d-121">**Så här uppdaterar du dina verksamhetsbaserade appar i Intune**</span><span class="sxs-lookup"><span data-stu-id="be83d-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="be83d-122">Logga in på [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="be83d-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="be83d-123">Välj **Alla tjänster**  >  **Intune.**</span><span class="sxs-lookup"><span data-stu-id="be83d-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="be83d-124">Intune finns i **avsnittet Övervakning +** Hantering.</span><span class="sxs-lookup"><span data-stu-id="be83d-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="be83d-125">Välj **Klientappar > appar**.</span><span class="sxs-lookup"><span data-stu-id="be83d-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="be83d-126">Leta upp och välj din app i listan med appar.</span><span class="sxs-lookup"><span data-stu-id="be83d-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="be83d-127">Välj **Egenskaper i** bladet **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="be83d-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="be83d-128">Välj **Programpaketsfil**.</span><span class="sxs-lookup"><span data-stu-id="be83d-128">Select **App package file**.</span></span>
7. <span data-ttu-id="be83d-129">Välj mappikonen och bläddra till den uppdaterade programfilens plats.</span><span class="sxs-lookup"><span data-stu-id="be83d-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="be83d-130">Välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="be83d-130">Select **Open**.</span></span> <span data-ttu-id="be83d-131">Programinformationen uppdateras med paketinformationen.</span><span class="sxs-lookup"><span data-stu-id="be83d-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="be83d-132">Kontrollera att **programversionen återspeglar** det uppdaterade programpaketet.</span><span class="sxs-lookup"><span data-stu-id="be83d-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="be83d-133">Återställa en app till en tidigare version</span><span class="sxs-lookup"><span data-stu-id="be83d-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="be83d-134">Om ett fel uppstår när en ny version av ett program har distribuerats kan du återställa till en tidigare version.</span><span class="sxs-lookup"><span data-stu-id="be83d-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="be83d-135">Processen som beskrivs här är för appar där typ anges **Windows en företagsapp** med MSI eller Windows **(Win 32) – förhandsversion**</span><span class="sxs-lookup"><span data-stu-id="be83d-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="be83d-136">**Återställa en verksamhetslinje till en tidigare version**</span><span class="sxs-lookup"><span data-stu-id="be83d-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="be83d-137">Logga in på [Microsoft Hanterat skrivbord administrationsportalen](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="be83d-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="be83d-138">Under **Lager** väljer du **Appar**.</span><span class="sxs-lookup"><span data-stu-id="be83d-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="be83d-139">Välj den app du vill återställa och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be83d-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="be83d-140">Under **Hantera** väljer du **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="be83d-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="be83d-141">För **Windows appprogram med** verksamhetsversionen av MSI väljer du **Appinformation** och sedan Ja under Ignorera **appversion.** </span><span class="sxs-lookup"><span data-stu-id="be83d-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="be83d-142">Om **Windows app (Win 32) –** förhandsgranska appar väljer du **Appinformation,** väljer **Identifieringsregler** och sedan Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="be83d-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="be83d-143">Om det finns en MSI-regel kontrollerar du att **kontrollen av MSI-produkten** är inställd på **Nej.**</span><span class="sxs-lookup"><span data-stu-id="be83d-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="be83d-144">[Upload en tidigare version av programkällfilen i](../get-started/deploy-apps.md) Microsoft Hanterat skrivbord administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="be83d-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

