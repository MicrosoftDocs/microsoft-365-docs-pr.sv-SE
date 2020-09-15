---
title: 'Partner åtkomst via API: er för Microsoft Threat Protection'
description: Lär dig hur du skapar ett AAD-program för att få program mässig åtkomst till skydd mot Microsoft Threat för dina kunders räkning
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
ms.openlocfilehash: d78996c0cd37a6b82edde52367b04647560d5cf7
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650567"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a><span data-ttu-id="fd172-104">Partner åtkomst via API: er för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fd172-104">Partner access through Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="fd172-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fd172-105">**Applies to:**</span></span>
- <span data-ttu-id="fd172-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="fd172-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="fd172-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="fd172-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fd172-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="fd172-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="fd172-109">På den här sidan beskrivs hur du skapar ett AAD-program för att få programmatisk åtkomst till Microsoft Threat Protection åt dina kunder.</span><span class="sxs-lookup"><span data-stu-id="fd172-109">This page describes how to create an AAD application to get programmatic access to Microsoft Threat Protection on behalf of your customers.</span></span>

<span data-ttu-id="fd172-110">Microsoft Threat Protection visar mycket av dess data och åtgärder genom en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="fd172-110">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="fd172-111">Dessa API: er kommer att hjälpa dig att automatisera arbets flöden och förnyas baserat på Microsoft Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="fd172-111">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="fd172-112">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="fd172-112">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="fd172-113">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="fd172-113">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="fd172-114">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="fd172-114">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="fd172-115">Skapa ett AAD **-program med flera innehavare** .</span><span class="sxs-lookup"><span data-stu-id="fd172-115">Create a **multi-tenant** AAD application.</span></span>
- <span data-ttu-id="fd172-116">Få godkännande (godkänt) av din kund administratör för din ansökan för att få åtkomst till Microsofts hot Protection-resurser.</span><span class="sxs-lookup"><span data-stu-id="fd172-116">Get authorized (consent) by your customer administrator for your application to access Microsoft Threat Protection resources it needs.</span></span>
- <span data-ttu-id="fd172-117">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="fd172-117">Get an access token using this application.</span></span>
- <span data-ttu-id="fd172-118">Använd token för att få åtkomst till Microsoft Threat Protection API.</span><span class="sxs-lookup"><span data-stu-id="fd172-118">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="fd172-119">Följ de här anvisningarna för att skapa ett AAD-program, skaffa en åtkomsttoken till Microsoft Threat Protection och validera token.</span><span class="sxs-lookup"><span data-stu-id="fd172-119">The following steps with guide you how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="fd172-120">Skapa appen för flera innehavare</span><span class="sxs-lookup"><span data-stu-id="fd172-120">Create the multi-tenant app</span></span>

1. <span data-ttu-id="fd172-121">Logga in på din [Azure-klient organisation](https://portal.azure.com) med en användare som har rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="fd172-121">Log on to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="fd172-122">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="fd172-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="fd172-124">I registrerings formuläret:</span><span class="sxs-lookup"><span data-stu-id="fd172-124">In the registration form:</span></span>

    - <span data-ttu-id="fd172-125">Välj ett namn för programmet.</span><span class="sxs-lookup"><span data-stu-id="fd172-125">Choose a name for your application.</span></span>

    - <span data-ttu-id="fd172-126">Konto typer som stöds-konton i valfri organisations katalog.</span><span class="sxs-lookup"><span data-stu-id="fd172-126">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="fd172-127">Omdirigera URI-typ: webb, URI: https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="fd172-127">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Bild av Microsoft Azure partner program registrering](../../media/atp-api-new-app-partner.png)


4. <span data-ttu-id="fd172-129">Ge ditt program åtkomst till Microsoft Threat Protection och tilldela det med den minsta behörighet som krävs för att slutföra integrationen.</span><span class="sxs-lookup"><span data-stu-id="fd172-129">Allow your Application to access Microsoft Threat Protection and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="fd172-130">På din program sida klickar du på **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** > ange **Microsoft Threat Protection** och klicka på **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="fd172-130">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft Threat Protection** and click on **Microsoft Threat Protection**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="fd172-131">Microsoft Threat Protection visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="fd172-131">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="fd172-132">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="fd172-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="fd172-134">Begära API-behörigheter</span><span class="sxs-lookup"><span data-stu-id="fd172-134">Request API permissions</span></span>

   <span data-ttu-id="fd172-135">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API du är intresse rad av.</span><span class="sxs-lookup"><span data-stu-id="fd172-135">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span> 

   <span data-ttu-id="fd172-136">I följande exempel kommer vi att använda behörigheten **"Läs alla händelser"** :</span><span class="sxs-lookup"><span data-stu-id="fd172-136">In the following example we will use **'Read all incidents'** permission:</span></span>

   <span data-ttu-id="fd172-137">Välj incidenter för **program behörigheter**  >  **. Läs alla** > Klicka på **Lägg till behörigheter**</span><span class="sxs-lookup"><span data-stu-id="fd172-137">Choose **Application permissions** > **Incidents.Read.All** > Click on **Add permissions**</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)


