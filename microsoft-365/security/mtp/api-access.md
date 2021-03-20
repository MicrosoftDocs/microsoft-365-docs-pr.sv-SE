---
title: Åtkomst till Microsoft 365 Defender-API:er
description: Lär dig hur du får tillgång till Microsoft 365 Defender-API:er
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 17fa47fd9998f4097ff323e670b9e442d7126a94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903982"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="7c7ac-104">Åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="7c7ac-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7c7ac-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7c7ac-105">**Applies to:**</span></span>

- <span data-ttu-id="7c7ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c7ac-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c7ac-107">Viss information handlar om en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7c7ac-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7c7ac-109">Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7c7ac-110">De här API:erna hjälper dig att automatisera arbetsflöden och utnyttja funktionerna i Microsoft 365 Defender till fullo.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="7c7ac-111">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="7c7ac-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="7c7ac-112">Skapa ett Azure Active Directory-program</span><span class="sxs-lookup"><span data-stu-id="7c7ac-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="7c7ac-113">Hämta en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="7c7ac-113">Get an access token using this application</span></span>
- <span data-ttu-id="7c7ac-114">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="7c7ac-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="7c7ac-115">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7c7ac-116">Mer information finns i [OAuth 2.0 Auktoriseringskodflöde](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="7c7ac-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7c7ac-117">När du har utfört de här stegen är du redo att använda Microsoft 365 Defender API i ett visst sammanhang.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="7c7ac-118">Programkontext (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="7c7ac-118">Application context (Recommended)</span></span>

<span data-ttu-id="7c7ac-119">Använd det här sammanhanget för appar som körs utan att en inloggad användare finns, till exempel bakgrundstjänster eller bakgrundsljud.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="7c7ac-120">Skapa ett Azure Active Directory-webbprogram.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="7c7ac-121">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="7c7ac-122">Skapa en nyckel för programmet.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-122">Create a key for the application.</span></span>
4. <span data-ttu-id="7c7ac-123">Hämta en säkerhetstoken med hjälp av programmet och dess nyckel.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="7c7ac-124">Använd tokenet för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7c7ac-125">Mer information finns i Skapa **[en app för att komma åt Microsoft 365 Defender utan användare.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="7c7ac-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="7c7ac-126">Användarkontext</span><span class="sxs-lookup"><span data-stu-id="7c7ac-126">User context</span></span>

<span data-ttu-id="7c7ac-127">Använd det här sammanhanget för att utföra åtgärder för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="7c7ac-128">Skapa ett Inbyggt Azure Active Directory-program.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="7c7ac-129">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="7c7ac-130">Hämta en säkerhetstoken med användaruppgifterna för programmet.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="7c7ac-131">Använd tokenet för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7c7ac-132">Mer information finns i Skapa **[en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="7c7ac-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="7c7ac-133">Partnerkontext</span><span class="sxs-lookup"><span data-stu-id="7c7ac-133">Partner context</span></span>

<span data-ttu-id="7c7ac-134">Använd det här sammanhanget när du behöver tillhandahålla ett program för många användare [i flera klientorganisationar.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="7c7ac-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="7c7ac-135">Skapa ett Azure Active Directory-program för flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="7c7ac-136">Tilldela önskad behörighet till programmet.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="7c7ac-137">Få [administratörsmedgivande](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="7c7ac-138">Hämta en säkerhetstoken med användarautentiseringsuppgifter baserat på en kunds klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="7c7ac-139">Använd tokenet för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7c7ac-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7c7ac-140">Mer information finns i Skapa **[en app med partneråtkomst till Microsoft 365 Defender-API:er.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="7c7ac-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7c7ac-141">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7c7ac-141">Related articles</span></span>

- [<span data-ttu-id="7c7ac-142">Översikt över Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="7c7ac-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7c7ac-143">OAuth 2.0-auktorisering för användar logga in och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="7c7ac-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="7c7ac-144">Hantera hemligheter i dina serverappar med Azure-tangentvalvet</span><span class="sxs-lookup"><span data-stu-id="7c7ac-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="7c7ac-145">Skapa programmet Hello world som har åtkomst till Microsoft 365-API:er</span><span class="sxs-lookup"><span data-stu-id="7c7ac-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)