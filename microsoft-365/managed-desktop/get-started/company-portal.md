---
title: Installera Intune företags Portal på enheter
description: Information om hur du installerar företagsportalsappen på Microsoft Managed Station ära enheter
keywords: Microsoft Managed Desktop, Microsoft 365, företags Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939290"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="15356-104">Installera Intune företags Portal på enheter</span><span class="sxs-lookup"><span data-stu-id="15356-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="15356-105">Microsoft Managed Desktop kräver att IT-administratörer installerar Intune företags Portal för sina användare med Microsoft-hanterade Station ära enheter.</span><span class="sxs-lookup"><span data-stu-id="15356-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="15356-106">Här är några fördelar för organisationen:</span><span class="sxs-lookup"><span data-stu-id="15356-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="15356-107">Användare kan bläddra efter och installera tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="15356-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="15356-108">IT-administratörer kan ordna program efter kategorier för sina användare.</span><span class="sxs-lookup"><span data-stu-id="15356-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="15356-109">Vissa program (till exempel Microsoft Project och Microsoft Visio) kräver att företags portalen distribueras med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="15356-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="15356-110">IT-administratörer kan anpassa företags portalen för sin organisation.</span><span class="sxs-lookup"><span data-stu-id="15356-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="15356-111">Detta inkluderar varumärkes bild, tillägg av lokala support kontakter med mera.</span><span class="sxs-lookup"><span data-stu-id="15356-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="15356-112">Mer information finns i [Konfigurera programmet Microsoft Intune-företagsportalsappen](https://docs.microsoft.com/intune/company-portal-app).</span><span class="sxs-lookup"><span data-stu-id="15356-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="15356-113">I det här avsnittet beskrivs hur du distribuerar Intune-företagsportalsappen till dina Microsoft-hanterade Skriv bords användare.</span><span class="sxs-lookup"><span data-stu-id="15356-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="15356-114">Den övergripande processen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="15356-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="15356-115">Köp företags portal från Microsoft Store för företag och synkroniserar med Intune</span><span class="sxs-lookup"><span data-stu-id="15356-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="15356-116">Tilldela företags Portal till dina användare</span><span class="sxs-lookup"><span data-stu-id="15356-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="15356-117">Kommunicera ändringar för användarna</span><span class="sxs-lookup"><span data-stu-id="15356-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="15356-118">Steg 1 – Köp företags portal från Microsoft Store för företag och synkronisera med Intune</span><span class="sxs-lookup"><span data-stu-id="15356-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="15356-119">Information om hur du köper appar och synkroniserar med Intune finns i [Microsoft Store för företag-appar](deploy-apps.md#msfb-apps) i *distribuera program till Microsoft Managed Station ära datorer*.</span><span class="sxs-lookup"><span data-stu-id="15356-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="15356-120">Det här avsnittet innehåller information om hur du:</span><span class="sxs-lookup"><span data-stu-id="15356-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="15356-121">Köp företags portal från Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="15356-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="15356-122">Framtvinga synkronisering mellan Intune och Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="15356-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="15356-123">Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag</span><span class="sxs-lookup"><span data-stu-id="15356-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="15356-124">Steg 2 – tilldela företags Portal till dina användare</span><span class="sxs-lookup"><span data-stu-id="15356-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="15356-125">När du har registrerat dig på Microsoft Managed Desktop kan Microsoft Managed Desktop-operationer automatiskt distribuera företags Portal till klient organisationen och installera programmet på Microsoft Managed Station ära enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="15356-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="15356-126">Steg 3 – meddela användarnas ändringar</span><span class="sxs-lookup"><span data-stu-id="15356-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="15356-127">Som IT-administratör i organisationen är det viktigt att låta användarna veta hur man använder företags portalen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="15356-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="15356-128">Microsoft Managed Station ära datorer rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="15356-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="15356-129">Steg för att installera program från företags portalen.</span><span class="sxs-lookup"><span data-stu-id="15356-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="15356-130">Mer information finns i [Installera och dela appar på din enhet](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span><span class="sxs-lookup"><span data-stu-id="15356-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="15356-131">Skicka förfrågningar till IT-administratörer för program som för tillfället inte är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="15356-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="15356-132">Mer information finns i [begära en app för arbete eller skola](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span><span class="sxs-lookup"><span data-stu-id="15356-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="15356-133">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="15356-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="15356-134">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="15356-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="15356-135">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="15356-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="15356-136">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="15356-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="15356-137">Distribuera Intune-företagsportalsappen (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="15356-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="15356-138">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="15356-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="15356-139">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="15356-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="15356-140">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="15356-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="15356-141">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="15356-141">Deploy apps</span></span>](deploy-apps.md)
