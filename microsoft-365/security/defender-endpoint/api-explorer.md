---
title: API Explorer i Microsoft Defender för Slutpunkt
ms.reviewer: ''
description: Använda API Explorer för att skapa och göra API-frågor, testa och skicka förfrågningar för alla tillgängliga API
keywords: api, explorer, send, request, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769803"
---
# <a name="api-explorer"></a><span data-ttu-id="bc725-104">API Explorer</span><span class="sxs-lookup"><span data-stu-id="bc725-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc725-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bc725-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc725-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bc725-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="bc725-107">Microsoft Defender för slutpunkts-API Explorer är ett verktyg som hjälper dig att utforska olika Defender för slutpunkts-API:er interaktivt.</span><span class="sxs-lookup"><span data-stu-id="bc725-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="bc725-108">MED API Explorer är det enkelt att skapa och göra API-frågor, testa och skicka förfrågningar för tillgängliga Defender för Endpoint API-slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="bc725-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="bc725-109">Använd API Explorer för att vidta åtgärder eller hitta data som kanske ännu inte är tillgängliga i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="bc725-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="bc725-110">Verktyget är användbart under programutveckling.</span><span class="sxs-lookup"><span data-stu-id="bc725-110">The tool is useful during app development.</span></span> <span data-ttu-id="bc725-111">Du kan utföra API-frågor som respekterar dina inställningar för användaråtkomst, vilket minskar behovet av att skapa åtkomsttoken.</span><span class="sxs-lookup"><span data-stu-id="bc725-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="bc725-112">Du kan också använda verktyget för att utforska galleriet med exempelfrågor, kopiera exempel på resultatkoder och generera felsökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="bc725-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="bc725-113">Med API Explorer kan du:</span><span class="sxs-lookup"><span data-stu-id="bc725-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="bc725-114">Kör begäranden för alla metoder och se svar i realtid</span><span class="sxs-lookup"><span data-stu-id="bc725-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="bc725-115">Bläddra snabbt igenom API-exemplen och lär dig vilka parametrar de stöder</span><span class="sxs-lookup"><span data-stu-id="bc725-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="bc725-116">Gör API-anrop enkelt. du behöver inte autentisera utöver hanteringsportalens inloggning</span><span class="sxs-lookup"><span data-stu-id="bc725-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="bc725-117">Access API Explorer</span><span class="sxs-lookup"><span data-stu-id="bc725-117">Access API Explorer</span></span>

<span data-ttu-id="bc725-118">I den vänstra navigeringsmenyn väljer du **Partners & API Explorer**  >  .</span><span class="sxs-lookup"><span data-stu-id="bc725-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="bc725-119">API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="bc725-119">Supported APIs</span></span>

<span data-ttu-id="bc725-120">API Explorer har stöd för alla API:er som erbjuds av Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bc725-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="bc725-121">Listan över API:er som stöds finns i [API:er-dokumentationen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bc725-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="bc725-122">Komma igång med API Explorer</span><span class="sxs-lookup"><span data-stu-id="bc725-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="bc725-123">I den vänstra rutan finns en lista med exempelbegäranden som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="bc725-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="bc725-124">Följ länkarna och klicka på **Kör fråga.**</span><span class="sxs-lookup"><span data-stu-id="bc725-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="bc725-125">Vissa exempel kan kräva att du anger en parameter i URL:en, till exempel {machine- ID}.</span><span class="sxs-lookup"><span data-stu-id="bc725-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="bc725-126">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="bc725-126">FAQ</span></span>

<span data-ttu-id="bc725-127">**Måste jag ha en API-token för att använda API Explorer?**</span><span class="sxs-lookup"><span data-stu-id="bc725-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="bc725-128">Autentiseringsuppgifter för att komma åt ett API behövs inte.</span><span class="sxs-lookup"><span data-stu-id="bc725-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="bc725-129">API Explorer använder Defender för slutpunktshanteringsportal-token när en begäran begärs.</span><span class="sxs-lookup"><span data-stu-id="bc725-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="bc725-130">De inloggade autentiseringsuppgifterna för användare används för att verifiera att API Explorer har behörighet att komma åt data för din räkning.</span><span class="sxs-lookup"><span data-stu-id="bc725-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="bc725-131">Vissa API-begäranden är begränsade baserat på dina RBAC-behörigheter.</span><span class="sxs-lookup"><span data-stu-id="bc725-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="bc725-132">En begäran om att skicka-indikatorn är till exempel begränsad till rollen som säkerhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="bc725-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
