---
title: Installera Intune-företagsportal på enheter
description: Information om hur du installerar en företagsportalapp på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, företagsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925780"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="f5ed1-104">Installera Intune-företagsportal på enheter</span><span class="sxs-lookup"><span data-stu-id="f5ed1-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="f5ed1-105">Microsoft Managed Desktop kräver att IT-administratörer installerar Intune-företagsportal för sina användare med Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f5ed1-106">Här är några fördelar för din organisation:</span><span class="sxs-lookup"><span data-stu-id="f5ed1-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="f5ed1-107">Användarna har ett ställe där de kan bläddra bland och installera tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="f5ed1-108">IT-administratörer kan ordna program efter kategorier för sina användare.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="f5ed1-109">För vissa program (till exempel Microsoft Project och Microsoft Visio) krävs en företagsportal för distribution med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="f5ed1-110">IT-administratörer kan anpassa företagsportalen för organisationen.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="f5ed1-111">Det inkluderar brand imaging, lägga till i lokala supportkontakter och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="f5ed1-112">Mer information finns i Konfigurera [appen Microsoft Intune-företagsportal.](/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="f5ed1-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="f5ed1-113">I det här avsnittet finns information om hur du distribuerar Intune-företagsportalen till användare av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f5ed1-114">Den övergripande processen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="f5ed1-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="f5ed1-115">Köp företagsportalen från Microsoft Store för företag och synkronisera med Intune</span><span class="sxs-lookup"><span data-stu-id="f5ed1-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="f5ed1-116">Tilldela företagsportalen till användarna</span><span class="sxs-lookup"><span data-stu-id="f5ed1-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="f5ed1-117">Informera användarna om ändringar</span><span class="sxs-lookup"><span data-stu-id="f5ed1-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="f5ed1-118">Steg 1 – Köp företagsportal från Microsoft Store för företag och synkronisera med Intune</span><span class="sxs-lookup"><span data-stu-id="f5ed1-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="f5ed1-119">Mer information om hur du köper appar och synkroniserar med Intune finns i Microsoft Store för [företag-appar](deploy-apps.md#msfb-apps) i Distribuera appar till *Microsoft Hanterade skrivbordsenheter.*</span><span class="sxs-lookup"><span data-stu-id="f5ed1-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="f5ed1-120">I det här avsnittet finns information om hur du:</span><span class="sxs-lookup"><span data-stu-id="f5ed1-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="f5ed1-121">Köp företagsportal från Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="f5ed1-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="f5ed1-122">Tvinga synkronisering mellan Intune och Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="f5ed1-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="f5ed1-123">Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="f5ed1-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="f5ed1-124">Steg 2 - Tilldela företagsportalen till användarna</span><span class="sxs-lookup"><span data-stu-id="f5ed1-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="f5ed1-125">Efter registreringen i Microsoft Managed Desktop kommer Microsoft Managed Desktop Operations automatiskt att distribuera företagsportalen till klientorganisationen och installera appen på Microsoft Managed Desktop-enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="f5ed1-126">Steg 3 - Meddela användarna om ändring</span><span class="sxs-lookup"><span data-stu-id="f5ed1-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="f5ed1-127">Som IT-administratör för din organisation är det viktigt att berätta för användarna hur företagsportalen i organisationen ska användas.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="f5ed1-128">Microsoft Managed Desktop rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="f5ed1-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="f5ed1-129">Steg för att installera program från företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="f5ed1-130">Mer information finns i [Installera och dela appar på din enhet.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="f5ed1-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="f5ed1-131">Så här skickar du förfrågningar till IT-administratörer för program som inte är tillgängliga för närvarande.</span><span class="sxs-lookup"><span data-stu-id="f5ed1-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="f5ed1-132">Mer information finns i Begära [en app för arbete eller skola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="f5ed1-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="f5ed1-133">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f5ed1-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="f5ed1-134">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="f5ed1-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="f5ed1-135">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="f5ed1-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="f5ed1-136">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="f5ed1-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="f5ed1-137">Distribuera Intune-företagsportal (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="f5ed1-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="f5ed1-138">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="f5ed1-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="f5ed1-139">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="f5ed1-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="f5ed1-140">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="f5ed1-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="f5ed1-141">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="f5ed1-141">Deploy apps</span></span>](deploy-apps.md)