---
title: Få åtkomst till Microsoft Defender för Endpoint API
ms.reviewer: ''
description: Lär dig hur du kan använda API:er för att automatisera arbetsflöden och ny information baserat på Microsoft Defender för slutpunktsfunktioner
keywords: apis, api, wdatp, open api, microsoft defender för endpoint api, microsoft defender atp, public api, apis som stöds, aviseringar, enhet, användare, domän, ip, fil, avancerad sökning, fråga
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571835"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="6906c-104">Få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="6906c-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6906c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6906c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6906c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6906c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6906c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6906c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="6906c-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6906c-108">**Applies to:**</span></span> 
- [<span data-ttu-id="6906c-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6906c-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="6906c-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6906c-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6906c-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6906c-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="6906c-112">Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="6906c-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6906c-113">De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="6906c-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="6906c-114">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="6906c-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6906c-115">Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="6906c-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6906c-116">Titta på den här videon för en snabb överblick över Defender för Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="6906c-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="6906c-117">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="6906c-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="6906c-118">Skapa ett [AAD-program](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="6906c-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="6906c-119">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="6906c-119">Get an access token using this application</span></span>
- <span data-ttu-id="6906c-120">Använda token för att komma åt Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="6906c-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="6906c-121">Du kan komma åt Defender för Endpoint API med **programkontext** eller **användarkontext.**</span><span class="sxs-lookup"><span data-stu-id="6906c-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="6906c-122">**Programkontext: (Rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="6906c-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="6906c-123">Används av appar som körs utan att en inloggad användare finns.</span><span class="sxs-lookup"><span data-stu-id="6906c-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="6906c-124">Exempel: appar som körs som bakgrundstjänster eller som bakgrundstjänster.</span><span class="sxs-lookup"><span data-stu-id="6906c-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="6906c-125">Steg som måste vidtas för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="6906c-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="6906c-126">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="6906c-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="6906c-127">Tilldela önskat tillstånd till programmet, till exempel "Läsaviseringar", "Isolera maskiner".</span><span class="sxs-lookup"><span data-stu-id="6906c-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="6906c-128">Skapa en nyckel för det här programmet.</span><span class="sxs-lookup"><span data-stu-id="6906c-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="6906c-129">Hämta token genom att använda programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="6906c-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="6906c-130">Använda token för att få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="6906c-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="6906c-131">Mer information finns i Få [åtkomst med programmets kontext.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="6906c-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="6906c-132">**Användarkontext:**</span><span class="sxs-lookup"><span data-stu-id="6906c-132">**User Context:**</span></span> <br>
    <span data-ttu-id="6906c-133">Används för att utföra åtgärder i API:t för en användares räkning.</span><span class="sxs-lookup"><span data-stu-id="6906c-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="6906c-134">Åtgärder att vidta för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="6906c-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="6906c-135">Skapa det ursprungliga AAD-programmet.</span><span class="sxs-lookup"><span data-stu-id="6906c-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="6906c-136">Tilldela önskat tillstånd till programmet, t.ex. "Läsaviseringar", "Isolera maskiner" osv.</span><span class="sxs-lookup"><span data-stu-id="6906c-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="6906c-137">Hämta token genom att använda programmet med användaruppgifter.</span><span class="sxs-lookup"><span data-stu-id="6906c-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="6906c-138">Använda token för att få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="6906c-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="6906c-139">Mer information finns i Få [åtkomst med användarkontext.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="6906c-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6906c-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6906c-140">Related topics</span></span>
- [<span data-ttu-id="6906c-141">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="6906c-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="6906c-142">Access Microsoft Defender för slutpunkt med programkontext</span><span class="sxs-lookup"><span data-stu-id="6906c-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="6906c-143">Använda Microsoft Defender för slutpunkt med användarkontext</span><span class="sxs-lookup"><span data-stu-id="6906c-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
