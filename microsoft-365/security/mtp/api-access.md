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
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197887"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="95d9f-104">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="95d9f-104">Access the Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="95d9f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="95d9f-105">**Applies to:**</span></span>
- <span data-ttu-id="95d9f-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="95d9f-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="95d9f-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="95d9f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="95d9f-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="95d9f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="95d9f-109">Microsoft Threat Protection visar mycket av dess data och åtgärder genom en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="95d9f-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="95d9f-110">Dessa API: er gör det möjligt för dig att automatisera arbets flöden och förnyande baserat på Microsoft Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="95d9f-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="95d9f-111">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="95d9f-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="95d9f-112">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="95d9f-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="95d9f-113">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="95d9f-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="95d9f-114">Skapa ett AAD-program</span><span class="sxs-lookup"><span data-stu-id="95d9f-114">Create an AAD application</span></span>
- <span data-ttu-id="95d9f-115">Skaffa en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="95d9f-115">Get an access token using this application</span></span>
- <span data-ttu-id="95d9f-116">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="95d9f-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="95d9f-117">Du kan få åtkomst till Microsoft Threat Protection API med **program kontext** eller **användar kontext**.</span><span class="sxs-lookup"><span data-stu-id="95d9f-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="95d9f-118">**Program kontext: (rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="95d9f-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="95d9f-119">Används av appar som körs utan en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="95d9f-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="95d9f-120">appar som körs som bakgrunds tjänster eller bakgrunds program.</span><span class="sxs-lookup"><span data-stu-id="95d9f-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="95d9f-121">Anvisningar som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="95d9f-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="95d9f-122">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="95d9f-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="95d9f-123">Ge den önskade behörigheten till applicationFor exempel, **incident. Read. all**, **AdvancedHunting. Read. all**.</span><span class="sxs-lookup"><span data-stu-id="95d9f-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="95d9f-124">Skapa en för detta program.</span><span class="sxs-lookup"><span data-stu-id="95d9f-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="95d9f-125">Hämta token med hjälp av programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="95d9f-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="95d9f-126">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="95d9f-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="95d9f-127">Mer information finns i [få åtkomst med program kontext](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="95d9f-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="95d9f-128">**Användar kontext:**</span><span class="sxs-lookup"><span data-stu-id="95d9f-128">**User Context:**</span></span> <br>
    <span data-ttu-id="95d9f-129">Används för att utföra åtgärder i API: et åt en användare.</span><span class="sxs-lookup"><span data-stu-id="95d9f-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="95d9f-130">Steg som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="95d9f-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="95d9f-131">Skapa AAD-program.</span><span class="sxs-lookup"><span data-stu-id="95d9f-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="95d9f-132">Ge programmet rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="95d9f-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="95d9f-133">Till exempel: **incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="95d9f-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="95d9f-134">Hämta token med hjälp av programmet med användarautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="95d9f-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="95d9f-135">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="95d9f-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="95d9f-136">Mer information finns i [få åtkomst med användar kontext](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="95d9f-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="95d9f-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="95d9f-137">Related topics</span></span>
- [<span data-ttu-id="95d9f-138">API för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="95d9f-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="95d9f-139">Åtkomst till Microsoft Threat Protection med program kontext</span><span class="sxs-lookup"><span data-stu-id="95d9f-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="95d9f-140">Åtkomst till Microsoft Threat Protection med användar kontext</span><span class="sxs-lookup"><span data-stu-id="95d9f-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
