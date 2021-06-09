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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d3f4431825193d189f7ea1d73b6a99163cac428
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843704"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="7666f-104">Få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="7666f-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7666f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7666f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7666f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7666f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7666f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7666f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="7666f-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7666f-108">**Applies to:**</span></span> 
- [<span data-ttu-id="7666f-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7666f-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="7666f-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7666f-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7666f-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7666f-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="7666f-112">Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="7666f-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7666f-113">De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="7666f-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="7666f-114">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="7666f-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7666f-115">Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="7666f-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7666f-116">Titta på den här videon för en snabb överblick över Defender för Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="7666f-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="7666f-117">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="7666f-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="7666f-118">Skapa ett [AAD-program](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="7666f-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="7666f-119">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="7666f-119">Get an access token using this application</span></span>
- <span data-ttu-id="7666f-120">Använda token för att komma åt Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="7666f-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="7666f-121">Du kan komma åt Defender för Endpoint API med **programkontext** eller **användarkontext.**</span><span class="sxs-lookup"><span data-stu-id="7666f-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="7666f-122">**Programkontext: (Rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="7666f-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="7666f-123">Används av appar som körs utan att en inloggad användare finns.</span><span class="sxs-lookup"><span data-stu-id="7666f-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="7666f-124">Exempel: appar som körs som bakgrundstjänster eller som bakgrundstjänster.</span><span class="sxs-lookup"><span data-stu-id="7666f-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="7666f-125">Steg som måste vidtas för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="7666f-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="7666f-126">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="7666f-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="7666f-127">Tilldela önskat tillstånd till programmet, till exempel "Läsaviseringar", "Isolera maskiner".</span><span class="sxs-lookup"><span data-stu-id="7666f-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="7666f-128">Skapa en nyckel för det här programmet.</span><span class="sxs-lookup"><span data-stu-id="7666f-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="7666f-129">Hämta token genom att använda programmet med dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="7666f-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="7666f-130">Använda token för att få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="7666f-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="7666f-131">Mer information finns i Få [åtkomst med programmets kontext.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="7666f-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="7666f-132">**Användarkontext:**</span><span class="sxs-lookup"><span data-stu-id="7666f-132">**User Context:**</span></span> <br>
    <span data-ttu-id="7666f-133">Används för att utföra åtgärder i API:t för en användares räkning.</span><span class="sxs-lookup"><span data-stu-id="7666f-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="7666f-134">Åtgärder att vidta för att komma åt Defender för Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="7666f-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="7666f-135">Skapa det ursprungliga AAD-programmet.</span><span class="sxs-lookup"><span data-stu-id="7666f-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="7666f-136">Tilldela önskat tillstånd till programmet, t.ex. "Läsaviseringar", "Isolera maskiner" osv.</span><span class="sxs-lookup"><span data-stu-id="7666f-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="7666f-137">Hämta token genom att använda programmet med användaruppgifter.</span><span class="sxs-lookup"><span data-stu-id="7666f-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="7666f-138">Använda token för att få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="7666f-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="7666f-139">Mer information finns i Få [åtkomst med användarkontext.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="7666f-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7666f-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7666f-140">Related topics</span></span>
- [<span data-ttu-id="7666f-141">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="7666f-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="7666f-142">Access Microsoft Defender för slutpunkt med programkontext</span><span class="sxs-lookup"><span data-stu-id="7666f-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="7666f-143">Använda Microsoft Defender för slutpunkt med användarkontext</span><span class="sxs-lookup"><span data-stu-id="7666f-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
