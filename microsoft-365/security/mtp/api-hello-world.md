---
title: Hej världen för Microsoft 365 Defender REST API
description: Lär dig hur du skapar en app och använder ett token för att komma åt API för Microsoft 365 Defender
keywords: app, token, Access, AAD, program, program registrering, PowerShell, skript, global administratör, tillåtelse, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719316"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="045ed-104">Hej världen för Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="045ed-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="045ed-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="045ed-105">**Applies to:**</span></span>

- <span data-ttu-id="045ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="045ed-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="045ed-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="045ed-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="045ed-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="045ed-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="045ed-109">Få incidenter med hjälp av ett enkelt PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="045ed-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="045ed-110">Det bör ta 5-10 minuter för projektet att genomföras.</span><span class="sxs-lookup"><span data-stu-id="045ed-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="045ed-111">I den här tids uppskattningen ingår att registrera programmet och tillämpa koden från PowerShell-exempelprogrammet.</span><span class="sxs-lookup"><span data-stu-id="045ed-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="045ed-112">Registrera ett program i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="045ed-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="045ed-113">Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="045ed-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="045ed-114">Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="045ed-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="045ed-116">I registrerings formuläret väljer du ett namn för ansökan och väljer sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="045ed-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="045ed-117">Det är valfritt att välja en URL för omdirigering.</span><span class="sxs-lookup"><span data-stu-id="045ed-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="045ed-118">Du behöver ingen för att genomföra det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="045ed-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="045ed-119">På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="045ed-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="045ed-120">Ditt program kan nu komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="045ed-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="045ed-121">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="045ed-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="045ed-122">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="045ed-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="045ed-123">![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="045ed-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="045ed-124">Välj **program behörigheter**  >  **incident. Read. all** och välj **Add Permissions**.</span><span class="sxs-lookup"><span data-stu-id="045ed-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="045ed-126">Välj **ge administratörs medgivande**.</span><span class="sxs-lookup"><span data-stu-id="045ed-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="045ed-127">Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="045ed-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

6. <span data-ttu-id="045ed-129">Lägg till en hemlighet i programmet.</span><span class="sxs-lookup"><span data-stu-id="045ed-129">Add a secret to the application.</span></span> <span data-ttu-id="045ed-130">Välj **certifikat & hemligheter**, Lägg till en beskrivning till hemligheten och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="045ed-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="045ed-131">När du har valt **Lägg till** väljer **du kopiera det genererade hemliga värdet**.</span><span class="sxs-lookup"><span data-stu-id="045ed-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="045ed-132">Du kommer inte att kunna hämta det hemliga värdet efter att du har lämnat.</span><span class="sxs-lookup"><span data-stu-id="045ed-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

7. <span data-ttu-id="045ed-134">Spela in ditt program-ID och klient-ID något säkert.</span><span class="sxs-lookup"><span data-stu-id="045ed-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="045ed-135">De visas under **Översikt** på din program sida.</span><span class="sxs-lookup"><span data-stu-id="045ed-135">They're listed under **Overview** on your application page.</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="045ed-137">Hämta ett token med appen och Använd token för att få åtkomst till API: t</span><span class="sxs-lookup"><span data-stu-id="045ed-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="045ed-138">Mer information om Azure Active Directory-tokens finns i [själv studie kursen för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="045ed-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="045ed-139">Även om exemplet i det här demo programmet uppmuntrar dig att klistra in ditt hemliga värde för testning bör du **aldrig hardcode hemligheter** i ett program som körs i produktion.</span><span class="sxs-lookup"><span data-stu-id="045ed-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="045ed-140">En tredje part kan använda din hemlighet för att komma åt resurser.</span><span class="sxs-lookup"><span data-stu-id="045ed-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="045ed-141">Du kan hålla dina programs hemligheter säkra genom att använda [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="045ed-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="045ed-142">Ett praktiskt exempel på hur du kan skydda din app finns i [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="045ed-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="045ed-143">Kopiera skriptet nedan och klistra in det i din text redigerare i Skype.</span><span class="sxs-lookup"><span data-stu-id="045ed-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="045ed-144">Spara som **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="045ed-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="045ed-145">Du kan också köra koden i PowerShell ISE, men du bör spara den eftersom vi måste köra den igen när vi använder skript för att hämta ett samtal i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="045ed-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="045ed-146">Med det här skriptet skapas ett token och sparas i arbetsmappen under namnet *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="045ed-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="045ed-147">Validera token</span><span class="sxs-lookup"><span data-stu-id="045ed-147">Validate the token</span></span>

1. <span data-ttu-id="045ed-148">Kopiera och klistra in den token du tog emot i [JWT](https://jwt.ms) för att avkoda den.</span><span class="sxs-lookup"><span data-stu-id="045ed-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="045ed-149">*JWT* står för *JSON Web token*.</span><span class="sxs-lookup"><span data-stu-id="045ed-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="045ed-150">Den kodade token innehåller ett antal JSON-formaterade objekt eller anspråk.</span><span class="sxs-lookup"><span data-stu-id="045ed-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="045ed-151">Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="045ed-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="045ed-152">I följande bild kan du se ett avkodat token från en app, med ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="045ed-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Bild jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="045ed-154">Få en lista över de senaste incidenterna</span><span class="sxs-lookup"><span data-stu-id="045ed-154">Get a list of recent incidents</span></span>

<span data-ttu-id="045ed-155">Skriptet nedan använder **Get-Token.ps1** för att komma åt API: t.</span><span class="sxs-lookup"><span data-stu-id="045ed-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="045ed-156">Då hämtas en lista över de incidenter som senast uppdaterades inom 48 timmar, och listan sparas som en JSON-fil.</span><span class="sxs-lookup"><span data-stu-id="045ed-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="045ed-157">Spara det här skriptet i samma mapp som du sparade **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="045ed-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="045ed-158">Nu är du klar!</span><span class="sxs-lookup"><span data-stu-id="045ed-158">You're all done!</span></span> <span data-ttu-id="045ed-159">Du har lyckats:</span><span class="sxs-lookup"><span data-stu-id="045ed-159">You've successfully:</span></span>

- <span data-ttu-id="045ed-160">Skapade och registrerade ett program.</span><span class="sxs-lookup"><span data-stu-id="045ed-160">Created and registered an application.</span></span>
- <span data-ttu-id="045ed-161">Har beviljats behörighet för det programmet att läsa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="045ed-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="045ed-162">Ansluten till API: t.</span><span class="sxs-lookup"><span data-stu-id="045ed-162">Connected to the API.</span></span>
- <span data-ttu-id="045ed-163">Använde ett PowerShell-skript för att returnera incidenter som uppdaterats under de senaste 48 timmarna.</span><span class="sxs-lookup"><span data-stu-id="045ed-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="045ed-164">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="045ed-164">Related articles</span></span>

- [<span data-ttu-id="045ed-165">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="045ed-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="045ed-166">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="045ed-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="045ed-167">Skapa en app för åtkomst till Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="045ed-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="045ed-168">Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="045ed-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="045ed-169">Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="045ed-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="045ed-170">Hantera hemligheter i dina serverprogram med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="045ed-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="045ed-171">OAuth 2,0-auktorisering för användare inloggning och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="045ed-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