5. <span data-ttu-id="fd172-139">Klicka på **bevilja medgivande**</span><span class="sxs-lookup"><span data-stu-id="fd172-139">Click **Grant consent**</span></span>

    >[!NOTE]
    ><span data-ttu-id="fd172-140">Varje gång du lägger till behörighet måste du klicka på **bevilja medgivande** för att den nya behörigheten ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="fd172-140">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

6. <span data-ttu-id="fd172-142">Lägg till en hemlighet i programmet.</span><span class="sxs-lookup"><span data-stu-id="fd172-142">Add a secret to the application.</span></span>

    - <span data-ttu-id="fd172-143">Klicka på **certifikat & hemligheter**, Lägg till en beskrivning till hemligheten och klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fd172-143">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="fd172-144">När du har valt **Lägg till** **kopierar du det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="fd172-144">After selecting **Add**, **copy the generated secret value**.</span></span> <span data-ttu-id="fd172-145">Du kommer inte att kunna hämta efter att du har lämnat!</span><span class="sxs-lookup"><span data-stu-id="fd172-145">You won't be able to retrieve after you leave!</span></span>

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

7. <span data-ttu-id="fd172-147">Skriv in ditt program-ID:</span><span class="sxs-lookup"><span data-stu-id="fd172-147">Write down your application ID:</span></span>

   - <span data-ttu-id="fd172-148">Gå till **Översikt** och kopiera följande på program sidan:</span><span class="sxs-lookup"><span data-stu-id="fd172-148">On your application page, go to **Overview** and copy the following:</span></span>

   ![Bild av ID för skapat program](../../media/app-id.png)

8. <span data-ttu-id="fd172-150">Lägg till ansökan till kund innehavaren.</span><span class="sxs-lookup"><span data-stu-id="fd172-150">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="fd172-151">Du behöver programmet vara godkänt i varje kund innehavare för att du ska kunna använda det.</span><span class="sxs-lookup"><span data-stu-id="fd172-151">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="fd172-152">Det beror på att ditt program interagerar med Microsoft Threat Protection-programmet åt din kund.</span><span class="sxs-lookup"><span data-stu-id="fd172-152">This is because your application interacts with Microsoft Threat Protection application on behalf of your customer.</span></span>

    <span data-ttu-id="fd172-153">En användare med **Global administratör** från kundens klient organisation måste klicka på medgivande länken och godkänna programmet.</span><span class="sxs-lookup"><span data-stu-id="fd172-153">A user with **Global Administrator** from your customer's tenant need to click the consent link and approve your application.</span></span>

    <span data-ttu-id="fd172-154">Godkännande länken är av formen:</span><span class="sxs-lookup"><span data-stu-id="fd172-154">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="fd172-155">Där 00000000-0000-0000-0000-000000000000 ska ersättas med ditt program-ID</span><span class="sxs-lookup"><span data-stu-id="fd172-155">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="fd172-156">När du har klickat på länken för godkännande loggar du in på den globala administratören för kundens klient organisation och godkänner programmet.</span><span class="sxs-lookup"><span data-stu-id="fd172-156">After clicking on the consent link, login with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![Bild av godkännande](../../media/app-consent-partner.png)

    <span data-ttu-id="fd172-158">Dessutom måste du be din kund om sitt klient-ID och spara det för framtida bruk när du hämtar token.</span><span class="sxs-lookup"><span data-stu-id="fd172-158">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="fd172-159">**Åstadkomma!**</span><span class="sxs-lookup"><span data-stu-id="fd172-159">**Done!**</span></span> <span data-ttu-id="fd172-160">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="fd172-160">You have successfully registered an application!</span></span> 
- <span data-ttu-id="fd172-161">Se exemplen nedan för hämtning av token och verifiering.</span><span class="sxs-lookup"><span data-stu-id="fd172-161">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-examples"></a><span data-ttu-id="fd172-162">Få ett exempel på en åtkomsttoken:</span><span class="sxs-lookup"><span data-stu-id="fd172-162">Get an access token examples:</span></span>

