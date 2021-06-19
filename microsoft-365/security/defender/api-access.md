---
title: Få åtkomst Microsoft 365 Defender API:er
description: Lär dig hur du får åtkomst Microsoft 365 Defender API:er
keywords: access, apis, programkontext, användarkontext, aad-program, åtkomsttoken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3cbd329c63d7cf1868083c66919773e14ed51156
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029603"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="21d22-104">Få åtkomst Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="21d22-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="21d22-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="21d22-105">**Applies to:**</span></span>

- <span data-ttu-id="21d22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21d22-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21d22-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="21d22-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="21d22-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="21d22-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="21d22-109">Microsoft 365 Defender mycket av informationen och åtgärderna via ett antal programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="21d22-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="21d22-110">De här API:erna hjälper dig att automatisera arbetsflöden och Microsoft 365 Defender av funktionerna.</span><span class="sxs-lookup"><span data-stu-id="21d22-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="21d22-111">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="21d22-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="21d22-112">Skapa ett Azure Active Directory program</span><span class="sxs-lookup"><span data-stu-id="21d22-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="21d22-113">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="21d22-113">Get an access token using this application</span></span>
- <span data-ttu-id="21d22-114">Använda tokenet för att komma åt Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="21d22-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="21d22-115">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="21d22-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="21d22-116">Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="21d22-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="21d22-117">När du har utfört de här stegen är du redo att använda API:t Microsoft 365 Defender ett visst sammanhang.</span><span class="sxs-lookup"><span data-stu-id="21d22-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="21d22-118">Programkontext (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="21d22-118">Application context (Recommended)</span></span>

<span data-ttu-id="21d22-119">Använd det här sammanhanget för appar som körs utan att en inloggad användare finns, till exempel bakgrundstjänster eller bakgrundsljud.</span><span class="sxs-lookup"><span data-stu-id="21d22-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="21d22-120">Skapa ett Azure Active Directory webbprogram.</span><span class="sxs-lookup"><span data-stu-id="21d22-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="21d22-121">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="21d22-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="21d22-122">Skapa en nyckel för programmet.</span><span class="sxs-lookup"><span data-stu-id="21d22-122">Create a key for the application.</span></span>
4. <span data-ttu-id="21d22-123">Hämta en säkerhetstoken med hjälp av programmet och dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="21d22-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="21d22-124">Använd tokenet för att komma åt Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="21d22-124">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="21d22-125">Mer information finns i Skapa **[ett program för att komma Microsoft 365 Defender utan en användare.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="21d22-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="21d22-126">Användarkontext</span><span class="sxs-lookup"><span data-stu-id="21d22-126">User context</span></span>

<span data-ttu-id="21d22-127">Använd det här sammanhanget för att utföra åtgärder för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="21d22-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="21d22-128">Skapa ett Azure Active Directory inbyggt program.</span><span class="sxs-lookup"><span data-stu-id="21d22-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="21d22-129">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="21d22-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="21d22-130">Hämta en säkerhetstoken med användaruppgifterna för programmet.</span><span class="sxs-lookup"><span data-stu-id="21d22-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="21d22-131">Använd tokenet för att komma åt Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="21d22-131">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="21d22-132">Mer information finns i Skapa **[ett program för att komma Microsoft 365 Defender API:er åt en användare.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="21d22-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="21d22-133">Partnerkontext</span><span class="sxs-lookup"><span data-stu-id="21d22-133">Partner context</span></span>

<span data-ttu-id="21d22-134">Använd det här sammanhanget när du behöver tillhandahålla ett program för många användare [i flera klientorganisationar.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="21d22-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="21d22-135">Skapa ett Azure Active Directory för flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="21d22-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="21d22-136">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="21d22-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="21d22-137">Få [administratörsmedgivande](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="21d22-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="21d22-138">Hämta en säkerhetstoken med användarautentiseringsuppgifter baserat på en kunds klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="21d22-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="21d22-139">Använd tokenet för att komma åt Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="21d22-139">Use the token to access the Microsoft 365 Defender API.</span></span>

<span data-ttu-id="21d22-140">Mer information finns i Skapa **[ett program med partneråtkomst till Microsoft 365 Defender API:er.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="21d22-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="21d22-141">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="21d22-141">Related articles</span></span>

- [<span data-ttu-id="21d22-142">Microsoft 365 Defender API:er – översikt</span><span class="sxs-lookup"><span data-stu-id="21d22-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="21d22-143">OAuth 2.0-auktorisering för användar logga in och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="21d22-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="21d22-144">Hantera hemligheter i dina serverappar med Azure-tangentvalvet</span><span class="sxs-lookup"><span data-stu-id="21d22-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="21d22-145">Skapa programmet Hej världen som har åtkomst till de Microsoft 365 API:er</span><span class="sxs-lookup"><span data-stu-id="21d22-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
