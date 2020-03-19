---
title: Hantera appar på Microsoft Managed Desktop
description: Information om hur du uppdaterar företagsappar som distribueras till Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="931a0-104">Hantera företagsappar på Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="931a0-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="931a0-105">Det finns ett par sätt att hantera appuppdateringar för appar som du har ombord på Microsoft Managed Desktop och distribuerat till dina Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="931a0-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="931a0-106">Du kan göra appuppdateringar i Microsoft Managed Desktop-portalen eller Intune.</span><span class="sxs-lookup"><span data-stu-id="931a0-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="931a0-107">Uppdatera företagsappar på Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="931a0-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="931a0-108">**Så här uppdaterar du dina företagsappar i Microsoft Managed Desktop-portalen**</span><span class="sxs-lookup"><span data-stu-id="931a0-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="931a0-109">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="931a0-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="931a0-110">Välj **Appar**under **Lager**.</span><span class="sxs-lookup"><span data-stu-id="931a0-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="931a0-111">Markera den app som du vill uppdatera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="931a0-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="931a0-112">Välj **Egenskaper**under **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="931a0-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="931a0-113">Klicka på **App paketfil**och bläddra sedan för att ladda upp en ny apppaketfil.</span><span class="sxs-lookup"><span data-stu-id="931a0-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="931a0-114">Välj **Apppaketfil**.</span><span class="sxs-lookup"><span data-stu-id="931a0-114">Select **App package file**.</span></span>
7. <span data-ttu-id="931a0-115">Välj mappikonen och bläddra till platsen för den uppdaterade appfilen.</span><span class="sxs-lookup"><span data-stu-id="931a0-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="931a0-116">Välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="931a0-116">Select **Open**.</span></span> <span data-ttu-id="931a0-117">Appinformationen uppdateras med paketinformationen.</span><span class="sxs-lookup"><span data-stu-id="931a0-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="931a0-118">Kontrollera att **App-versionen** återspeglar det uppdaterade apppaketet.</span><span class="sxs-lookup"><span data-stu-id="931a0-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="931a0-119">Den uppdaterade appen distribueras till användarens enheter.</span><span class="sxs-lookup"><span data-stu-id="931a0-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="931a0-120">Uppdatera företagsappar i Intune</span><span class="sxs-lookup"><span data-stu-id="931a0-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="931a0-121">**Så här uppdaterar du dina företagsappar i Intune**</span><span class="sxs-lookup"><span data-stu-id="931a0-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="931a0-122">Logga in på [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="931a0-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="931a0-123">Välj**Intune för** **alla tjänster** > .</span><span class="sxs-lookup"><span data-stu-id="931a0-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="931a0-124">Intune finns i avsnittet **Övervakning + hantering.**</span><span class="sxs-lookup"><span data-stu-id="931a0-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="931a0-125">Välj **klientappar > appar**.</span><span class="sxs-lookup"><span data-stu-id="931a0-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="931a0-126">Hitta och välj din app i listan över appar.</span><span class="sxs-lookup"><span data-stu-id="931a0-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="931a0-127">Välj **Egenskaper**i bladet **Översikt** .</span><span class="sxs-lookup"><span data-stu-id="931a0-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="931a0-128">Välj **Apppaketfil**.</span><span class="sxs-lookup"><span data-stu-id="931a0-128">Select **App package file**.</span></span>
7. <span data-ttu-id="931a0-129">Välj mappikonen och bläddra till platsen för den uppdaterade appfilen.</span><span class="sxs-lookup"><span data-stu-id="931a0-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="931a0-130">Välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="931a0-130">Select **Open**.</span></span> <span data-ttu-id="931a0-131">Appinformationen uppdateras med paketinformationen.</span><span class="sxs-lookup"><span data-stu-id="931a0-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="931a0-132">Kontrollera att **App-versionen** återspeglar det uppdaterade apppaketet.</span><span class="sxs-lookup"><span data-stu-id="931a0-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="931a0-133">Återställa en app till en tidigare version</span><span class="sxs-lookup"><span data-stu-id="931a0-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="931a0-134">Om det finns ett fel som hittades när en ny version av en app distribueras kan du återställa till en tidigare version.</span><span class="sxs-lookup"><span data-stu-id="931a0-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="931a0-135">Den process som beskrivs här är för appar där typ visas som **Windows MSI-företagsapp** eller **Windows-app (Win 32) - förhandsgranskning**</span><span class="sxs-lookup"><span data-stu-id="931a0-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="931a0-136">**Så här återställer du en företagsapp till en tidigare version**</span><span class="sxs-lookup"><span data-stu-id="931a0-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="931a0-137">Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="931a0-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="931a0-138">Välj **Appar**under **Lager**.</span><span class="sxs-lookup"><span data-stu-id="931a0-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="931a0-139">Välj den app du behöver för att återställa och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="931a0-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="931a0-140">Välj **Egenskaper**under **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="931a0-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="931a0-141">För **Appappar för Windows MSI** väljer du **Appinformation**och väljer sedan **Ja**under **Ignorera appversion**.</span><span class="sxs-lookup"><span data-stu-id="931a0-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="931a0-142">För **Windows-appen (Win 32) – förhandsgranska** appar väljer du **Appinformation,** väljer **Identifieringsregler**och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="931a0-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="931a0-143">Om det finns en MSI-regel kontrollerar du att **MSI:s produktversionskontroll** är inställt på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="931a0-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="931a0-144">[Ladda upp en tidigare version av appkällfilen](../get-started/deploy-apps.md) till Microsoft Managed Desktop Admin portal.</span><span class="sxs-lookup"><span data-stu-id="931a0-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

