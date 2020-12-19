---
title: 'Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning'
description: Lär dig hur du kommer åt Microsoft 365 Defender API för en användare.
keywords: åtkomst, å användare, API, program, användare, åtkomsttoken, token,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719422"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="7b854-104">Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="7b854-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7b854-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7b854-105">**Applies to:**</span></span>

- <span data-ttu-id="7b854-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b854-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b854-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="7b854-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7b854-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="7b854-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7b854-109">På den här sidan beskrivs hur du skapar ett program för att få programmerings åtkomst till Microsoft 365 Defender åt en och samma användare.</span><span class="sxs-lookup"><span data-stu-id="7b854-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="7b854-110">Om du behöver programmatisk åtkomst till Microsoft 365 Defender utan en definierad användare (om du till exempel skriver en bakgrunds program eller en daemon) läser du [skapa en app för att få åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="7b854-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="7b854-111">Om du behöver ge åtkomst till flera klient organisationer, till exempel om du har en stor organisation eller en grupp kunder – läser du [skapa en app med partner åtkomst till Microsoft 365 Defender API: er](api-partner-access.md). Om du inte är säker på vilken typ av åtkomst du behöver läser du [komma igång](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="7b854-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="7b854-112">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="7b854-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7b854-113">Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="7b854-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="7b854-114">Denna API-åtkomst kräver autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b854-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7b854-115">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="7b854-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7b854-116">I allmänhet måste du göra följande för att använda dessa API:</span><span class="sxs-lookup"><span data-stu-id="7b854-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="7b854-117">Skapa ett Azure Active Directory (Azure AD)-program.</span><span class="sxs-lookup"><span data-stu-id="7b854-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="7b854-118">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="7b854-118">Get an access token using this application.</span></span>
- <span data-ttu-id="7b854-119">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7b854-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7b854-120">I den här artikeln förklarar vi hur du:</span><span class="sxs-lookup"><span data-stu-id="7b854-120">This article explains how to:</span></span>

- <span data-ttu-id="7b854-121">Skapa ett Azure AD-program</span><span class="sxs-lookup"><span data-stu-id="7b854-121">Create an Azure AD application</span></span>
- <span data-ttu-id="7b854-122">Skaffa en åtkomsttoken till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b854-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="7b854-123">Validera token</span><span class="sxs-lookup"><span data-stu-id="7b854-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="7b854-124">När du använder Microsoft 365 Defender API för en användare behöver du rätt program behörigheter och användar behörigheter.</span><span class="sxs-lookup"><span data-stu-id="7b854-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="7b854-125">Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API: t.</span><span class="sxs-lookup"><span data-stu-id="7b854-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="7b854-126">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="7b854-126">Create an app</span></span>

1. <span data-ttu-id="7b854-127">Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="7b854-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="7b854-128">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="7b854-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="7b854-130">Välj ett namn för programmet i formuläret och ange följande information för omdirigerings-URI: n och välj sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="7b854-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Bild av fönstret Skapa programfönster](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="7b854-132">**Program typ:** Offentlig klient</span><span class="sxs-lookup"><span data-stu-id="7b854-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="7b854-133">**OMDIRIGERA URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="7b854-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="7b854-134">På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="7b854-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="7b854-135">Ditt program kan nu komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7b854-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="7b854-136">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="7b854-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="7b854-137">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="7b854-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="7b854-139">Välj **delegerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="7b854-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="7b854-140">Välj relevanta behörigheter för ditt scenario (till exempel **incident. Read**) och välj sedan **Add Permissions**.</span><span class="sxs-lookup"><span data-stu-id="7b854-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="7b854-142">Du måste välja relevanta behörigheter för scenariot.</span><span class="sxs-lookup"><span data-stu-id="7b854-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="7b854-143">*Läs alla händelser* är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="7b854-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="7b854-144">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API som du vill ringa.</span><span class="sxs-lookup"><span data-stu-id="7b854-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="7b854-145">Om du till exempel vill [köra avancerade frågor](api-advanced-hunting.md)väljer du "kör avancerade frågor". Om du vill [isolera en enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)väljer du "isolera datorns tillstånd".</span><span class="sxs-lookup"><span data-stu-id="7b854-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="7b854-146">Välj **ge administratörs medgivande**.</span><span class="sxs-lookup"><span data-stu-id="7b854-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="7b854-147">Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="7b854-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Bild av beviljande behörigheter](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="7b854-149">Spela in ditt program-ID och klient-ID något säkert.</span><span class="sxs-lookup"><span data-stu-id="7b854-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="7b854-150">De visas under **Översikt** på din program sida.</span><span class="sxs-lookup"><span data-stu-id="7b854-150">They're listed under **Overview** on your application page.</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="7b854-152">Skaffa en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="7b854-152">Get an access token</span></span>

<span data-ttu-id="7b854-153">Mer information om Azure Active Directory-tokens finns i [själv studie kursen för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="7b854-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="7b854-154">Skaffa en åtkomsttoken med PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b854-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="7b854-155">Validera token</span><span class="sxs-lookup"><span data-stu-id="7b854-155">Validate the token</span></span>

1. <span data-ttu-id="7b854-156">Kopiera och klistra in token i [JWT](https://jwt.ms) för att avkoda det.</span><span class="sxs-lookup"><span data-stu-id="7b854-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="7b854-157">Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="7b854-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="7b854-158">I följande bild kan du se ett avkodat token från en app, med ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="7b854-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="7b854-160">Använda token för att komma åt Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="7b854-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="7b854-161">Välj det API du vill använda (incidenter eller avancerad jakt).</span><span class="sxs-lookup"><span data-stu-id="7b854-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="7b854-162">Mer information finns i [Microsoft 365 Defender API: n](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="7b854-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="7b854-163">I den http-begäran som du ska skicka kan du ange tillstånds huvudet till `"Bearer" <token>` , *innehavaren* är ett godkännande och *token* som verifierad token.</span><span class="sxs-lookup"><span data-stu-id="7b854-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="7b854-164">Token upphör att gälla inom en timme.</span><span class="sxs-lookup"><span data-stu-id="7b854-164">The token will expire within one hour.</span></span> <span data-ttu-id="7b854-165">Du kan skicka fler än en begäran under tiden med samma token.</span><span class="sxs-lookup"><span data-stu-id="7b854-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="7b854-166">I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med C#**.</span><span class="sxs-lookup"><span data-stu-id="7b854-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="7b854-167">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7b854-167">Related articles</span></span>

- [<span data-ttu-id="7b854-168">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="7b854-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7b854-169">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b854-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7b854-170">Skapa en ' Hej världen '-App</span><span class="sxs-lookup"><span data-stu-id="7b854-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="7b854-171">Skapa en app för åtkomst till Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="7b854-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="7b854-172">Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="7b854-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="7b854-173">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="7b854-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="7b854-174">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="7b854-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="7b854-175">OAuth 2,0-auktorisering för användare inloggning och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="7b854-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
