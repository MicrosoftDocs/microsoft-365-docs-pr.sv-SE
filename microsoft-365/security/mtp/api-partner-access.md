---
title: 'Partner åtkomst via Microsoft 365 Defender API: er'
description: Lär dig hur du skapar en app för att få programmatisk åtkomst till Microsoft 365 Defender åt dina användare.
keywords: partner, Access, API, multi-klient, medgivande, åtkomsttoken, app
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719446"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="9a6ac-104">Skapa en app med partner åtkomst till Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="9a6ac-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9a6ac-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9a6ac-105">**Applies to:**</span></span>

- <span data-ttu-id="9a6ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a6ac-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a6ac-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9a6ac-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9a6ac-109">På den här sidan beskrivs hur du skapar ett Azure Active Directory-program som har programmatisk åtkomst till Microsoft 365 Defender för användare i flera klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="9a6ac-110">Flera klient program är användbara för att betjäna stora användar grupper.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="9a6ac-111">Om du behöver programmatisk åtkomst till Microsoft 365 Defender för en enskild användare läser du [skapa en app för att få åtkomst till microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="9a6ac-112">Om du behöver åtkomst utan någon användare uttryckligen (om du till exempel skriver en bakgrunds program eller en daemon) läser du [skapa en app för att få åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="9a6ac-113">Om du inte är säker på vilken typ av åtkomst du behöver läser du [komma igång](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="9a6ac-114">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9a6ac-115">Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="9a6ac-116">Denna API-åtkomst kräver autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9a6ac-117">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9a6ac-118">I allmänhet måste du göra följande för att använda dessa API:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="9a6ac-119">Skapa ett Azure Active Directory (Azure AD)-program.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="9a6ac-120">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-120">Get an access token using this application.</span></span>
- <span data-ttu-id="9a6ac-121">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9a6ac-122">Eftersom den här appen är en multi-klient organisation behöver du också [Administratörs medgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) från varje klient organisation åt sina användare.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="9a6ac-123">I den här artikeln förklarar vi hur du:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-123">This article explains how to:</span></span>

- <span data-ttu-id="9a6ac-124">Skapa ett Azure AD-program **med flera innehavare**</span><span class="sxs-lookup"><span data-stu-id="9a6ac-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="9a6ac-125">Få ett godkänt medgivande från din användar administratör för din ansökan för att få åtkomst till Microsoft 365 Defender-resurserna som behövs.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="9a6ac-126">Skaffa en åtkomsttoken till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a6ac-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="9a6ac-127">Validera token</span><span class="sxs-lookup"><span data-stu-id="9a6ac-127">Validate the token</span></span>

<span data-ttu-id="9a6ac-128">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9a6ac-129">Dessa API: er hjälper dig att automatisera arbets flöden och förnyas baserat på Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="9a6ac-130">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9a6ac-131">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9a6ac-132">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="9a6ac-133">Skapa ett Azure AD-program **med flera innehavare** .</span><span class="sxs-lookup"><span data-stu-id="9a6ac-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="9a6ac-134">Få godkännande (godkänt) av din användar administratör för ditt program för att få åtkomst till Microsoft 365 Defender-resurser som behövs.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="9a6ac-135">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-135">Get an access token using this application.</span></span>
- <span data-ttu-id="9a6ac-136">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9a6ac-137">Följ de här anvisningarna för att skapa ett Azure AD-program med flera innehavare, skaffa en åtkomsttoken till Microsoft 365 Defender och validera token.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="9a6ac-138">Skapa appen för flera innehavare</span><span class="sxs-lookup"><span data-stu-id="9a6ac-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="9a6ac-139">Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="9a6ac-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="9a6ac-140">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9a6ac-142">I registrerings formuläret:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-142">In the registration form:</span></span>

   - <span data-ttu-id="9a6ac-143">Välj ett namn för programmet.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="9a6ac-144">Från **konto typer som stöds** väljer du **konton i valfri organisations katalog (vilken Azure AD-katalog)-multiinnehavare**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="9a6ac-145">Fyll i avsnittet **OMDIRIGERA URI** .</span><span class="sxs-lookup"><span data-stu-id="9a6ac-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="9a6ac-146">Välj Skriv **webbplats** och ge omdirigerings-URI som **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="9a6ac-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="9a6ac-147">När du har fyllt i formuläret väljer du **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-147">After you're done filling out the form, select **Register**.</span></span>

   ![Bild av registret registrera ett ansöknings formulär](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="9a6ac-149">På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="9a6ac-150">Ditt program kan nu komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="9a6ac-151">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="9a6ac-152">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="9a6ac-154">Välj **program behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-154">Select **Application permissions**.</span></span> <span data-ttu-id="9a6ac-155">Välj relevanta behörigheter för ditt scenario (till exempel **incident. Read. all**) och välj sedan **Add Permissions**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="9a6ac-157">Du måste välja relevanta behörigheter för scenariot.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="9a6ac-158">*Läs alla händelser* är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="9a6ac-159">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API som du vill ringa.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="9a6ac-160">Om du till exempel vill [köra avancerade frågor](api-advanced-hunting.md)väljer du "kör avancerade frågor". Om du vill [isolera en enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)väljer du "isolera datorns tillstånd".</span><span class="sxs-lookup"><span data-stu-id="9a6ac-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="9a6ac-161">Välj **ge administratörs medgivande**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="9a6ac-162">Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

7. <span data-ttu-id="9a6ac-164">Om du vill lägga till en hemlighet i programmet väljer du **certifikat & hemligheter**, lägger till en beskrivning till hemligheten och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9a6ac-165">När du har valt **Lägg till** väljer **du kopiera det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="9a6ac-166">Du kommer inte att kunna hämta det hemliga värdet efter att du har lämnat.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

8. <span data-ttu-id="9a6ac-168">Spela in ditt program-ID och klient-ID något säkert.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="9a6ac-169">De visas under **Översikt** på din program sida.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-169">They're listed under **Overview** on your application page.</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="9a6ac-171">Lägg till programmet i användarens innehavare.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="9a6ac-172">Eftersom ditt program interagerar med Microsoft 365 Defender åt användarna måste det godkännas för varje klient organisation som ska använda det.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="9a6ac-173">En **Global administratör** från användarens innehavare måste visa medgivande länken och godkänna ditt program.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="9a6ac-174">Godkännande länken är av formen:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="9a6ac-175">Siffrorna `00000000-0000-0000-0000-000000000000` bör ersättas med ditt program-ID.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="9a6ac-176">När du har klickat på länken för godkännande loggar du in med den globala administratören för användarens klient organisation och godkänner programmet.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Bild av godkännande](../../media/app-consent-partner.png)

   <span data-ttu-id="9a6ac-178">Du måste också be din användare om sitt klient-ID.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="9a6ac-179">Klient-ID är en av de identifierare som används för att hämta åtkomst-token.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="9a6ac-180">**Åstadkomma!**</span><span class="sxs-lookup"><span data-stu-id="9a6ac-180">**Done!**</span></span> <span data-ttu-id="9a6ac-181">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="9a6ac-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="9a6ac-182">Se exemplen nedan för hämtning av token och verifiering.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="9a6ac-183">Skaffa en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="9a6ac-183">Get an access token</span></span>

<span data-ttu-id="9a6ac-184">Mer information om Azure AD-token finns i [Azure AD själv studie kurs](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a6ac-185">Även om exemplen i det här avsnittet uppmanar dig att klistra in hemliga värden i test syfte bör du **aldrig hardcode hemligheter** i ett program som körs i produktion.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="9a6ac-186">En tredje part kan använda din hemlighet för att komma åt resurser.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="9a6ac-187">Du kan hålla dina programs hemligheter säkra genom att använda [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="9a6ac-188">Ett praktiskt exempel på hur du kan skydda din app finns i [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="9a6ac-189">I följande exempel använder du en användares klient-ID för att testa att skriptet fungerar.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="9a6ac-190">Skaffa en åtkomsttoken med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a6ac-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="9a6ac-191">Skaffa en åtkomsttoken med C\#</span><span class="sxs-lookup"><span data-stu-id="9a6ac-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="9a6ac-192">Följande kod har testats med NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="9a6ac-193">Skapa ett nytt konsol program.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-193">Create a new console application.</span></span>
1. <span data-ttu-id="9a6ac-194">Installera NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="9a6ac-195">Lägg till följande rad:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="9a6ac-196">Kopiera och klistra in följande kod i appen (Glöm inte att uppdatera de tre variablerna: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="9a6ac-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="9a6ac-197">Skaffa en åtkomsttoken med python</span><span class="sxs-lookup"><span data-stu-id="9a6ac-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="9a6ac-198">Skaffa en åtkomsttoken med hjälp av sväng</span><span class="sxs-lookup"><span data-stu-id="9a6ac-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="9a6ac-199">Sväng är förinstallerat på Windows 10, version 1803 och senare.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="9a6ac-200">För andra versioner av Windows laddar du ned och installerar verktyget direkt från den [officiella platsen](https://curl.haxx.se/windows/).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="9a6ac-201">Öppna en kommando tolk och ange CLIENT_ID till ditt Azure-program-ID.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="9a6ac-202">Ange CLIENT_SECRET till din Azure Application Secret.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="9a6ac-203">Ange TENANT_ID till Azure TENANT ID för den användare som vill använda din app för att komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="9a6ac-204">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="9a6ac-205">Ett lyckat svar ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="9a6ac-206">Validera token</span><span class="sxs-lookup"><span data-stu-id="9a6ac-206">Validate the token</span></span>

1. <span data-ttu-id="9a6ac-207">Kopiera och klistra in din token i [JSON Web token validator-webbplatsen, JWT,](https://jwt.ms) för att avkoda den.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="9a6ac-208">Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="9a6ac-209">I följande bild kan du se ett avkodat token från en app, med ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="9a6ac-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="9a6ac-211">Använda token för att komma åt Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="9a6ac-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="9a6ac-212">Välj det API du vill använda (incidenter eller avancerad jakt).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="9a6ac-213">Mer information finns i [Microsoft 365 Defender API: n](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="9a6ac-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="9a6ac-214">I den http-begäran som du ska skicka kan du ange tillstånds huvudet till `"Bearer" <token>` , *innehavaren* är ett godkännande och *token* som verifierad token.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="9a6ac-215">Token upphör att gälla inom en timme.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-215">The token will expire within one hour.</span></span> <span data-ttu-id="9a6ac-216">Du kan skicka fler än en begäran under tiden med samma token.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="9a6ac-217">I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med C#**.</span><span class="sxs-lookup"><span data-stu-id="9a6ac-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="9a6ac-218">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9a6ac-218">Related articles</span></span>

- [<span data-ttu-id="9a6ac-219">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="9a6ac-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="9a6ac-220">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a6ac-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9a6ac-221">Skapa ett ' Hej världen '-program</span><span class="sxs-lookup"><span data-stu-id="9a6ac-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="9a6ac-222">Skapa en app för åtkomst till Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="9a6ac-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9a6ac-223">Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="9a6ac-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="9a6ac-224">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="9a6ac-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="9a6ac-225">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="9a6ac-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="9a6ac-226">Hantera hemligheter i dina serverprogram med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9a6ac-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="9a6ac-227">OAuth 2,0-auktorisering för användare inloggning och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="9a6ac-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