>[!NOTE]
> <span data-ttu-id="fd172-163">För att få till gång till din kunds räkning kan du använda kundens klient organisations-ID på följande token-hämtningar.</span><span class="sxs-lookup"><span data-stu-id="fd172-163">To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="fd172-164">Mer information om AAD-token finns i [artikeln om AAD-vägledning](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="fd172-164">For more details on AAD token, refer to [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fd172-165">Använda PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd172-165">Using PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a><span data-ttu-id="fd172-166">Använda C#:</span><span class="sxs-lookup"><span data-stu-id="fd172-166">Using C#:</span></span>

><span data-ttu-id="fd172-167">Koden nedan har testats med NuGet Microsoft. IdentityModel. clients. ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="fd172-167">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="fd172-168">Skapa ett nytt konsol program</span><span class="sxs-lookup"><span data-stu-id="fd172-168">Create a new Console Application</span></span>
- <span data-ttu-id="fd172-169">Installera NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="fd172-169">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="fd172-170">Lägg till nedan med</span><span class="sxs-lookup"><span data-stu-id="fd172-170">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="fd172-171">Kopiera/klistra in koden nedan i programmet (Glöm inte att uppdatera tre variabler: ```tenantId, appId, appSecret``` )</span><span class="sxs-lookup"><span data-stu-id="fd172-171">Copy/Paste the below code in your application (do not forget to update the 3 variables: ```tenantId, appId, appSecret```)</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a><span data-ttu-id="fd172-172">Använda sväng</span><span class="sxs-lookup"><span data-stu-id="fd172-172">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="fd172-173">Proceduren nedan som ska vara en sväng för Windows är redan installerad på datorn</span><span class="sxs-lookup"><span data-stu-id="fd172-173">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="fd172-174">Öppna ett kommando fönster</span><span class="sxs-lookup"><span data-stu-id="fd172-174">Open a command window</span></span>
- <span data-ttu-id="fd172-175">Ange CLIENT_ID till ditt Azure-program-ID</span><span class="sxs-lookup"><span data-stu-id="fd172-175">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="fd172-176">Ange CLIENT_SECRET till din Azure Application Secret</span><span class="sxs-lookup"><span data-stu-id="fd172-176">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="fd172-177">Ange TENANT_ID till det Azure klient organisations-ID: t för kunden som vill använda ditt program för att få åtkomst till Microsoft Threat Protection-programmet</span><span class="sxs-lookup"><span data-stu-id="fd172-177">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Threat Protection application</span></span>
- <span data-ttu-id="fd172-178">Kör kommandot nedan:</span><span class="sxs-lookup"><span data-stu-id="fd172-178">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="fd172-179">Du får ett svar på formuläret:</span><span class="sxs-lookup"><span data-stu-id="fd172-179">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="fd172-180">Validera token</span><span class="sxs-lookup"><span data-stu-id="fd172-180">Validate the token</span></span>

<span data-ttu-id="fd172-181">Sanity kontrol lera att du har rätt token:</span><span class="sxs-lookup"><span data-stu-id="fd172-181">Sanity check to make sure you got a correct token:</span></span>

- <span data-ttu-id="fd172-182">Kopiera/klistra in i [JWT](https://jwt.ms) det token du får i föregående steg för att avkoda det</span><span class="sxs-lookup"><span data-stu-id="fd172-182">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="fd172-183">Verifiera att du får en "roles"-anspråk med de önskade behörigheterna</span><span class="sxs-lookup"><span data-stu-id="fd172-183">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="fd172-184">I skärm bilden nedan kan du se ett avkodat token som hämtats från ett program med flera behörigheter till Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="fd172-184">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to Microsoft Threat Protection:</span></span>
- <span data-ttu-id="fd172-185">"Tid"-anspråk är det klient-ID som token tillhör.</span><span class="sxs-lookup"><span data-stu-id="fd172-185">The "tid" claim is the tenant ID the token belongs to.</span></span>

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="fd172-187">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="fd172-187">Use the token to access Microsoft Threat Protection API</span></span>

- <span data-ttu-id="fd172-188">Välj det API du vill använda för mer information, se [API: er som stöds av Microsoft Threat Protection](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="fd172-188">Choose the API you want to use, for more information, see [Supported Microsoft Threat Protection APIs](api-supported.md)</span></span>
- <span data-ttu-id="fd172-189">Ange auktorisations huvudet i http-begäran som du skickar till "Bearer {token}" (innehavaren är godkännandet)</span><span class="sxs-lookup"><span data-stu-id="fd172-189">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="fd172-190">Giltighets tiden för token är 1 timme (du kan skicka mer än en begäran med samma token)</span><span class="sxs-lookup"><span data-stu-id="fd172-190">The Expiration time of the token is 1 hour (you can send more then one request with the same token)</span></span>

- <span data-ttu-id="fd172-191">Exempel på att skicka en begäran om att få en lista över incidenter **med C#**</span><span class="sxs-lookup"><span data-stu-id="fd172-191">Example of sending a request to get a list of incidents **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a><span data-ttu-id="fd172-192">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fd172-192">Related topics</span></span> 

- [<span data-ttu-id="fd172-193">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="fd172-193">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="fd172-194">Åtkomst till Microsoft Threat Protection med program kontext</span><span class="sxs-lookup"><span data-stu-id="fd172-194">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="fd172-195">Åtkomst till Microsoft Threat Protection med användar kontext</span><span class="sxs-lookup"><span data-stu-id="fd172-195">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
