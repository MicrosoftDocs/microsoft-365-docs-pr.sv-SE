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
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

På den här sidan beskrivs hur du skapar ett program för att få programmerings åtkomst till Microsoft 365 Defender åt en och samma användare.

Om du behöver programmatisk åtkomst till Microsoft 365 Defender utan en definierad användare (om du till exempel skriver en bakgrunds program eller en daemon) läser du [skapa en app för att få åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md). Om du behöver ge åtkomst till flera klient organisationer, till exempel om du har en stor organisation eller en grupp kunder – läser du [skapa en app med partner åtkomst till Microsoft 365 Defender API: er](api-partner-access.md). Om du inte är säker på vilken typ av åtkomst du behöver läser du [komma igång](api-access.md).

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er. Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsoft 365 Defender-funktionerna. Denna API-åtkomst kräver autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

I allmänhet måste du göra följande för att använda dessa API:

- Skapa ett Azure Active Directory (Azure AD)-program.
- Skaffa en åtkomsttoken med det här programmet.
- Använd token för att få åtkomst till Microsoft 365 Defender API.

I den här artikeln förklarar vi hur du:

- Skapa ett Azure AD-program
- Skaffa en åtkomsttoken till Microsoft 365 Defender
- Validera token

> [!NOTE]
> När du använder Microsoft 365 Defender API för en användare behöver du rätt program behörigheter och användar behörigheter.

> [!TIP]
> Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API: t.

## <a name="create-an-app"></a>Skapa en app

1. Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .

2. Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. Välj ett namn för programmet i formuläret och ange följande information för omdirigerings-URI: n och välj sedan **Registrera**.

   ![Bild av fönstret Skapa programfönster](../../media/nativeapp-create2.PNG)

   - **Program typ:** Offentlig klient
   - **OMDIRIGERA URI:**https://portal.azure.com

4. På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**. Ditt program kan nu komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan. Du måste börja skriva dess namn i text rutan för att se det.

   ![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - Välj **delegerade behörigheter**. Välj relevanta behörigheter för ditt scenario (till exempel **incident. Read**) och välj sedan **Add Permissions**.

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Du måste välja relevanta behörigheter för scenariot. *Läs alla händelser* är bara ett exempel. Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API som du vill ringa.
    >
    > Om du till exempel vill [köra avancerade frågor](api-advanced-hunting.md)väljer du "kör avancerade frågor". Om du vill [isolera en enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)väljer du "isolera datorns tillstånd".

5. Välj **ge administratörs medgivande**. Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.

   ![Bild av beviljande behörigheter](../../media/grant-consent-delegated.PNG)

6. Spela in ditt program-ID och klient-ID något säkert. De visas under **Översikt** på din program sida.

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Skaffa en åtkomsttoken

Mer information om Azure Active Directory-tokens finns i [själv studie kursen för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="get-an-access-token-using-powershell"></a>Skaffa en åtkomsttoken med PowerShell

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

## <a name="validate-the-token"></a>Validera token

1. Kopiera och klistra in token i [JWT](https://jwt.ms) för att avkoda det.
1. Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.

I följande bild kan du se ett avkodat token från en app, med ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Använda token för att komma åt Microsoft 365 Defender API

1. Välj det API du vill använda (incidenter eller avancerad jakt). Mer information finns i [Microsoft 365 Defender API: n](api-supported.md).
2. I den http-begäran som du ska skicka kan du ange tillstånds huvudet till `"Bearer" <token>` , *innehavaren* är ett godkännande och *token* som verifierad token.
3. Token upphör att gälla inom en timme. Du kan skicka fler än en begäran under tiden med samma token.

I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Gå till API för Microsoft 365 Defender](api-access.md)
- [Skapa en ' Hej världen '-App](api-hello-world.md)
- [Skapa en app för åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md)
- [Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er](api-partner-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [OAuth 2,0-auktorisering för användare inloggning och API-åtkomst](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
