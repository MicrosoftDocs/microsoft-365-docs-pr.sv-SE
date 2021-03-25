---
title: Få åtkomst till API:er för Microsoft Defender för slutpunkt
ms.reviewer: ''
description: Lär dig hur du kan använda API:er för att automatisera arbetsflöden och ny information baserat på Microsoft Defender ATP-funktioner
keywords: apis, api, wdatp, open api, microsoft defender atp api, public api, apis som stöds, aviseringar, enhet, användare, domän, ip, fil, avancerad sökning, fråga
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
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164778"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f4da3-104">Få åtkomst till API:er för Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4da3-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4da3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f4da3-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4da3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4da3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4da3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4da3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="f4da3-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f4da3-108">**Applies to:**</span></span> 
- [<span data-ttu-id="f4da3-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4da3-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="f4da3-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f4da3-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4da3-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f4da3-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="f4da3-112">Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="f4da3-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f4da3-113">De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="f4da3-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="f4da3-114">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="f4da3-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f4da3-115">Mer information finns i [OAuth 2.0 Auktoriseringskodflöde](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f4da3-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f4da3-116">Titta på den här videon för en snabb överblick över Defender för Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="f4da3-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="f4da3-117">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="f4da3-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f4da3-118">Skapa ett AAD-program</span><span class="sxs-lookup"><span data-stu-id="f4da3-118">Create an AAD application</span></span>
- <span data-ttu-id="f4da3-119">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="f4da3-119">Get an access token using this application</span></span>
- <span data-ttu-id="f4da3-120">Använda token för att komma åt Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="f4da3-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="f4da3-121">Du kan komma åt Defender för Endpoint API med **programkontext** eller **användarkontext.**</span><span class="sxs-lookup"><span data-stu-id="f4da3-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="f4da3-122">**Programkontext: (Rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="f4da3-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="f4da3-123">Används av appar som körs utan att en inloggad användare finns.</span><span class="sxs-lookup"><span data-stu-id="f4da3-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="f4da3-124">Exempel: appar som körs som bakgrundstjänster eller som bakgrundstjänster.</span><span class="sxs-lookup"><span data-stu-id="f4da3-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="f4da3-125">Steg som måste vidtas för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="f4da3-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="f4da3-126">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="f4da3-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="f4da3-127">Tilldela önskat tillstånd till programmet, till exempel "Läsaviseringar", "Isolera maskiner".</span><span class="sxs-lookup"><span data-stu-id="f4da3-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="f4da3-128">Skapa en nyckel för det här programmet.</span><span class="sxs-lookup"><span data-stu-id="f4da3-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="f4da3-129">Hämta token genom att använda programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="f4da3-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="f4da3-130">Använda token för att få åtkomst till Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="f4da3-130">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="f4da3-131">Mer information finns i Få [åtkomst med programmets kontext.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="f4da3-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="f4da3-132">**Användarkontext:**</span><span class="sxs-lookup"><span data-stu-id="f4da3-132">**User Context:**</span></span> <br>
    <span data-ttu-id="f4da3-133">Används för att utföra åtgärder i API:t för en användares räkning.</span><span class="sxs-lookup"><span data-stu-id="f4da3-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="f4da3-134">Åtgärder att vidta för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="f4da3-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="f4da3-135">Skapa det ursprungliga AAD-programmet.</span><span class="sxs-lookup"><span data-stu-id="f4da3-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="f4da3-136">Tilldela önskat tillstånd till programmet, t.ex. "Läsaviseringar", "Isolera maskiner" osv.</span><span class="sxs-lookup"><span data-stu-id="f4da3-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="f4da3-137">Hämta token genom att använda programmet med användaruppgifter.</span><span class="sxs-lookup"><span data-stu-id="f4da3-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="f4da3-138">Använda token för att få åtkomst till Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="f4da3-138">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="f4da3-139">Mer information finns i Få [åtkomst med användarkontext.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="f4da3-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f4da3-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f4da3-140">Related topics</span></span>
- [<span data-ttu-id="f4da3-141">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="f4da3-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f4da3-142">Access Microsoft Defender för slutpunkt med programkontext</span><span class="sxs-lookup"><span data-stu-id="f4da3-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="f4da3-143">Använda Microsoft Defender för slutpunkt med användarkontext</span><span class="sxs-lookup"><span data-stu-id="f4da3-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
