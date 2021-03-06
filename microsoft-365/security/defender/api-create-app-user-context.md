---
title: Skapa en app för att Microsoft 365 Defender-API:er för en användares räkning
description: Lär dig hur du Microsoft 365 Defender-API:er åt en användare.
keywords: åtkomst, på uppdrag av användare, api, program, användare, åtkomsttoken, token,
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
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076705"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Skapa en app för att Microsoft 365 Defender-API:er för en användares räkning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

På den här sidan beskrivs hur du skapar ett program för att få programbehörighet till Microsoft 365 Defender för en enskild användare.

Om du behöver programåtkomst till Microsoft 365 Defender utan en definierad användare (om du till exempel skriver en bakgrundsapp eller ett bakgrundsprogram) kan du gå till Skapa en app för att komma åt Microsoft 365 Defender utan en [användare.](api-create-app-web.md) Om du behöver ge åtkomst för flera klientorganisationar – till exempel om du arbetar i en stor organisation eller en grupp kunder – kan du gå till Skapa en app med partneråtkomst till [Microsoft 365 Defender-API:er.](api-partner-access.md) Om du är osäker på vilken typ av åtkomst du behöver kan du gå till [Komma igång.](api-access.md)

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De här API:erna hjälper dig att automatisera arbetsflöden och Microsoft 365 av Defenders funktioner. Den här API-åtkomsten kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du vidta följande steg för att använda följande API:er:

- Skapa ett Azure Active Directory (Azure AD).
- Hämta en åtkomsttoken med det här programmet.
- Använd tokenet för att komma Microsoft 365 Defender API.

I den här artikeln förklaras hur du:

- Skapa ett Azure AD-program
- Hämta en åtkomsttoken för Microsoft 365 Defender
- Verifiera token

> [!NOTE]
> När du öppnar Microsoft 365 Defender API åt en användare behöver du rätt programbehörigheter och användarbehörigheter.

> [!TIP]
> Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API:t.

## <a name="create-an-app"></a>Skapa en app

1. Logga in i [Azure](https://portal.azure.com) som en användare med **rollen Global** administratör.

2. Gå till **Azure Active Directory**  >  **Appregistreringar**  >  **Ny registrering.**

   ![Bild av Microsoft Azure navigering till registrering av program](../../media/atp-azure-new-app2.png)

3. Välj ett namn för programmet i formuläret och ange följande information för omdirigerings-URI:en och välj sedan **Registrera**.

   ![Bild av fönstret Skapa program](../../media/nativeapp-create2.PNG)

   - **Programtyp:** Offentlig klient
   - **Omdirigera URI:**https://portal.azure.com

4. På programsidan väljer du **API-behörigheter** Lägg till  >    >  **behörighets-API:er** som min organisation använder >, skriver **Microsoft Threat Protection** och väljer Microsoft Threat Protection . Appen kan nu komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn Microsoft 365 Defender och visas inte i den ursprungliga listan. Du måste börja skriva namnet i textrutan för att det ska visas.

   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - Välj **Delegerade behörigheter**. Välj relevanta behörigheter för ditt scenario (till exempel **Incident.Läsa)** och välj sedan Lägg **till behörigheter.**

   ![Bild av val av API-åtkomst och API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Du måste välja rätt behörighet för ditt scenario. *Läs alla incidenter* är bara ett exempel. Information om vilken behörighet du behöver finns i avsnittet **Behörigheter i** det API du vill anropa.
    >
    > Om du till exempel [vill köra avancerade frågor](api-advanced-hunting.md)väljer du behörigheten Kör avancerade frågor. om [du vill isolera en](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)enhet väljer du behörigheten "Isolera dator".

5. Välj **Bevilja administratörsmedgivande**. Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande** för att den ska gälla.

   ![Bild av bevilja behörigheter](../../media/grant-consent-delegated.PNG)

6. Spela in ditt program-ID och ditt klient-ID på ett säkert ställe. De visas under Översikt **på** din programsida.

   ![Bild på skapad app-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Hämta en åtkomsttoken

Mer information om hur Azure Active Directory tokens finns i självstudiekursen [för Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Hämta en åtkomsttoken med Hjälp av PowerShell

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

1. Kopiera och klistra in tokenet i [JWT för](https://jwt.ms) att avkoda det.
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
- [Skapa en Hello world-app](api-hello-world.md)
- [Skapa en app för åtkomst Microsoft 365 Defender utan användare](api-create-app-web.md)
- [Skapa en app med partner med flera klientorganisationens åtkomst Microsoft 365 Defender-API:er](api-partner-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)