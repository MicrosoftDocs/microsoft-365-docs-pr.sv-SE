---
title: Skapa ett program för åtkomst till Microsoft Defender för slutpunkt utan användare
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6182b4cb0d1f648f33c3a7fc4da4c648d8996bcd
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770619"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>Partneråtkomst via Microsoft Defender för slutpunkts-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

På den här sidan beskrivs hur du skapar ett Azure Active Directory -program (Azure AD) för att få programmässiga åtkomst till Microsoft Defender för Endpoint åt dina kunder.


Microsoft Defender för slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De HÄR API:erna hjälper dig att automatisera arbetsflöden och nya funktioner baserat på Microsoft Defender för Slutpunkt-funktioner. API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du vidta följande steg för att använda API:er:
- Skapa ett **Azure AD-program med** flera innehavare.
- Få auktoriserat(medgivande) av din kundadministratör för programmet för att få tillgång till Defender för de Endpoint-resurser som behövs.
- Hämta en åtkomsttoken med det här programmet.
- Använd tokenet för att få åtkomst till Microsoft Defender för Endpoint API.

Följande steg vägleder dig hur du skapar ett Azure AD-program, hämtar en åtkomsttoken till Microsoft Defender för Endpoint och verifierar token.

## <a name="create-the-multi-tenant-app"></a>Skapa appen för flera innehavare

1. Logga in på [Azure-klienten med](https://portal.azure.com) användare som har **rollen global** administratör.

2. Gå till **Azure Active Directory**  >  **Appregistreringar**  >  **Ny registrering.** 

   ![Bild av Microsoft Azure navigering till registrering av program](images/atp-azure-new-app2.png)

3. I registreringsformuläret:

    - Välj ett namn på programmet.

    - Kontotyper som stöds – konton i valfri organisationskatalog.

    - Omdirigera URI – typ: Webb, URI: https://portal.azure.com

    ![Bild på registrering Microsoft Azure partnerprogram](images/atp-api-new-app-partner.png)


4. Tillåt att programmet får åtkomst till Microsoft Defender för Endpoint och tilldela det med minimal mängd behörigheter som krävs för att slutföra integreringen.

   - Välj API-behörigheter Lägg till **behörighetS-API:er** som min organisation använder för  >    >   > **WindowsDefenderATP** och välj på **WindowsDefenderATP.**

   - **Obs!** *WindowsDefenderATP* visas inte i den ursprungliga listan. Börja skriva namnet i textrutan så att det visas.

   ![lägg till behörighet](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a>Begära API-behörigheter

   Ta reda på vilken behörighet du behöver i avsnittet **Behörigheter** i API:t som du vill anropa. Till exempel:

   - Om [du vill köra avancerade](run-advanced-query-api.md)frågor väljer du behörigheten Kör avancerade frågor
   
   - Om [du vill isolera en enhet](isolate-machine.md)väljer du behörigheten Isolera dator

   I följande exempel använder vi **behörigheten Läs alla** aviseringar:

   Välj **Avisering om**  >  **programbehörigheter.Read.All >** på Lägg till **behörigheter**

   ![appbehörigheter](images/application-permissions.png)


5. Välj **Bevilja medgivande**

    - **Obs!** Varje gång du lägger till behörighet måste du välja **Bevilja medgivande** för att den nya behörigheten ska gälla.

    ![Bild av bevilja behörigheter](images/grant-consent.png)

6. Gör programmet hemligt.

    - Välj **Certifikat & hemligheter ,** lägg till en beskrivning av hemligheten och välj Lägg **till**.

    **Viktigt:** Efter att du klickat på Lägg **till kopierar du det genererade hemliga värdet**. Du kommer inte att kunna hämta igen när du har lämnat!

    ![Bild av skapa programnyckel](images/webapp-create-key2.png)

7. Skriv ned ditt program-ID:

   - Gå till Översikt på **programsidan och** kopiera följande information:

   ![Bild på skapad app-ID](images/app-id.png)

8. Lägg till programmet i kundens klientorganisation.

    Du behöver att programmet ska godkännas i varje kundklientorganisation där du tänker använda det. Det beror på att ditt program interagerar med Microsoft Defender för Endpoint-programmet åt din kund.

    En användare med **global administratör** från kundens klientorganisation måste välja medgivandelänken och godkänna programmet.

    Medgivandelänken är i formuläret:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Där 00000000-0000-0000-0000-00000000000 ska ersättas med ditt Program-ID

    När du klickat på medgivandelänken loggar du in med den globala administratören för kundens klientorganisation och godkänner programmet.

    ![Bild av medgivande](images/app-consent-partner.png)

    Dessutom måste du be kunden om deras klientorganisations-ID och spara det för framtida användning när du hämtar token.

- **Klart!** Du har registrerat ett program! 
- Se exempel nedan för insamling och validering av token.

## <a name="get-an-access-token-example"></a>Hämta ett exempel på åtkomsttoken:

**Obs!** Om du vill få åtkomsttoken åt kunden använder du kundens klientorganisations-ID vid följande tokeninköp.

<br>Mer information om AAD token finns i [AAD-självstudiekursen](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>Använda PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a>Med hjälp av C#:

>Koden nedan testades med Nuget Microsoft.IdentityModel.Clients.ActiveDirectory

- Skapa ett nytt konsolprogram
- Installera NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Lägg till nedan med

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Kopiera/klistra in nedanstående kod i programmet (glöm inte att uppdatera de tre variablerna: ```tenantId, appId, appSecret``` )

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


### <a name="using-python"></a>Använda Python

Se Hämta [token med Python](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>Använda Avokrypt

> [!NOTE]
> Följande procedur ska vara Avig för Windows är redan installerad på datorn

- Öppna ett kommandofönster
- Ange CLIENT_ID ditt Azure-program-ID
- Ställ CLIENT_SECRET till Azure-programhemligheten
- Ange TENANT_ID azure-klientorganisations-ID för kunden som vill använda ditt program för att få åtkomst till Microsoft Defender för endpoint-programmet
- Kör följande kommando:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Du får ett svar på formuläret:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Verifiera token

Sanity-kontroll för att kontrollera att du har fått ett korrekt token:
- Kopiera/klistra in [i JWT](https://jwt.ms) den token du får i föregående steg för att avkoda den
- Verifiera att du får ett anspråk om "roller" med rätt behörighet
- På skärmbilden nedan kan du se en avkodad token som förvärvats från ett program med flera behörigheter till Microsoft Defender för Slutpunkt:
- Anspråket "tid" är det klientorganisations-ID som token tillhör.

![Bild på tokenverifiering](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Använda token för att komma åt Microsoft Defender för Endpoint API

- Välj det API du vill använda. Mer information finns i Microsoft Defender som stöds [för slutpunkts-API:er](exposed-apis-list.md)
- Ange rubriken Auktorisering i http-begäran som du skickar till "Bearer {token}" (Bearer är auktoriseringsschemat)
- Förfallodatum för token är 1 timme (du kan skicka mer än en begäran med samma token)

- Exempel på att skicka en begäran om att få en lista med aviseringar **med C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Se även
- [Microsoft Defender för Endpoint API:er som stöds](exposed-apis-list.md)
- [Åtkomst till Microsoft Defender för Endpoint åt en användare](exposed-apis-create-app-nativeapp.md)
