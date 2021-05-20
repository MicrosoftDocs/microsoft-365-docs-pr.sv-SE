---
title: Få åtkomst till Microsoft Defender för Endpoint API
ms.reviewer: ''
description: Lär dig hur du kan använda API:er för att automatisera arbetsflöden och innovera baserat på Microsoft Defender för slutpunktsfunktioner
keywords: apis, api, wdatp, open api, microsoft defender för endpoint api, microsoft defender atp, public api, stöds apis, varningar, enhet, användare, domän, ip, fil, avancerad jakt, fråga
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
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="26c5d-104">Få åtkomst till Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="26c5d-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26c5d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="26c5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="26c5d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="26c5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="26c5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26c5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="26c5d-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="26c5d-108">**Applies to:**</span></span> 
- [<span data-ttu-id="26c5d-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="26c5d-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="26c5d-110">Vill du uppleva Microsoft Defender för Endpoint?</span><span class="sxs-lookup"><span data-stu-id="26c5d-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="26c5d-111">Registrera dig för en gratis provperiod.</span><span class="sxs-lookup"><span data-stu-id="26c5d-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="26c5d-112">Defender for Endpoint exponerar mycket av sina data och åtgärder via en uppsättning programmatiska API:er.</span><span class="sxs-lookup"><span data-stu-id="26c5d-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="26c5d-113">Dessa API:er gör att du kan automatisera arbetsflöden och förnya baserat på Defender för Endpoint-funktioner.</span><span class="sxs-lookup"><span data-stu-id="26c5d-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="26c5d-114">API-åtkomsten kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="26c5d-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="26c5d-115">Mer information finns i [OAuth 2.0 Auktoriseringskod Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="26c5d-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="26c5d-116">Titta på den här videon för en snabb översikt över Defender for Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="26c5d-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="26c5d-117">I allmänhet måste du vidta följande steg för att använda API: erna:</span><span class="sxs-lookup"><span data-stu-id="26c5d-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="26c5d-118">Skapa ett [AAD-program](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="26c5d-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="26c5d-119">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="26c5d-119">Get an access token using this application</span></span>
- <span data-ttu-id="26c5d-120">Använda token för att komma åt Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="26c5d-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="26c5d-121">Du kan komma åt Defender för slutpunkts-API:et **med programkontext** eller **användarkontext**.</span><span class="sxs-lookup"><span data-stu-id="26c5d-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="26c5d-122">**Programkontext: (rekommenderas)**</span><span class="sxs-lookup"><span data-stu-id="26c5d-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="26c5d-123">Används av appar som körs utan att en inloggad användare är närvarande.</span><span class="sxs-lookup"><span data-stu-id="26c5d-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="26c5d-124">till exempel appar som körs som bakgrundstjänster eller demoner.</span><span class="sxs-lookup"><span data-stu-id="26c5d-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="26c5d-125">Steg som måste vidtas för att komma åt Defender for Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="26c5d-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="26c5d-126">Skapa ett AAD-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="26c5d-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="26c5d-127">Tilldela önskad behörighet till programmet, till exempel "Läs aviseringar", "Isolera datorer".</span><span class="sxs-lookup"><span data-stu-id="26c5d-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="26c5d-128">Skapa en nyckel för det här programmet.</span><span class="sxs-lookup"><span data-stu-id="26c5d-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="26c5d-129">Hämta token med hjälp av programmet med nyckeln.</span><span class="sxs-lookup"><span data-stu-id="26c5d-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="26c5d-130">Använda token för att komma åt MICROSOFT Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="26c5d-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="26c5d-131">Mer information finns i [Få åtkomst med programkontext .](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="26c5d-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="26c5d-132">**Användarkontext:**</span><span class="sxs-lookup"><span data-stu-id="26c5d-132">**User Context:**</span></span> <br>
    <span data-ttu-id="26c5d-133">Används för att utföra åtgärder i API:et för en användares räkning.</span><span class="sxs-lookup"><span data-stu-id="26c5d-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="26c5d-134">Steg att vidta för att komma åt Defender for Endpoint API med programkontext:</span><span class="sxs-lookup"><span data-stu-id="26c5d-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="26c5d-135">Skapa AAD Native-Application.</span><span class="sxs-lookup"><span data-stu-id="26c5d-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="26c5d-136">Tilldela önskad behörighet till programmet, t.ex. "Läs varningar", "Isolera maskiner" etc.</span><span class="sxs-lookup"><span data-stu-id="26c5d-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="26c5d-137">Hämta token med hjälp av programmet med användarautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="26c5d-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="26c5d-138">Använda token för att komma åt MICROSOFT Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="26c5d-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="26c5d-139">Mer information finns i [Få åtkomst med användarkontext .](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="26c5d-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="26c5d-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="26c5d-140">Related topics</span></span>
- [<span data-ttu-id="26c5d-141">Microsoft Defender för API:er för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="26c5d-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="26c5d-142">Komma åt Microsoft Defender för slutpunkt med programkontext</span><span class="sxs-lookup"><span data-stu-id="26c5d-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="26c5d-143">Komma åt Microsoft Defender för slutpunkt med användarkontext</span><span class="sxs-lookup"><span data-stu-id="26c5d-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
