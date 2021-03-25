---
title: Skapa en app för åtkomst till Microsoft Defender för slutpunkt utan en användare
ms.reviewer: ''
description: Lär dig hur du designar en webbapp för att få programåtkomst till Microsoft Defender för Endpoint utan en användare.
keywords: apis, graph api, apis som stöds, aktör, aviseringar, enhet, användare, domän, ip, fil, avancerad sökning, fråga
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f480a148d72428c6346930a91358d1e8b674ee7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200011"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="7aa8f-104">Skapa en app för åtkomst till Microsoft Defender för slutpunkt utan en användare</span><span class="sxs-lookup"><span data-stu-id="7aa8f-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7aa8f-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7aa8f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7aa8f-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7aa8f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7aa8f-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="7aa8f-108">På den här sidan beskrivs hur du skapar ett program för att få programtisk åtkomst till Defender för Endpoint utan en användare.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="7aa8f-109">Om du behöver programmeringsåtkomst till Defender för Endpoint för en användares räkning kan du gå till [Få åtkomst med användarkontext](exposed-apis-create-app-nativeapp.md).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="7aa8f-110">Om du inte är säker på vilken åtkomst du behöver kan du [gå till Komma igång.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7aa8f-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="7aa8f-111">Microsoft Defender för slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7aa8f-112">De HÄR API:erna hjälper dig att automatisera arbetsflöden och nyfikna baserat på Defender för Slutpunkt-funktioner.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="7aa8f-113">API-åtkomst kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7aa8f-114">Mer information finns i [OAuth 2.0 Auktoriseringskodflöde](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7aa8f-115">I allmänhet måste du vidta följande steg för att använda API:er:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="7aa8f-116">Skapa ett Azure Active Directory-program (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="7aa8f-117">Hämta en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-117">Get an access token using this application.</span></span>
- <span data-ttu-id="7aa8f-118">Använd tokenet för att komma åt Defender för Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="7aa8f-119">I den här artikeln förklaras hur du skapar ett Azure AD-program, hämtar en åtkomsttoken till Microsoft Defender för Endpoint och verifierar token.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="7aa8f-120">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="7aa8f-120">Create an app</span></span>

1. <span data-ttu-id="7aa8f-121">Logga in på [Azure](https://portal.azure.com) med en användare som har **rollen Global** administratör.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="7aa8f-122">Gå till **Azure Active Directory-appregistreringar**  >    >  **Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Bild av Microsoft Azure och navigering till programregistrering](images/atp-azure-new-app2.png)

3. <span data-ttu-id="7aa8f-124">Välj ett namn på din ansökan i registreringsformuläret och välj sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="7aa8f-125">Om du vill aktivera appen för  att komma åt Defender för Slutpunkt och tilldela behörigheten Läs alla aviseringar väljer du API-behörigheter Lägg till **behörighets-API:er** som min organisation använder >, skriver  >    >   **WindowsDefenderATP** och väljer **sedan WindowsDefenderATP.**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7aa8f-126">*WindowsDefenderATP* visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="7aa8f-127">Börja skriva namnet i textrutan så att det visas.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-127">Start writing its name in the text box to see it appear.</span></span>

   ![lägg till behörighet](images/add-permission.png)

   - <span data-ttu-id="7aa8f-129">Välj **Avisering om**  >  **programbehörigheter.Läs.Alla** och välj sedan Lägg till **behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![appbehörighet](images/application-permissions.png)

     <span data-ttu-id="7aa8f-131">Du måste välja rätt behörighet.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="7aa8f-132">"Läs alla aviseringar" är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="7aa8f-133">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-133">For instance:</span></span>

     - <span data-ttu-id="7aa8f-134">Om [du vill köra avancerade](run-advanced-query-api.md)frågor väljer du behörigheten Kör avancerade frågor.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="7aa8f-135">Om [du vill isolera en](isolate-machine.md)enhet väljer du behörigheten "Isolera dator".</span><span class="sxs-lookup"><span data-stu-id="7aa8f-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="7aa8f-136">Du kan avgöra vilken behörighet du behöver i avsnittet **Behörigheter i** api:t som du vill anropa.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="7aa8f-137">Välj **Bevilja medgivande**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7aa8f-138">Varje gång du lägger till en behörighet måste du välja **Ge medgivande** för att den nya behörigheten ska gälla.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Bevilja behörigheter](images/grant-consent.png)

6. <span data-ttu-id="7aa8f-140">Om du vill lägga till en hemligt i programmet väljer **du Certifikat &,** lägger till en beskrivning till hemligheten och väljer sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa8f-141">När du har **valt Lägg** till väljer du kopiera **det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="7aa8f-142">Du kommer inte att kunna hämta det här värdet när du har lämnar det.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-142">You won't be able to retrieve this value after you leave.</span></span>

    ![Bild av skapa programnyckel](images/webapp-create-key2.png)

7. <span data-ttu-id="7aa8f-144">Skriv ned ditt program-ID och ditt klient-ID.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="7aa8f-145">Gå till Översikt på **programsidan och** kopiera följande.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![Bild på skapad app-ID](images/app-and-tenant-ids.png)

8. <span data-ttu-id="7aa8f-147">**Endast för Microsoft Defender för slutpunktspartner.**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="7aa8f-148">Ange att appen ska ha flera klientorganisationsklienter (tillgänglig i alla klientorganisationen efter medgivande).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="7aa8f-149">Detta krävs **för** appar från tredje part (till exempel om du skapar ett program som ska köras i flera kunders klientorganisation).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="7aa8f-150">Detta krävs **inte** om du skapar en tjänst som du bara vill köra i klientorganisationen (till exempel om du skapar ett program för din egen användning som bara kommer att interagera med dina egna data).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="7aa8f-151">Så här anger du att programmet ska ha flera klientorganisationsklienter:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="7aa8f-152">Gå till **Autentisering** och lägg till `https://portal.azure.com` som Redirect **URI.**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="7aa8f-153">Längst ned på **sidan,** under Kontotyper  som stöds, väljer du Konton i ett organisationskatalogprograms medgivande för appen med flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="7aa8f-154">Du behöver att programmet ska godkännas i varje klientorganisation där du tänker använda det.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="7aa8f-155">Det beror på att ditt program interagerar Defender för Endpoint åt din kund.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="7aa8f-156">Du (eller kunden om du skriver en app från tredje part) måste välja länken för medgivande och godkänna appen.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="7aa8f-157">Medgivandet bör göras med en användare som har administratörsbehörighet i Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="7aa8f-158">Medgivandelänken är utformad på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="7aa8f-159">Där 00000000-0000-0000-0000-00000000000 ersätts med ditt program-ID.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="7aa8f-160">**Klart!**</span><span class="sxs-lookup"><span data-stu-id="7aa8f-160">**Done!**</span></span> <span data-ttu-id="7aa8f-161">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="7aa8f-161">You have successfully registered an application!</span></span> <span data-ttu-id="7aa8f-162">Se exempel nedan för insamling och validering av token.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="7aa8f-163">Hämta en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="7aa8f-163">Get an access token</span></span>

<span data-ttu-id="7aa8f-164">Mer information om Azure AD-token finns i [självstudiekursen om Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="7aa8f-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="7aa8f-165">Använda PowerShell</span><span class="sxs-lookup"><span data-stu-id="7aa8f-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
```

### <a name="use-c"></a><span data-ttu-id="7aa8f-166">Använd C#:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-166">Use C#:</span></span>

<span data-ttu-id="7aa8f-167">Följande kod testades med NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="7aa8f-168">Skapa ett nytt konsolprogram.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-168">Create a new console application.</span></span>
1. <span data-ttu-id="7aa8f-169">Installera NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="7aa8f-170">Lägg till följande:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="7aa8f-171">Kopiera och klistra in följande kod i programmet (glöm inte att uppdatera de tre variablerna: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="7aa8f-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="7aa8f-172">Använda Python</span><span class="sxs-lookup"><span data-stu-id="7aa8f-172">Use Python</span></span>

<span data-ttu-id="7aa8f-173">Se [Hämta token med Python](run-advanced-query-sample-python.md#get-token).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="7aa8f-174">Använd Avokrypt</span><span class="sxs-lookup"><span data-stu-id="7aa8f-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="7aa8f-175">Följande procedur förutsätter att Avbildning för Windows redan är installerat på datorn.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="7aa8f-176">Öppna en kommandotolk och ange CLIENT_ID ditt Azure-program-ID.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="7aa8f-177">Ställ CLIENT_SECRET till Azure-programhemligheten.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="7aa8f-178">Ange TENANT_ID Azure-klientorganisations-ID för kunden som vill använda appen för att komma åt Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="7aa8f-179">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="7aa8f-180">Du får ett svar i följande formulär:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="7aa8f-181">Verifiera token</span><span class="sxs-lookup"><span data-stu-id="7aa8f-181">Validate the token</span></span>

<span data-ttu-id="7aa8f-182">Se till att du har fått rätt token:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="7aa8f-183">Kopiera och klistra in den token du fick i föregående steg i [JWT](https://jwt.ms) för att avkoda den.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="7aa8f-184">Verifiera att du får ett anspråk om "roller" med rätt behörighet</span><span class="sxs-lookup"><span data-stu-id="7aa8f-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="7aa8f-185">I följande bild kan du se en avkodad token som förvärvats från en app med behörighet till alla Microsoft Defender för Endpoints roller:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![Bild på tokenverifiering](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="7aa8f-187">Använda token för att komma åt Microsoft Defender för Endpoint API</span><span class="sxs-lookup"><span data-stu-id="7aa8f-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="7aa8f-188">Välj det API du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-188">Choose the API you want to use.</span></span> <span data-ttu-id="7aa8f-189">Mer information finns i Defender [för slutpunkts-API:er som stöds.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="7aa8f-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="7aa8f-190">Ange ett auktoriseringshuvud i http-begäran som du skickar till "Bearer {token}" (Bearer är auktoriseringsschemat).</span><span class="sxs-lookup"><span data-stu-id="7aa8f-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="7aa8f-191">Utgångstiden för token är en timme.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="7aa8f-192">Du kan skicka fler än en begäran med samma token.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="7aa8f-193">Följande är ett exempel på att skicka en begäran om att få en lista med aviseringar **med hjälp av C#**:</span><span class="sxs-lookup"><span data-stu-id="7aa8f-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="7aa8f-194">Se även</span><span class="sxs-lookup"><span data-stu-id="7aa8f-194">See also</span></span>
- [<span data-ttu-id="7aa8f-195">Microsoft Defender-API:er som stöds för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="7aa8f-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="7aa8f-196">Åtkomst till Microsoft Defender för Endpoint åt en användare</span><span class="sxs-lookup"><span data-stu-id="7aa8f-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
