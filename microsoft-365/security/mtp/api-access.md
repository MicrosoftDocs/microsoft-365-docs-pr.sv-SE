---
title: 'Komma åt API: erna för skydd mot Microsoft Threat'
description: 'Lär dig hur du kommer åt API: erna för skydd mot Microsoft Threat'
keywords: 'åtkomst, API: er, program kontext, användar kontext, AAD-program, åtkomsttoken'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650596"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="e62a9-104">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="e62a9-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="e62a9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e62a9-105">**Applies to:**</span></span>
- <span data-ttu-id="e62a9-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="e62a9-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e62a9-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="e62a9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e62a9-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="e62a9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="e62a9-109">Microsoft Threat Protection visar mycket av dess data och åtgärder genom en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="e62a9-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="e62a9-110">Dessa API: er gör det möjligt för dig att automatisera arbets flöden och förnyande baserat på Microsoft Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="e62a9-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="e62a9-111">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="e62a9-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="e62a9-112">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="e62a9-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="e62a9-113">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="e62a9-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="e62a9-114">Skapa ett AAD-program</span><span class="sxs-lookup"><span data-stu-id="e62a9-114">Create an AAD application</span></span>
- <span data-ttu-id="e62a9-115">Skaffa en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="e62a9-115">Get an access token using this application</span></span>
- <span data-ttu-id="e62a9-116">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="e62a9-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="e62a9-117">Du kan få åtkomst till Microsoft Threat Protection API med **program kontext** eller **användar kontext**.</span><span class="sxs-lookup"><span data-stu-id="e62a9-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="e62a9-118">**Program kontext: (rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="e62a9-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="e62a9-119">Används av appar som körs utan en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="e62a9-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="e62a9-120">appar som körs som bakgrunds tjänster eller bakgrunds program.</span><span class="sxs-lookup"><span data-stu-id="e62a9-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="e62a9-121">Anvisningar som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="e62a9-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="e62a9-122">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="e62a9-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="e62a9-123">Ge den önskade behörigheten till applicationFor exempel, **incident. Read. all**, **AdvancedHunting. Read. all**.</span><span class="sxs-lookup"><span data-stu-id="e62a9-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="e62a9-124">Skapa en för detta program.</span><span class="sxs-lookup"><span data-stu-id="e62a9-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="e62a9-125">Hämta token med hjälp av programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="e62a9-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="e62a9-126">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="e62a9-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="e62a9-127">Mer information finns i [få åtkomst med program kontext](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="e62a9-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="e62a9-128">**Användar kontext:**</span><span class="sxs-lookup"><span data-stu-id="e62a9-128">**User Context:**</span></span> <br>
    <span data-ttu-id="e62a9-129">Används för att utföra åtgärder i API: et åt en användare.</span><span class="sxs-lookup"><span data-stu-id="e62a9-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="e62a9-130">Steg som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="e62a9-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="e62a9-131">Skapa AAD-program.</span><span class="sxs-lookup"><span data-stu-id="e62a9-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="e62a9-132">Ge programmet rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="e62a9-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="e62a9-133">Till exempel: **incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="e62a9-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="e62a9-134">Hämta token med hjälp av programmet med användarautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e62a9-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="e62a9-135">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="e62a9-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="e62a9-136">Mer information finns i [få åtkomst med användar kontext](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="e62a9-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="e62a9-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e62a9-137">Related topics</span></span>
- [<span data-ttu-id="e62a9-138">API för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="e62a9-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="e62a9-139">Åtkomst till Microsoft Threat Protection med program kontext</span><span class="sxs-lookup"><span data-stu-id="e62a9-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="e62a9-140">Åtkomst till Microsoft Threat Protection med användar kontext</span><span class="sxs-lookup"><span data-stu-id="e62a9-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
