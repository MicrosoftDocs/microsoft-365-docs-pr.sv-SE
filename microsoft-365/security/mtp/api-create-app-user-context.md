---
title: Skapa en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning
description: Lär dig hur du får åtkomst till Microsoft 365 Defender-API:er för en användares räkning.
keywords: åtkomst för användare, api, program, användare, åtkomsttoken, token,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d443334a00b5247525a2cdba98a11cfe0f515193
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928468"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Skapa en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

På den här sidan beskrivs hur du skapar ett program för att få programmeringsåtkomst till Microsoft 365 Defender för en enskild användares räkning.

Om du behöver programmeringsåtkomst till Microsoft 365 Defender utan en definierad användare (till exempel om du skriver en bakgrundsapp eller ett bakgrundsprogram) kan du gå till Skapa en app för att få åtkomst till [Microsoft 365 Defender](api-create-app-web.md)utan en användare. Om du behöver ge åtkomst för flera klientorganisationar – till exempel om du arbetar för en stor organisation eller en grupp kunder – kan du gå till Skapa en app med partneråtkomst till [Microsoft 365 Defender-API:er.](api-partner-access.md) Om du är osäker på vilken typ av åtkomst du behöver kan du gå till [Komma igång.](api-access.md)

Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er. De HÄR API:erna hjälper dig att automatisera arbetsflöden och använda funktionerna i Microsoft 365 Defender. Den här API-åtkomsten kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du göra följande för att använda följande API:er:

- Skapa ett Azure Active Directory-program (Azure AD).
- Hämta en åtkomsttoken med hjälp av det här programmet.
- Använd token för att få åtkomst till Microsoft 365 Defender API.

I den här artikeln förklaras hur du:

- Skapa ett Azure AD-program
- Hämta en åtkomsttoken till Microsoft 365 Defender
- Verifiera token

> [!NOTE]
> När du får åtkomst till Microsoft 365 Defender API åt en användare behöver du rätt programbehörigheter och användarbehörigheter.

> [!TIP]
> Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API:t.

## <a name="create-an-app"></a>Skapa en app

1. Logga in på [Azure](https://portal.azure.com) som användare med **rollen Global** administratör.

2. Gå till **Azure Active**  >  **Directory-appregistreringar**  >  **Ny registrering.**

   ![Bild av Microsoft Azure och navigering till programregistrering](../../media/atp-azure-new-app2.png)

3. Välj ett namn för programmet i formuläret och ange följande information för omdirigerings-URI:en och välj sedan **Registrera.**

   ![Bild av fönstret Skapa program](../../media/nativeapp-create2.PNG)

   - **Programtyp:** Offentlig klient
   - **Omdirigera URI:**https://portal.azure.com

4. Välj API-behörigheter Lägg till **behörighets-API:er** som min organisation använder >, skriv Microsoft Threat Protection och  >    >   välj Microsoft **Threat Protection.**  Nu kan du komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och visas inte i den ursprungliga listan. Du måste börja skriva namnet i textrutan för att det ska visas.

   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - Välj **delegerade behörigheter.** Välj rätt behörigheter för ditt scenario (till exempel **Incident.Läsa)** och välj sedan Lägg **till behörigheter.**

   ![Bild av API-åtkomst och API-markering](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Du måste välja rätt behörighet för ditt scenario. *Läs alla incidenter* är bara ett exempel. Ta reda på vilken behörighet du behöver i avsnittet **Behörigheter** i det API du vill anropa.
    >
    > Om du till exempel [vill köra avancerade frågor](api-advanced-hunting.md)väljer du behörigheten Kör avancerade frågor. om [du vill isolera en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)enhet väljer du behörigheten "Isolera dator".

5. Välj **Bevilja administratörsmedgivande.** Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande för** att den ska gälla.

   ![Bild av Bevilja behörigheter](../../media/grant-consent-delegated.PNG)

6. Spela in ditt program-ID och ditt klient-ID någonstans säkert. De visas under Översikt **på** din programsida.

   ![Bild på skapat program-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Hämta en åtkomsttoken

Mer information om Azure Active Directory-token finns i självstudiekursen [om Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Hämta en åtkomsttoken med hjälp av PowerShell

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

## <a name="validate-the-token"></a>Verifiera token

1. Kopiera och klistra in tokenet [i JWT för](https://jwt.ms) att avkoda det.
1. Kontrollera att rollerna *gör* anspråk i den avkodade token innehåller de önskade behörigheterna.

I följande bild visas en avkodad token som förvärvats från en app, med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:

![Bild på tokenverifiering](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Använda token för att få åtkomst till Microsoft 365 Defender API

1. Välj det API du vill använda (ärenden eller avancerad sökning). Mer information finns i Microsoft [365 Defender-API:er som stöds.](api-supported.md)
2. I http-begäran som du ska skicka ställer du in auktoriseringsrubriken på , Bearer är auktoriseringsschemat och token som `"Bearer" <token>` din verifierade  token. 
3. Tokenet förfaller inom en timme. Du kan skicka mer än en begäran under denna tid med samma token.

I följande exempel visas hur du skickar en begäran för att få en lista över incidenter **med hjälp av C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över API:er för Microsoft 365 Defender](api-overview.md)
- [Få åtkomst till API:er för Microsoft 365 Defender](api-access.md)
- [Skapa appen Hej världen](api-hello-world.md)
- [Skapa en app för att komma åt Microsoft 365 Defender utan en användare](api-create-app-web.md)
- [Skapa en app med partneråtkomst för flera innehavare till API:er för Microsoft 365 Defender](api-partner-access.md)
- [Läs mer om API-begränsningar och -licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
