---
title: Partneråtkomst via Microsoft 365 Defender-API:er
description: Lär dig hur du skapar en app för att få programmeringsåtkomst till Microsoft 365 Defender åt dina användare.
keywords: partner, åtkomst, api, flerklient, medgivande, åtkomsttoken, app
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070074"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Skapa en app med partneråtkomst till Microsoft 365 Defender-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

På den här sidan beskrivs hur du skapar en Azure Active Directory-app som har programmeringsåtkomst till Microsoft 365 Defender för användare i flera klientorganisationen. Appar med flera klientorganisationer är användbara när du ska använda stora grupper av användare.

Om du behöver programmeringsåtkomst till Microsoft 365 Defender åt en enskild användare kan du gå till Skapa en app för att [komma åt Microsoft 365 Defender-API:er för en användares räkning.](api-create-app-user-context.md) Om du behöver åtkomst utan att en användare uttryckligen definierats (till exempel om du skriver en bakgrundsapp eller bakgrund), se Skapa en app för att komma åt [Microsoft 365 Defender utan en användare.](api-create-app-web.md) Om du är osäker på vilken typ av åtkomst du behöver kan du gå till [Komma igång.](api-access.md)

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De här API:erna hjälper dig att automatisera arbetsflöden och Microsoft 365 av Defenders funktioner. Den här API-åtkomsten kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du vidta följande steg för att använda följande API:er:

- Skapa ett Azure Active Directory (Azure AD).
- Hämta en åtkomsttoken med det här programmet.
- Använd tokenet för att komma Microsoft 365 Defender API.

Eftersom appen har flera klientorganisationsbehörigheter måste du också ha [administratörsmedgivande](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) från varje klientorganisation för dess användares räkning.

I den här artikeln förklaras hur du:

- Skapa ett **Azure AD-program med** flera innehavare
- Få ett auktoriserat medgivande från din användaradministratör för programmet för att få åtkomst Microsoft 365 Defender på de resurser som behövs.
- Hämta en åtkomsttoken för Microsoft 365 Defender
- Verifiera token

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De HÄR API:erna hjälper dig att automatisera arbetsflöden och nyfikna Microsoft 365 Defender-funktioner. API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du vidta följande steg för att använda API:er:

- Skapa ett **Azure AD-program med** flera innehavare.
- Få auktoriserat (godkännande) av din användaradministratör för programmet för att få åtkomst Microsoft 365 Defender-resurser som behövs.
- Hämta en åtkomsttoken med det här programmet.
- Använd tokenet för att komma Microsoft 365 Defender API.

Följande steg hjälper dig att skapa ett Azure AD-program med flera innehavare, få en åtkomsttoken för att Microsoft 365 Defender och verifiera token.

## <a name="create-the-multi-tenant-app"></a>Skapa appen för flera innehavare

