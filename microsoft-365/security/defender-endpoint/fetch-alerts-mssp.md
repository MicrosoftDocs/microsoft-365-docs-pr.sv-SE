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
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076609"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Hämta aviseringar från MSSP-kundklientorganisationen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Den här åtgärden vidtas av MSSP.


Du kan hämta aviseringar på två sätt:
- Använda SIEM-metoden
- Använda API:er

## <a name="fetch-alerts-into-your-siem"></a>Hämta aviseringar till din SIEM

Om du vill hämta aviseringar till ditt SIEM-system måste du göra följande:

Steg 1: Skapa ett program från tredje part

Steg 2: Få åtkomst och uppdatera token från kundens klientorganisation
 
Steg 3: Tillåt ditt program i Microsoft Defender Säkerhetscenter
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Steg 1: Skapa ett program i Azure Active Directory (Azure AD)
 
Du måste skapa ett program och ge det behörighet att hämta aviseringar från kundens Microsoft Defender för Slutpunktsklientorganisation.

1. Logga in på [Azure AD-portalen](https://aad.portal.azure.com/).

2. Välj **Azure Active**  >  **Directory-appregistreringar**.
 
3. Klicka **på Ny registrering**.

4. Ange följande värden:

    - Namn: \<Tenant_name\> SIEM MSSP-koppling (Tenant_name med klientorganisationens visningsnamn)
 
    - Kontotyper som stöds: Endast konto i denna organisationskatalog 
    - Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector` (replace <domain_name> with the tenant name)

5. Klicka **på Registrera**. Programmet visas i listan med program som du äger.

6. Markera programmet och klicka sedan på **Översikt.**

7. Kopiera värdet från fältet **Application (client) ID** till en säker plats. Det behöver du i nästa steg.

8. Välj **Certifikat & hemligheter i** panelen för det nya programmet.

9. Klicka **på Ny klienthemlighet.**

    - Beskrivning: Ange en beskrivning för nyckeln.
    - Går ut: Välj **om 1 år**

 
10. Klicka **på** Lägg till , kopiera värdet för klienthemligheten till en säker plats, du behöver detta i nästa steg.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Steg 2: Få åtkomst och uppdatera token från kundens klientorganisation
I det här avsnittet får du veta hur du använder ett PowerShell-skript för att hämta tokens från kundens klientorganisation. Det här skriptet använder programmet från föregående steg för att få åtkomst och uppdatera tokens med OAuth-auktoriseringskodflödet.

När du har lämnat in dina autentiseringsuppgifter måste du ge medgivande till programmet så att programmet etableras i kundens klientorganisation.


1. Skapa en ny mapp och ge den ett namn: `MsspTokensAcquisition` .

2. Ladda ned [modulen LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) och spara den i `MsspTokensAcquisition` mappen.

    >[!NOTE]
    >Ersätt med på rad `authorzationUrl` `authorizationUrl` 30.

3. Skapa en fil med följande innehåll och spara den med `MsspTokensAcquisition.ps1` namnet i mappen:
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
4. Öppna en PowerShell-kommandotolk med förhöjd behörighet i `MsspTokensAcquisition` mappen.

5. Kör följande kommando:`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Ange följande kommandon: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Ersätt \<client_id\> med det program **-ID (klient-ID)** du fick i föregående steg.
    - Ersätt \<app_key\> med **klienthemligheten som** du skapade från föregående steg.
    - Ersätt \<customer_tenant_id\> med kundens **klientorganisations-ID.** 
 

7. Du uppmanas att ange dina autentiseringsuppgifter och ditt medgivande. Ignorera sidomdirigeringen.

8. I PowerShell-fönstret får du en åtkomsttoken och en uppdateringstoken. Spara uppdateringstoken för att konfigurera SIEM-kopplingen. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Steg 3: Tillåt ditt program i Microsoft Defender Säkerhetscenter
Du måste tillåta programmet som du skapade i Microsoft Defender Säkerhetscenter.
 
Du måste ha behörigheten **Hantera portalsysteminställningar** för att tillåta programmet. Annars måste du begära att kunden tillåter programmet åt dig.

1. Gå till `https://securitycenter.windows.com?tid=<customer_tenant_id>` (ersätt \<customer_tenant_id\> med kundens klientorganisations-ID.

2. Klicka **på Inställningar**  >  **SIEM.** 

3. Välj fliken **MSSP.**

4. Ange **Program-ID från** det första steget och ditt **klientorganisations-ID.**

5. Klicka **på Auktorisera program**. 

 
Nu kan du ladda ned den relevanta konfigurationsfilen för SIEM och ansluta till Defender för Endpoint API. Mer information finns i Hämta [aviseringar till dina SIEM-verktyg.](configure-siem.md)
 

- I filen ArcSight configuration file /Splunk Authentication Properties skriver du programnyckeln manuellt genom att ange det hemliga värdet.
- I stället för att skaffa en uppdateringstoken i portalen använder du skriptet från föregående steg för att skaffa en uppdateringstoken (eller skaffa den på annat sätt).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Hämta aviseringar från MSSP-klientens klientorganisation med API:er
 
Information om hur du hämtar aviseringar med HJÄLP av REST API finns i [Hämta aviseringar med REST API.](pull-alerts-using-rest-api.md)


## <a name="see-also"></a>Se även
- [Bevilja MSSP-åtkomst till portalen](grant-mssp-access.md)
- [Få åtkomst till kundportalen för MSSP](access-mssp-portal.md)
- [Konfigurera aviseringsmeddelanden](configure-mssp-notifications.md)
