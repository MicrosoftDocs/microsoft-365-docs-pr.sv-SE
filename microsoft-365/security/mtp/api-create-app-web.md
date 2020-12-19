---
title: Skapa en app för åtkomst till Microsoft 365 Defender utan en användare
description: Lär dig hur du skapar en app för att komma åt Microsoft 365 Defender utan en användare.
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719362"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="64ee4-104">Skapa en app för åtkomst till Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="64ee4-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="64ee4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="64ee4-105">**Applies to:**</span></span>

- <span data-ttu-id="64ee4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64ee4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64ee4-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="64ee4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="64ee4-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="64ee4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="64ee4-109">På den här sidan beskrivs hur du skapar ett program för att få programmatisk åtkomst till Microsoft 365 Defender utan en definierad användare, till exempel om du skapar en daemon-eller bakgrunds tjänst.</span><span class="sxs-lookup"><span data-stu-id="64ee4-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="64ee4-110">Om du behöver programmatisk åtkomst till Microsoft 365 Defender för en eller flera användare läser du [skapa en app för att få åtkomst till microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md) och [skapa en app med partner åtkomst till Microsoft 365 Defender API: er](api-partner-access.md).</span><span class="sxs-lookup"><span data-stu-id="64ee4-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="64ee4-111">Om du inte är säker på vilken typ av åtkomst du behöver läser du [komma igång](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="64ee4-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="64ee4-112">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="64ee4-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="64ee4-113">Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsoft 365 Defender-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="64ee4-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="64ee4-114">Denna API-åtkomst kräver autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="64ee4-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="64ee4-115">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="64ee4-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="64ee4-116">I allmänhet måste du göra följande för att använda dessa API:</span><span class="sxs-lookup"><span data-stu-id="64ee4-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="64ee4-117">Skapa ett Azure Active Directory (Azure AD)-program.</span><span class="sxs-lookup"><span data-stu-id="64ee4-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="64ee4-118">Skaffa en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="64ee4-118">Get an access token using this application.</span></span>
- <span data-ttu-id="64ee4-119">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="64ee4-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="64ee4-120">I den här artikeln förklarar vi hur du:</span><span class="sxs-lookup"><span data-stu-id="64ee4-120">This article explains how to:</span></span>

- <span data-ttu-id="64ee4-121">Skapa ett Azure AD-program</span><span class="sxs-lookup"><span data-stu-id="64ee4-121">Create an Azure AD application</span></span>
- <span data-ttu-id="64ee4-122">Skaffa en åtkomsttoken till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64ee4-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="64ee4-123">Validera token.</span><span class="sxs-lookup"><span data-stu-id="64ee4-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="64ee4-124">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="64ee4-124">Create an app</span></span>

1. <span data-ttu-id="64ee4-125">Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="64ee4-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="64ee4-126">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="64ee4-128">I formuläret väljer du ett namn för ansökan och väljer sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="64ee4-129">På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="64ee4-130">Ditt program kan nu komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="64ee4-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="64ee4-131">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="64ee4-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="64ee4-132">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="64ee4-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="64ee4-134">Välj **program behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-134">Select **Application permissions**.</span></span> <span data-ttu-id="64ee4-135">Välj relevanta behörigheter för ditt scenario (till exempel **incident. Read. all**) och välj sedan **Add Permissions**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="64ee4-137">Du måste välja relevanta behörigheter för scenariot.</span><span class="sxs-lookup"><span data-stu-id="64ee4-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="64ee4-138">*Läs alla händelser* är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="64ee4-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="64ee4-139">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API som du vill ringa.</span><span class="sxs-lookup"><span data-stu-id="64ee4-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="64ee4-140">Om du till exempel vill [köra avancerade frågor](api-advanced-hunting.md)väljer du "kör avancerade frågor". Om du vill [isolera en enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)väljer du "isolera datorns tillstånd".</span><span class="sxs-lookup"><span data-stu-id="64ee4-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="64ee4-141">Välj **ge administratörs medgivande**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="64ee4-142">Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="64ee4-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

7. <span data-ttu-id="64ee4-144">Om du vill lägga till en hemlighet i programmet väljer du **certifikat & hemligheter**, lägger till en beskrivning till hemligheten och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="64ee4-145">När du har valt **Lägg till** väljer **du kopiera det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="64ee4-146">Du kommer inte att kunna hämta det hemliga värdet efter att du har lämnat.</span><span class="sxs-lookup"><span data-stu-id="64ee4-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

8. <span data-ttu-id="64ee4-148">Spela in ditt program-ID och klient-ID något säkert.</span><span class="sxs-lookup"><span data-stu-id="64ee4-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="64ee4-149">De visas under **Översikt** på din program sida.</span><span class="sxs-lookup"><span data-stu-id="64ee4-149">They're listed under **Overview** on your application page.</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="64ee4-151">**Endast för microsoft 365 Defender-partners**: [Följ de här anvisningarna](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) för partner åtkomst via API för Microsoft 365 Defender, Ställ in din app så att den blir multi-Tenant så att den kan vara tillgänglig i alla klient organisationer när du har fått administratörs tillåtelse.</span><span class="sxs-lookup"><span data-stu-id="64ee4-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="64ee4-152">Partner åtkomst **krävs** för tredjepartsprogram, till exempel om du skapar ett program som är avsett att köras i flera kunders klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="64ee4-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="64ee4-153">Det är **inte nödvändigt** om du skapar en tjänst som du bara vill köra i klient organisationen, till exempel ett program för din egen användning som bara interagerar med dina egna data.</span><span class="sxs-lookup"><span data-stu-id="64ee4-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="64ee4-154">Så här anger du att programmet ska vara Multi-klient organisation:</span><span class="sxs-lookup"><span data-stu-id="64ee4-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="64ee4-155">Gå till **inloggningsautentisering** och Lägg till https://portal.azure.com som **omdirigerings-URI**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="64ee4-156">Under **konto typer som stöds** längst ned på sidan väljer du **konton i valfritt organisations katalog** program medgivande för appen med flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="64ee4-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="64ee4-157">Eftersom ditt program interagerar med Microsoft 365 Defender åt användarna måste det godkännas för varje klient organisation som ska använda det.</span><span class="sxs-lookup"><span data-stu-id="64ee4-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="64ee4-158">Den globala Active Directory-administratören för varje innehavare måste välja medgivande länken och godkänna programmet.</span><span class="sxs-lookup"><span data-stu-id="64ee4-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="64ee4-159">Medgivande länken har följande struktur:</span><span class="sxs-lookup"><span data-stu-id="64ee4-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="64ee4-160">Siffrorna `00000000-0000-0000-0000-000000000000` bör ersättas med ditt program-ID.</span><span class="sxs-lookup"><span data-stu-id="64ee4-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="64ee4-161">**Åstadkomma!**</span><span class="sxs-lookup"><span data-stu-id="64ee4-161">**Done!**</span></span> <span data-ttu-id="64ee4-162">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="64ee4-162">You've successfully registered an application!</span></span> <span data-ttu-id="64ee4-163">Se exemplen nedan för hämtning av token och verifiering.</span><span class="sxs-lookup"><span data-stu-id="64ee4-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="64ee4-164">Skaffa en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="64ee4-164">Get an access token</span></span>

<span data-ttu-id="64ee4-165">Mer information om Azure Active Directory-tokens finns i [själv studie kursen för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="64ee4-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64ee4-166">Även om exemplen i det här avsnittet uppmanar dig att klistra in hemliga värden i test syfte bör du **aldrig hardcode hemligheter** i ett program som körs i produktion.</span><span class="sxs-lookup"><span data-stu-id="64ee4-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="64ee4-167">En tredje part kan använda din hemlighet för att komma åt resurser.</span><span class="sxs-lookup"><span data-stu-id="64ee4-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="64ee4-168">Du kan hålla dina programs hemligheter säkra genom att använda [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="64ee4-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="64ee4-169">Ett praktiskt exempel på hur du kan skydda din app finns i [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="64ee4-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="64ee4-170">Skaffa en åtkomsttoken med PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ee4-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="64ee4-171">Skaffa en åtkomsttoken med C\#</span><span class="sxs-lookup"><span data-stu-id="64ee4-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="64ee4-172">Följande kod har testats med NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="64ee4-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="64ee4-173">Skapa ett nytt konsol program.</span><span class="sxs-lookup"><span data-stu-id="64ee4-173">Create a new console application.</span></span>

1. <span data-ttu-id="64ee4-174">Installera NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="64ee4-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="64ee4-175">Lägg till följande rad:</span><span class="sxs-lookup"><span data-stu-id="64ee4-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="64ee4-176">Kopiera och klistra in följande kod i appen (Glöm inte att uppdatera de tre variablerna: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="64ee4-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="64ee4-177">Skaffa en åtkomsttoken med python</span><span class="sxs-lookup"><span data-stu-id="64ee4-177">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="64ee4-178">Skaffa en åtkomsttoken med hjälp av sväng</span><span class="sxs-lookup"><span data-stu-id="64ee4-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="64ee4-179">Sväng är förinstallerat på Windows 10, version 1803 och senare.</span><span class="sxs-lookup"><span data-stu-id="64ee4-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="64ee4-180">För andra versioner av Windows laddar du ned och installerar verktyget direkt från den [officiella platsen](https://curl.haxx.se/windows/).</span><span class="sxs-lookup"><span data-stu-id="64ee4-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="64ee4-181">Öppna en kommando tolk och ange CLIENT_ID till ditt Azure-program-ID.</span><span class="sxs-lookup"><span data-stu-id="64ee4-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="64ee4-182">Ange CLIENT_SECRET till din Azure Application Secret.</span><span class="sxs-lookup"><span data-stu-id="64ee4-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="64ee4-183">Ange TENANT_ID till det Azure TENANT ID för kunden som vill använda din app för att komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="64ee4-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="64ee4-184">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="64ee4-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="64ee4-185">Ett lyckat svar ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="64ee4-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="64ee4-186">Validera token</span><span class="sxs-lookup"><span data-stu-id="64ee4-186">Validate the token</span></span>

1. <span data-ttu-id="64ee4-187">Kopiera och klistra in din token i [JSON Web token validator-webbplatsen, JWT,](https://jwt.ms) för att avkoda den.</span><span class="sxs-lookup"><span data-stu-id="64ee4-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="64ee4-188">Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="64ee4-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="64ee4-189">I följande bild kan du se ett avkodat token från en app, med `Incidents.Read.All` , `Incidents.ReadWrite.All` och `AdvancedHunting.Read.All` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="64ee4-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="64ee4-191">Använda token för att komma åt Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="64ee4-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="64ee4-192">Välj det API du vill använda (incidenter eller avancerad jakt).</span><span class="sxs-lookup"><span data-stu-id="64ee4-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="64ee4-193">Mer information finns i [Microsoft 365 Defender API: n](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="64ee4-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="64ee4-194">I den http-begäran du är på väg att skicka kan du ange tillstånds huvudet till `"Bearer" <token>` , *innehavaren* är ett godkännande och *token* som verifierad token.</span><span class="sxs-lookup"><span data-stu-id="64ee4-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="64ee4-195">Token upphör att gälla inom en timme.</span><span class="sxs-lookup"><span data-stu-id="64ee4-195">The token will expire within one hour.</span></span> <span data-ttu-id="64ee4-196">Du kan skicka fler än en begäran under tiden med samma token.</span><span class="sxs-lookup"><span data-stu-id="64ee4-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="64ee4-197">I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med C#**.</span><span class="sxs-lookup"><span data-stu-id="64ee4-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="64ee4-198">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="64ee4-198">Related articles</span></span>

- [<span data-ttu-id="64ee4-199">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="64ee4-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="64ee4-200">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64ee4-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="64ee4-201">Skapa ett ' Hej världen '-program</span><span class="sxs-lookup"><span data-stu-id="64ee4-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="64ee4-202">Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="64ee4-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="64ee4-203">Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="64ee4-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="64ee4-204">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="64ee4-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="64ee4-205">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="64ee4-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="64ee4-206">Hantera hemligheter i dina serverprogram med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="64ee4-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="64ee4-207">OAuth 2,0-auktorisering för användare inloggning och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="64ee4-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
