---
title: Skapa en app för att få åtkomst till Microsoft Threat Protection utan en användare
description: Lär dig hur du skapar en app för att få åtkomst till Microsoft Threat Protection utan en användare
keywords: app, Access, API, skapa
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201425"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="48681-104">Skapa en app för att få åtkomst till Microsoft Threat Protection utan en användare</span><span class="sxs-lookup"><span data-stu-id="48681-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="48681-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="48681-105">**Applies to:**</span></span>
- <span data-ttu-id="48681-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="48681-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="48681-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="48681-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="48681-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="48681-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="48681-109">På den här sidan beskrivs hur du skapar ett program för att få programmatisk åtkomst till Microsoft Threat Protection utan en användare.</span><span class="sxs-lookup"><span data-stu-id="48681-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="48681-110">Om du behöver programmatisk åtkomst till Microsoft Threat Protection för en användares räkning kan du läsa [få åtkomst med användar kontext](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="48681-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="48681-111">Om du inte är säker på vilken åtkomst du behöver läser du [komma igång](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="48681-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="48681-112">Microsoft Threat Protection visar mycket av dess data och åtgärder genom en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="48681-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="48681-113">Dessa API: er kommer att hjälpa dig att automatisera arbets flöden och förnyas baserat på Microsoft Threat Protection-funktioner.</span><span class="sxs-lookup"><span data-stu-id="48681-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="48681-114">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="48681-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="48681-115">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="48681-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="48681-116">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="48681-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="48681-117">Skapa ett Azure Active Directory (Azure AD)-program.</span><span class="sxs-lookup"><span data-stu-id="48681-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="48681-118">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="48681-118">Get an access token using this application.</span></span>
- <span data-ttu-id="48681-119">Använd token för att få åtkomst till Microsoft Threat Protection API.</span><span class="sxs-lookup"><span data-stu-id="48681-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="48681-120">I den här artikeln förklaras hur du skapar ett Azure AD-program, hämtar en åtkomsttoken till Microsoft Threat Protection och validerar token.</span><span class="sxs-lookup"><span data-stu-id="48681-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="48681-121">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="48681-121">Create an app</span></span>

1. <span data-ttu-id="48681-122">Logga in på [Azure](https://portal.azure.com) med en användare som har rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="48681-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="48681-123">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="48681-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="48681-125">I registrerings formuläret väljer du ett namn för ansökan och väljer sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="48681-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="48681-126">Om du vill göra det möjligt för din app att komma åt Microsoft Threat Protection och tilldela behörigheter kan du välja **API-behörigheter**  >  **Lägg till behörighets**-API: er för att lägga till behörigheter i > på din program sida  >  **APIs my organization uses** , och sedan välja **Microsoft Threat Protection** **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="48681-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48681-127">Microsoft Threat Protection visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="48681-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="48681-128">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="48681-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="48681-130">Välj **program behörigheter** > välja relevanta behörigheter för scenariot, till exempel. **incident. Read. all**och välj sedan **Add Permissions**.</span><span class="sxs-lookup"><span data-stu-id="48681-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="48681-132">Du måste välja relevanta behörigheter för scenariot, **"Läs alla händelser"** , är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="48681-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="48681-133">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API du är intresse rad av.</span><span class="sxs-lookup"><span data-stu-id="48681-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="48681-134">Välj **bevilja medgivande**.</span><span class="sxs-lookup"><span data-stu-id="48681-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="48681-135">Varje gång du lägger till en behörighet måste du välja **bevilja medgivande** för att den nya behörigheten ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="48681-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

6. <span data-ttu-id="48681-137">Om du vill lägga till en hemlighet i programmet väljer du **certifikat & hemligheter**, lägger till en beskrivning för hemligheten och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="48681-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48681-138">När du har valt **Lägg till**väljer **du kopiera det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="48681-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="48681-139">Du kommer inte att kunna hämta det här värdet efter att du har lämnat.</span><span class="sxs-lookup"><span data-stu-id="48681-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

7. <span data-ttu-id="48681-141">Skriv in ditt program-ID och ditt klient-ID.</span><span class="sxs-lookup"><span data-stu-id="48681-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="48681-142">Gå till **Översikt** och kopiera följande på program sidan.</span><span class="sxs-lookup"><span data-stu-id="48681-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="48681-144">**Endast för Microsoft Threat Protection partners**.</span><span class="sxs-lookup"><span data-stu-id="48681-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="48681-145">[Följ instruktionerna här](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="48681-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="48681-146">Ställ in din app så att den är flertrådad (tillgänglig i alla innehavare efter medgivande).</span><span class="sxs-lookup"><span data-stu-id="48681-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="48681-147">Detta är **obligatoriskt** för tredjepartsprogram (till exempel om du skapar ett program som är avsett att köras i flera kunders innehavare).</span><span class="sxs-lookup"><span data-stu-id="48681-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="48681-148">Detta är **inte obligatoriskt** om du skapar en tjänst som du bara vill köra i klient organisationen (om du till exempel skapar ett program för ditt eget bruk som bara interagerar med dina egna data).</span><span class="sxs-lookup"><span data-stu-id="48681-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="48681-149">Så här ställer du in appen så att den är flertrådad:</span><span class="sxs-lookup"><span data-stu-id="48681-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="48681-150">Gå till **inloggningsautentisering**och Lägg till https://portal.azure.com som **omdirigerings-URI**.</span><span class="sxs-lookup"><span data-stu-id="48681-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="48681-151">Under **konto typer som stöds**längst ned på sidan väljer du **konton i valfritt organisations katalog** program medgivande för appen med flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="48681-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="48681-152">Du behöver programmet vara godkänt för varje innehavare där du tänker använda det.</span><span class="sxs-lookup"><span data-stu-id="48681-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="48681-153">Det beror på att ditt program interagerar med skydd mot Microsoft Threat för din kund.</span><span class="sxs-lookup"><span data-stu-id="48681-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="48681-154">Du (eller din kund om du skriver ett program från tredje part) måste välja medgivande länken och godkänna programmet.</span><span class="sxs-lookup"><span data-stu-id="48681-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="48681-155">Godkännandet bör göras med en användare som har administratörs behörighet i Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48681-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="48681-156">Medgivande länken är utformad så här:</span><span class="sxs-lookup"><span data-stu-id="48681-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="48681-157">Där 00000000-0000-0000-0000-000000000000 ersätts med ditt program-ID.</span><span class="sxs-lookup"><span data-stu-id="48681-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="48681-158">**Åstadkomma!**</span><span class="sxs-lookup"><span data-stu-id="48681-158">**Done!**</span></span> <span data-ttu-id="48681-159">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="48681-159">You have successfully registered an application!</span></span> <span data-ttu-id="48681-160">Se exemplen nedan för hämtning av token och verifiering.</span><span class="sxs-lookup"><span data-stu-id="48681-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="48681-161">Skaffa en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="48681-161">Get an access token</span></span>

<span data-ttu-id="48681-162">Mer information om Azure AD-tokens finns i [själv studie kursen för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="48681-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="48681-163">Använda PowerShell</span><span class="sxs-lookup"><span data-stu-id="48681-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="48681-164">Använda C#:</span><span class="sxs-lookup"><span data-stu-id="48681-164">Use C#:</span></span>

<span data-ttu-id="48681-165">Följande kod har testats med NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="48681-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="48681-166">Skapa ett nytt konsol program.</span><span class="sxs-lookup"><span data-stu-id="48681-166">Create a new console application.</span></span>
1. <span data-ttu-id="48681-167">Installera NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="48681-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="48681-168">Lägg till följande:</span><span class="sxs-lookup"><span data-stu-id="48681-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="48681-169">Kopiera och klistra in följande kod i programmet (Glöm inte att uppdatera de tre variablerna: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="48681-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="48681-170">Använd python</span><span class="sxs-lookup"><span data-stu-id="48681-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="48681-171">Använda sväng</span><span class="sxs-lookup"><span data-stu-id="48681-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="48681-172">I följande anvisningar förutsätts att bläddring för Windows redan är installerat på datorn.</span><span class="sxs-lookup"><span data-stu-id="48681-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="48681-173">Öppna en kommando tolk och ange CLIENT_ID till ditt Azure-program-ID.</span><span class="sxs-lookup"><span data-stu-id="48681-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="48681-174">Ange CLIENT_SECRET till din Azure Application Secret.</span><span class="sxs-lookup"><span data-stu-id="48681-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="48681-175">Ange TENANT_ID till det Azure TENANT-ID för kunden som vill använda ditt program för att få åtkomst till Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="48681-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="48681-176">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="48681-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="48681-177">Du får svaret i följande form:</span><span class="sxs-lookup"><span data-stu-id="48681-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="48681-178">Validera token</span><span class="sxs-lookup"><span data-stu-id="48681-178">Validate the token</span></span>

<span data-ttu-id="48681-179">Kontrol lera att du har rätt token:</span><span class="sxs-lookup"><span data-stu-id="48681-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="48681-180">Kopiera och klistra in den token du fick i det föregående steget i [JWT](https://jwt.ms) för att avkoda den.</span><span class="sxs-lookup"><span data-stu-id="48681-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="48681-181">Verifiera att du får en "roles"-anspråk med de önskade behörigheterna</span><span class="sxs-lookup"><span data-stu-id="48681-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="48681-182">I följande bild kan du se ett avkodat token från en app med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörighet:</span><span class="sxs-lookup"><span data-stu-id="48681-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="48681-184">Använda token för att få åtkomst till Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="48681-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="48681-185">Välj det API du vill använda.</span><span class="sxs-lookup"><span data-stu-id="48681-185">Choose the API you want to use.</span></span> <span data-ttu-id="48681-186">Mer information finns i [API: er som stöds av Microsoft Threat Protection](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="48681-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="48681-187">Ange auktorisations huvudet i http-begäran som du skickar till "Bearer {token}" (innehavaren är godkännandet).</span><span class="sxs-lookup"><span data-stu-id="48681-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="48681-188">Giltighets tiden för token är en timme.</span><span class="sxs-lookup"><span data-stu-id="48681-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="48681-189">Du kan skicka mer än en begäran med samma token.</span><span class="sxs-lookup"><span data-stu-id="48681-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="48681-190">Nedan följer ett exempel på hur man skickar en begäran om att få en lista över incidenter **med C#**:</span><span class="sxs-lookup"><span data-stu-id="48681-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="48681-191">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="48681-191">Related topics</span></span>
- [<span data-ttu-id="48681-192">Komma åt API: erna för skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="48681-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="48681-193">Åtkomst till Microsoft Threat Protection med program kontext</span><span class="sxs-lookup"><span data-stu-id="48681-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="48681-194">Åtkomst till Microsoft Threat Protection med användar kontext</span><span class="sxs-lookup"><span data-stu-id="48681-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
