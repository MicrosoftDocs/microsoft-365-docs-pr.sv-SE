---
title: Skapa en app för åtkomst till Microsoft 365 Defender-API:er för en användares räkning
description: Lär dig hur du får tillgång till Microsoft 365 Defender-API:er för en användares räkning.
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
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="cf278-104">Skapa en app för åtkomst till Microsoft 365 Defender-API:er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="cf278-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cf278-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cf278-105">**Applies to:**</span></span>

- <span data-ttu-id="cf278-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf278-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf278-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="cf278-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cf278-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="cf278-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cf278-109">På den här sidan beskrivs hur du skapar ett program för att få programbehörighet till Microsoft 365 Defender för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="cf278-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="cf278-110">Om du behöver programåtkomst till Microsoft 365 Defender utan en definierad användare (om du till exempel skriver en bakgrundsapp eller bakgrund), se Skapa en app för att komma åt [Microsoft 365 Defender](api-create-app-web.md)utan en användare.</span><span class="sxs-lookup"><span data-stu-id="cf278-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="cf278-111">Om du behöver ge åtkomst för flera klientorganisationar – till exempel om du arbetar i en stor organisation eller en grupp kunder – kan du gå till Skapa ett program med partneråtkomst till [Microsoft 365 Defender-API:er.](api-partner-access.md) Om du är osäker på vilken typ av åtkomst du behöver kan du gå till [Komma igång.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="cf278-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="cf278-112">Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="cf278-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="cf278-113">De här API:erna hjälper dig att automatisera arbetsflöden och utnyttja funktionerna i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="cf278-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="cf278-114">Den här API-åtkomsten kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="cf278-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="cf278-115">Mer information finns i [OAuth 2.0 Auktoriseringskodflöde](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="cf278-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="cf278-116">I allmänhet måste du vidta följande steg för att använda följande API:er:</span><span class="sxs-lookup"><span data-stu-id="cf278-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="cf278-117">Skapa ett Azure Active Directory-program (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cf278-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="cf278-118">Hämta en åtkomsttoken med det här programmet.</span><span class="sxs-lookup"><span data-stu-id="cf278-118">Get an access token using this application.</span></span>
- <span data-ttu-id="cf278-119">Använd tokenet för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="cf278-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="cf278-120">I den här artikeln förklaras hur du:</span><span class="sxs-lookup"><span data-stu-id="cf278-120">This article explains how to:</span></span>

- <span data-ttu-id="cf278-121">Skapa ett Azure AD-program</span><span class="sxs-lookup"><span data-stu-id="cf278-121">Create an Azure AD application</span></span>
- <span data-ttu-id="cf278-122">Hämta en åtkomsttoken till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf278-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="cf278-123">Verifiera token</span><span class="sxs-lookup"><span data-stu-id="cf278-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="cf278-124">När du använder Microsoft 365 Defender API åt en användare behöver du rätt programbehörigheter och användarbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="cf278-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="cf278-125">Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API:t.</span><span class="sxs-lookup"><span data-stu-id="cf278-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="cf278-126">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="cf278-126">Create an app</span></span>

1. <span data-ttu-id="cf278-127">Logga in i [Azure](https://portal.azure.com) som en användare med **rollen Global** administratör.</span><span class="sxs-lookup"><span data-stu-id="cf278-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="cf278-128">Gå till **Azure Active Directory-appregistreringar**  >    >  **Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="cf278-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till programregistrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="cf278-130">Välj ett namn för programmet i formuläret och ange följande information för omdirigerings-URI:en och välj sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="cf278-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Bild av fönstret Skapa program](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="cf278-132">**Programtyp:** Offentlig klient</span><span class="sxs-lookup"><span data-stu-id="cf278-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="cf278-133">**Omdirigera URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="cf278-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="cf278-134">På programsidan väljer du **API-behörigheter** Lägg till  >    >  **behörighetS-API:er** som min organisation använder >, skriver Microsoft Threat Protection och väljer **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="cf278-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="cf278-135">Appen kan nu komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="cf278-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="cf278-136">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="cf278-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="cf278-137">Du måste börja skriva namnet i textrutan för att det ska visas.</span><span class="sxs-lookup"><span data-stu-id="cf278-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="cf278-139">Välj **Delegerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="cf278-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="cf278-140">Välj relevanta behörigheter för ditt scenario (till exempel **Incident.Läsa)** och välj sedan Lägg **till behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="cf278-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Bild av val av API-åtkomst och API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="cf278-142">Du måste välja rätt behörighet för ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="cf278-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="cf278-143">*Läs alla incidenter* är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="cf278-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="cf278-144">Information om vilken behörighet du behöver finns i avsnittet **Behörigheter i** det API du vill anropa.</span><span class="sxs-lookup"><span data-stu-id="cf278-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="cf278-145">Om du till exempel [vill köra avancerade frågor](api-advanced-hunting.md)väljer du behörigheten Kör avancerade frågor. om [du vill isolera en](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)enhet väljer du behörigheten "Isolera dator".</span><span class="sxs-lookup"><span data-stu-id="cf278-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="cf278-146">Välj **Bevilja administratörsmedgivande**.</span><span class="sxs-lookup"><span data-stu-id="cf278-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="cf278-147">Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande** för att den ska gälla.</span><span class="sxs-lookup"><span data-stu-id="cf278-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Bild av bevilja behörigheter](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="cf278-149">Spela in ditt program-ID och ditt klient-ID på ett säkert ställe.</span><span class="sxs-lookup"><span data-stu-id="cf278-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="cf278-150">De visas under Översikt **på** din programsida.</span><span class="sxs-lookup"><span data-stu-id="cf278-150">They're listed under **Overview** on your application page.</span></span>

   ![Bild på skapad app-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="cf278-152">Hämta en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="cf278-152">Get an access token</span></span>

<span data-ttu-id="cf278-153">Mer information om Azure Active Directory-token finns i [självstudiekursen för Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="cf278-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="cf278-154">Hämta en åtkomsttoken med Hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf278-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="cf278-155">Verifiera token</span><span class="sxs-lookup"><span data-stu-id="cf278-155">Validate the token</span></span>

1. <span data-ttu-id="cf278-156">Kopiera och klistra in tokenet i [JWT för](https://jwt.ms) att avkoda det.</span><span class="sxs-lookup"><span data-stu-id="cf278-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="cf278-157">Kontrollera att rollerna *som* anges i den avkodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="cf278-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="cf278-158">På följande bild kan du se en avkodad token som köpts från en app, med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , och ```AdvancedHunting.Read.All``` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="cf278-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild på tokenverifiering](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="cf278-160">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="cf278-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="cf278-161">Välj det API du vill använda (ärenden eller avancerad sökning).</span><span class="sxs-lookup"><span data-stu-id="cf278-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="cf278-162">Mer information finns i Microsoft [365 Defender-API:er som stöds.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="cf278-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="cf278-163">I http-begäran som du ska skicka anger du i autentiseringsrubriken till , Bearer som auktoriseringsschema och token som din `"Bearer" <token>` verifierade token.  </span><span class="sxs-lookup"><span data-stu-id="cf278-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="cf278-164">Tokenet förfaller inom en timme.</span><span class="sxs-lookup"><span data-stu-id="cf278-164">The token will expire within one hour.</span></span> <span data-ttu-id="cf278-165">Du kan skicka mer än en begäran under denna tid med samma token.</span><span class="sxs-lookup"><span data-stu-id="cf278-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="cf278-166">I följande exempel visas hur du skickar en begäran om att få en lista över incidenter med **hjälp av C#**.</span><span class="sxs-lookup"><span data-stu-id="cf278-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="cf278-167">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cf278-167">Related articles</span></span>

- [<span data-ttu-id="cf278-168">Översikt över Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="cf278-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cf278-169">Åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="cf278-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cf278-170">Skapa en Hello world-app</span><span class="sxs-lookup"><span data-stu-id="cf278-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="cf278-171">Skapa en app för att komma åt Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="cf278-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="cf278-172">Skapa en app med partner med flera klientorganisationens åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="cf278-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="cf278-173">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="cf278-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cf278-174">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="cf278-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="cf278-175">OAuth 2.0-auktorisering för användar logga in och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="cf278-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)