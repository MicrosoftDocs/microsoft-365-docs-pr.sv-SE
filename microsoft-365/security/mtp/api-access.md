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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719244"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="31210-104">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31210-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="31210-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="31210-105">**Applies to:**</span></span>

- <span data-ttu-id="31210-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31210-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31210-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="31210-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="31210-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="31210-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="31210-109">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="31210-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="31210-110">Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsofts 365 Defender-funktioner fullt ut.</span><span class="sxs-lookup"><span data-stu-id="31210-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="31210-111">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="31210-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="31210-112">Skapa ett Azure Active Directory-program</span><span class="sxs-lookup"><span data-stu-id="31210-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="31210-113">Skaffa en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="31210-113">Get an access token using this application</span></span>
- <span data-ttu-id="31210-114">Använda token för att komma åt Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="31210-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="31210-115">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="31210-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="31210-116">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="31210-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="31210-117">När du har utfört de här stegen kan du komma åt Microsoft 365 Defender API med en viss kontext.</span><span class="sxs-lookup"><span data-stu-id="31210-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="31210-118">Program kontext (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="31210-118">Application context (Recommended)</span></span>

<span data-ttu-id="31210-119">Använd den här kontexten för appar som körs utan en inloggad användare, till exempel bakgrunds tjänster och bakgrunds program.</span><span class="sxs-lookup"><span data-stu-id="31210-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="31210-120">Skapa ett Azure Active Directory-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="31210-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="31210-121">Tilldela önskade behörigheter till programmet.</span><span class="sxs-lookup"><span data-stu-id="31210-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="31210-122">Skapa en-tangenten för programmet.</span><span class="sxs-lookup"><span data-stu-id="31210-122">Create a key for the application.</span></span>
4. <span data-ttu-id="31210-123">Skaffa ett säkerhetstoken med programmet och dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="31210-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="31210-124">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="31210-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="31210-125">Mer information finns i **[skapa en app för att komma åt Microsoft 365 Defender utan en användare](api-create-app-web.md)**.</span><span class="sxs-lookup"><span data-stu-id="31210-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="31210-126">Användar kontext</span><span class="sxs-lookup"><span data-stu-id="31210-126">User context</span></span>

<span data-ttu-id="31210-127">Använd den här kontexten för att utföra åtgärder åt en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="31210-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="31210-128">Skapa ett internt Azure Active Directory-program.</span><span class="sxs-lookup"><span data-stu-id="31210-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="31210-129">Ge programmet rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="31210-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="31210-130">Skaffa en säkerhetstoken med hjälp av användarens autentiseringsuppgifter för programmet.</span><span class="sxs-lookup"><span data-stu-id="31210-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="31210-131">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="31210-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="31210-132">Mer information finns i **[skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md)**.</span><span class="sxs-lookup"><span data-stu-id="31210-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="31210-133">Partner kontext</span><span class="sxs-lookup"><span data-stu-id="31210-133">Partner context</span></span>

<span data-ttu-id="31210-134">Använd den här kontexten om du behöver tillhandahålla en app för många användare i [flera klient organisationer](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span><span class="sxs-lookup"><span data-stu-id="31210-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="31210-135">Skapa ett Azure Active Directory-program med flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="31210-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="31210-136">Ge programmet rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="31210-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="31210-137">Få ett [administrativt medgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje innehavare.</span><span class="sxs-lookup"><span data-stu-id="31210-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="31210-138">Skaffa en säkerhetstoken med hjälp av användarautentiseringsuppgifter baserat på kundens klient organisations-ID.</span><span class="sxs-lookup"><span data-stu-id="31210-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="31210-139">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="31210-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="31210-140">Mer information finns i **[skapa en app med partner åtkomst till Microsoft 365 Defender API: er](api-partner-access.md)**.</span><span class="sxs-lookup"><span data-stu-id="31210-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="31210-141">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="31210-141">Related articles</span></span>

- [<span data-ttu-id="31210-142">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="31210-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="31210-143">OAuth 2,0-auktorisering för användare inloggning och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="31210-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="31210-144">Hantera hemligheter i dina serverprogram med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="31210-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="31210-145">Skapa ett ' Hej världen '-program som använder API för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31210-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
