---
title: Gå till API för Microsoft 365 Defender
description: 'Lär dig hur du kommer åt Microsoft 365 Defender API: er'
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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845026"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="ec535-104">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec535-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec535-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ec535-105">**Applies to:**</span></span>
- <span data-ttu-id="ec535-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec535-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="ec535-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="ec535-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ec535-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="ec535-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="ec535-109">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="ec535-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ec535-110">Dessa API: er gör det möjligt för dig att automatisera arbets flöden och förnyande baserat på Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="ec535-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="ec535-111">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="ec535-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ec535-112">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="ec535-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="ec535-113">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="ec535-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="ec535-114">Skapa ett AAD-program</span><span class="sxs-lookup"><span data-stu-id="ec535-114">Create an AAD application</span></span>
- <span data-ttu-id="ec535-115">Skaffa en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="ec535-115">Get an access token using this application</span></span>
- <span data-ttu-id="ec535-116">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="ec535-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="ec535-117">Du kan komma åt Microsoft 365 Defender API med **program kontext** eller **användar kontext**.</span><span class="sxs-lookup"><span data-stu-id="ec535-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="ec535-118">**Program kontext: (rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="ec535-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="ec535-119">Används av appar som körs utan en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="ec535-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="ec535-120">appar som körs som bakgrunds tjänster eller bakgrunds program.</span><span class="sxs-lookup"><span data-stu-id="ec535-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="ec535-121">Steg som måste vidtas för att få åtkomst till Microsoft 365 Defender API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="ec535-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="ec535-122">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="ec535-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="ec535-123">Ge den önskade behörigheten till applicationFor exempel, **incident. Read. all** , **AdvancedHunting. Read. all**.</span><span class="sxs-lookup"><span data-stu-id="ec535-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="ec535-124">Skapa en för detta program.</span><span class="sxs-lookup"><span data-stu-id="ec535-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="ec535-125">Hämta token med hjälp av programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="ec535-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="ec535-126">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="ec535-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="ec535-127">Mer information finns i [få åtkomst med program kontext](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="ec535-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="ec535-128">**Användar kontext:**</span><span class="sxs-lookup"><span data-stu-id="ec535-128">**User Context:**</span></span> <br>
    <span data-ttu-id="ec535-129">Används för att utföra åtgärder i API: et åt en användare.</span><span class="sxs-lookup"><span data-stu-id="ec535-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="ec535-130">Steg som måste vidtas för att få åtkomst till Microsoft 365 Defender API med program kontext:</span><span class="sxs-lookup"><span data-stu-id="ec535-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="ec535-131">Skapa AAD-program.</span><span class="sxs-lookup"><span data-stu-id="ec535-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="ec535-132">Ge programmet rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="ec535-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="ec535-133">Till exempel: **incident. Read** , **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="ec535-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="ec535-134">Hämta token med hjälp av programmet med användarautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ec535-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="ec535-135">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="ec535-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="ec535-136">Mer information finns i [få åtkomst med användar kontext](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="ec535-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="ec535-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ec535-137">Related topics</span></span>
- [<span data-ttu-id="ec535-138">Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="ec535-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="ec535-139">Åtkomst till Microsoft 365 Defender med program kontext</span><span class="sxs-lookup"><span data-stu-id="ec535-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="ec535-140">Åtkomst till Microsoft 365 Defender med användar kontext</span><span class="sxs-lookup"><span data-stu-id="ec535-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
