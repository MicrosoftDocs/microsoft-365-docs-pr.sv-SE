---
title: Hämta aviseringar från MSSP-kundklientorganisationen
description: Lär dig hur du hämtar aviseringar från en kundklientorganisation
keywords: hanterad säkerhetstjänstleverantör, mssp, konfigurera, integrering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770775"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="a891c-104">Hämta aviseringar från MSSP-kundklientorganisationen</span><span class="sxs-lookup"><span data-stu-id="a891c-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a891c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a891c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a891c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a891c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="a891c-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a891c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a891c-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a891c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="a891c-109">Den här åtgärden vidtas av MSSP.</span><span class="sxs-lookup"><span data-stu-id="a891c-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="a891c-110">Du kan hämta aviseringar på två sätt:</span><span class="sxs-lookup"><span data-stu-id="a891c-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="a891c-111">Använda SIEM-metoden</span><span class="sxs-lookup"><span data-stu-id="a891c-111">Using the SIEM method</span></span>
- <span data-ttu-id="a891c-112">Använda API:er</span><span class="sxs-lookup"><span data-stu-id="a891c-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="a891c-113">Hämta aviseringar till din SIEM</span><span class="sxs-lookup"><span data-stu-id="a891c-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="a891c-114">Om du vill hämta aviseringar till ditt SIEM-system måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="a891c-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="a891c-115">Steg 1: Skapa ett program från tredje part</span><span class="sxs-lookup"><span data-stu-id="a891c-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="a891c-116">Steg 2: Få åtkomst och uppdatera token från kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="a891c-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="a891c-117">Steg 3: tillåta ditt program på Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="a891c-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="a891c-118">Steg 1: Skapa ett program i Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a891c-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="a891c-119">Du måste skapa ett program och ge det behörighet att hämta aviseringar från kundens Microsoft Defender för Slutpunktsklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a891c-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="a891c-120">Logga in på [Azure AD-portalen](https://aad.portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a891c-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="a891c-121">Välj **Azure Active Directory**  >  **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="a891c-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="a891c-122">Klicka **på Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="a891c-122">Click **New registration**.</span></span>

4. <span data-ttu-id="a891c-123">Ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="a891c-123">Specify the following values:</span></span>

    - <span data-ttu-id="a891c-124">Namn: \<Tenant_name\> SIEM MSSP-koppling (Tenant_name med klientorganisationens visningsnamn)</span><span class="sxs-lookup"><span data-stu-id="a891c-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="a891c-125">Kontotyper som stöds: Endast konto i denna organisationskatalog</span><span class="sxs-lookup"><span data-stu-id="a891c-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="a891c-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector` (replace <domain_name> with the tenant name)</span><span class="sxs-lookup"><span data-stu-id="a891c-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="a891c-127">Klicka **på Registrera**.</span><span class="sxs-lookup"><span data-stu-id="a891c-127">Click **Register**.</span></span> <span data-ttu-id="a891c-128">Programmet visas i listan med program som du äger.</span><span class="sxs-lookup"><span data-stu-id="a891c-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="a891c-129">Markera programmet och klicka sedan på **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="a891c-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="a891c-130">Kopiera värdet från fältet **Application (client) ID** till en säker plats. Det behöver du i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="a891c-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="a891c-131">Välj **Certifikat & hemligheter i** panelen för det nya programmet.</span><span class="sxs-lookup"><span data-stu-id="a891c-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="a891c-132">Klicka **på Ny klienthemlighet.**</span><span class="sxs-lookup"><span data-stu-id="a891c-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="a891c-133">Beskrivning: Ange en beskrivning för nyckeln.</span><span class="sxs-lookup"><span data-stu-id="a891c-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="a891c-134">Går ut: Välj **om 1 år**</span><span class="sxs-lookup"><span data-stu-id="a891c-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="a891c-135">Klicka **på** Lägg till , kopiera värdet för klienthemligheten till en säker plats, du behöver detta i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="a891c-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="a891c-136">Steg 2: Få åtkomst och uppdatera token från kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="a891c-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="a891c-137">I det här avsnittet får du veta hur du använder ett PowerShell-skript för att hämta tokens från kundens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a891c-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="a891c-138">Det här skriptet använder programmet från föregående steg för att få åtkomst- och uppdateringstoken med OAuth-auktoriseringskoden för Flow.</span><span class="sxs-lookup"><span data-stu-id="a891c-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="a891c-139">När du har lämnat in dina autentiseringsuppgifter måste du ge medgivande till programmet så att programmet etableras i kundens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a891c-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="a891c-140">Skapa en ny mapp och ge den ett namn: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="a891c-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="a891c-141">Ladda ned [modulen LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) och spara den i `MsspTokensAcquisition` mappen.</span><span class="sxs-lookup"><span data-stu-id="a891c-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a891c-142">Ersätt med på rad `authorzationUrl` `authorizationUrl` 30.</span><span class="sxs-lookup"><span data-stu-id="a891c-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="a891c-143">Skapa en fil med följande innehåll och spara den med `MsspTokensAcquisition.ps1` namnet i mappen:</span><span class="sxs-lookup"><span data-stu-id="a891c-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="a891c-144">Öppna en PowerShell-kommandotolk med förhöjd behörighet i `MsspTokensAcquisition` mappen.</span><span class="sxs-lookup"><span data-stu-id="a891c-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="a891c-145">Kör följande kommando:`Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="a891c-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="a891c-146">Ange följande kommandon: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="a891c-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="a891c-147">Ersätt \<client_id\> med det program **-ID (klient-ID)** du fick i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="a891c-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="a891c-148">Ersätt \<app_key\> med **klienthemligheten som** du skapade från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="a891c-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="a891c-149">Ersätt \<customer_tenant_id\> med kundens **klientorganisations-ID.**</span><span class="sxs-lookup"><span data-stu-id="a891c-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="a891c-150">Du uppmanas att ange dina autentiseringsuppgifter och ditt medgivande.</span><span class="sxs-lookup"><span data-stu-id="a891c-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="a891c-151">Ignorera sidomdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="a891c-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="a891c-152">I PowerShell-fönstret får du en åtkomsttoken och en uppdateringstoken.</span><span class="sxs-lookup"><span data-stu-id="a891c-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="a891c-153">Spara uppdateringstoken för att konfigurera SIEM-kopplingen.</span><span class="sxs-lookup"><span data-stu-id="a891c-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="a891c-154">Steg 3: Tillåt ditt program på Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="a891c-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="a891c-155">Du måste tillåta det program som du skapade i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="a891c-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="a891c-156">Du måste ha behörigheten **Hantera portalsysteminställningar** för att tillåta programmet.</span><span class="sxs-lookup"><span data-stu-id="a891c-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="a891c-157">Annars måste du begära att kunden tillåter programmet åt dig.</span><span class="sxs-lookup"><span data-stu-id="a891c-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="a891c-158">Gå till `https://securitycenter.windows.com?tid=<customer_tenant_id>` (ersätt \<customer_tenant_id\> med kundens klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="a891c-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="a891c-159">Klicka **Inställningar**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="a891c-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="a891c-160">Välj fliken **MSSP.**</span><span class="sxs-lookup"><span data-stu-id="a891c-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="a891c-161">Ange **Program-ID från** det första steget och ditt **klientorganisations-ID.**</span><span class="sxs-lookup"><span data-stu-id="a891c-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="a891c-162">Klicka **på Auktorisera program**.</span><span class="sxs-lookup"><span data-stu-id="a891c-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="a891c-163">Nu kan du ladda ned den relevanta konfigurationsfilen för SIEM och ansluta till Defender för Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="a891c-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="a891c-164">Mer information finns i Hämta [aviseringar till dina SIEM-verktyg.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="a891c-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="a891c-165">I filen ArcSight configuration file /Splunk Authentication Properties skriver du programnyckeln manuellt genom att ange det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="a891c-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="a891c-166">I stället för att skaffa en uppdateringstoken i portalen använder du skriptet från föregående steg för att skaffa en uppdateringstoken (eller skaffa den på annat sätt).</span><span class="sxs-lookup"><span data-stu-id="a891c-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="a891c-167">Hämta aviseringar från MSSP-klientens klientorganisation med API:er</span><span class="sxs-lookup"><span data-stu-id="a891c-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="a891c-168">Information om hur du hämtar aviseringar med HJÄLP av REST API finns i [Hämta aviseringar med REST API.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="a891c-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="a891c-169">Se även</span><span class="sxs-lookup"><span data-stu-id="a891c-169">See also</span></span>
- [<span data-ttu-id="a891c-170">Bevilja MSSP åtkomst till portalen</span><span class="sxs-lookup"><span data-stu-id="a891c-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="a891c-171">Få åtkomst till MSSP-kundportalen</span><span class="sxs-lookup"><span data-stu-id="a891c-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="a891c-172">Konfigurera varningsaviseringar</span><span class="sxs-lookup"><span data-stu-id="a891c-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