1. Logga in i [Azure](https://portal.azure.com) som en användare med **rollen Global** administratör.

2. Gå till **Azure Active Directory**  >  **Appregistreringar**  >  **Ny registrering.**

   ![Bild av Microsoft Azure navigering till registrering av program](../../media/atp-azure-new-app2.png)

3. I registreringsformuläret:

   - Välj ett namn på programmet.
   - Välj **Konton i valfri** organisationskatalog **(Azure AD-katalog) – Multitenant** från Kontotyper som stöds .
   - Fyll i avsnittet **Omdirigera URI.** Välj typ **webb** och ge omdirigerings-URI som **https://portal.azure.com** .

   När du har fyllt i formuläret väljer du **Registrera**.

   ![Bild på formuläret Registrera ett program](../..//media/atp-api-new-app-partner.png)

4. På programsidan väljer du **API-behörigheter** Lägg till  >    >  **behörighets-API:er** som min organisation använder >, skriver **Microsoft Threat Protection** och väljer Microsoft Threat Protection . Appen kan nu komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn Microsoft 365 Defender och visas inte i den ursprungliga listan. Du måste börja skriva namnet i textrutan för att det ska visas.

   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

5. Välj **Programbehörigheter.** Välj relevanta behörigheter för ditt scenario (till exempel **Incident.Läsa.Alla)** och välj sedan Lägg **till behörigheter.**

   ![Bild av val av API-åtkomst och API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Du måste välja rätt behörighet för ditt scenario. *Läs alla incidenter* är bara ett exempel. Information om vilken behörighet du behöver finns i avsnittet **Behörigheter i** det API du vill anropa.
    >
    > Om du till exempel [vill köra avancerade frågor](api-advanced-hunting.md)väljer du behörigheten Kör avancerade frågor. om [du vill isolera en](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)enhet väljer du behörigheten "Isolera dator".

6. Välj **Bevilja administratörsmedgivande**. Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande** för att den ska gälla.

    ![Bild av bevilja behörigheter](../../media/grant-consent.PNG)

7. Om du vill lägga till en hemligt i programmet väljer **du Certifikat &,** lägger till en beskrivning till hemligheten och väljer sedan Lägg **till**.

    > [!TIP]
    > När du har **valt Lägg** till väljer du kopiera **det genererade hemliga värdet**. Du kommer inte att kunna hämta det hemliga värdet när du har lämnat.

    ![Bild av skapa programnyckel](../../media/webapp-create-key2.png)

8. Spela in ditt program-ID och ditt klient-ID på ett säkert ställe. De visas under Översikt **på** din programsida.

   ![Bild på skapad app-ID](../../media/app-and-tenant-ids.png)

9. Lägg till programmet i användarens klientorganisation.

   Eftersom programmet interagerar med Microsoft 365 Defender åt dina användare måste det godkännas för varje klientorganisation för vilken du tänker använda det.

   En **global administratör** från användarens klientorganisation måste visa medgivandelänken och godkänna programmet.

   Medgivandelänken är i formuläret:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Siffrorna ska `00000000-0000-0000-0000-000000000000` ersättas med ditt Program-ID.

   När du klickat på medgivandelänken loggar du in med den globala administratören för användarens klientorganisation och godkänner programmet.

   ![Bild av medgivande](../../media/app-consent-partner.png)

   Du måste också be användaren om deras klientorganisations-ID. Klientorganisations-ID:t är ett av identifierarna som används för att hämta åtkomsttoken.

- **Klart!** Ett program har registrerats!
- Se exempel nedan för insamling och validering av token.

## <a name="get-an-access-token"></a>Hämta en åtkomsttoken

Mer information om Azure AD-token finns i [självstudiekursen om Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Även om exemplen i det här avsnittet uppmuntrar dig att  klistra in i hemliga värden i testsyfte bör du aldrig hårdkoda hemligheter i ett program som körs i produktion. En tredje part kan använda din hemligt för att komma åt resurser. Du kan skydda dina apphemligheter med hjälp av [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates) Ett praktiskt exempel på hur du kan skydda din app finns i Hantera hemligheter i [dina serverappar med Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)

> [!TIP]
> I följande exempel kan du använda en användares klientorganisations-ID för att testa att skriptet fungerar.

### <a name="get-an-access-token-using-powershell"></a>Hämta en åtkomsttoken med Hjälp av PowerShell

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

### <a name="get-an-access-token-using-c"></a>Hämta en åtkomsttoken med C\#

> [!NOTE]
> Följande kod testades med Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Skapa ett nytt konsolprogram.
1. Installera NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Lägg till följande rad:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopiera och klistra in följande kod i programmet (glöm inte att uppdatera de tre variablerna: `tenantId` `clientId` , , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Hämta en åtkomsttoken med Python

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

### <a name="get-an-access-token-using-curl"></a>Få en åtkomsttoken genom att avböja

> [!NOTE]
> Avrullning är förinstallerat på Windows 10, version 1803 och senare. För andra versioner av Windows laddar du ned och installerar verktyget direkt från den [officiella avinstallationswebbplatsen](https://curl.haxx.se/windows/).

1. Öppna en kommandotolk och ange CLIENT_ID ditt Azure-program-ID.
1. Ställ CLIENT_SECRET till Azure-programhemligheten.
1. Ange TENANT_ID Azure-klientorganisations-ID för den användare som vill använda appen för att komma åt Microsoft 365 Defender.
1. Kör följande kommando:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Ett lyckat svar ser ut så här:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Verifiera token

1. Kopiera och klistra in tokenet på [JSON-webbplatsen för webbtokens validator, JWT,](https://jwt.ms) för att avkoda den.
1. Kontrollera att rollerna *som* anges i den avkodade token innehåller de önskade behörigheterna.

På följande bild kan du se en avkodad token som köpts från en app, med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , och ```AdvancedHunting.Read.All``` behörigheter:

![Bild på tokenverifiering](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Använda tokenet för att komma åt Microsoft 365 Defender API

1. Välj det API du vill använda (ärenden eller avancerad sökning). Mer information finns i [Defender-API:Microsoft 365 som stöds.](api-supported.md)
2. I http-begäran som du ska skicka anger du i autentiseringsrubriken till , Bearer som auktoriseringsschema och token som din `"Bearer" <token>` verifierade token.  
3. Tokenet förfaller inom en timme. Du kan skicka mer än en begäran under denna tid med samma token.

I följande exempel visas hur du skickar en begäran om att få en lista över incidenter med **hjälp av C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Översikt över Defender-API:er](api-overview.md)
- [Komma åt Microsoft 365 Defender-API:er](api-access.md)
- [Skapa programmet Hello world](api-hello-world.md)
- [Skapa en app för åtkomst Microsoft 365 Defender utan användare](api-create-app-web.md)
- [Skapa en app för att Microsoft 365 Defender-API:er för en användares räkning](api-create-app-user-context.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Hantera hemligheter i dina serverappar med Azure-tangentvalvet](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)