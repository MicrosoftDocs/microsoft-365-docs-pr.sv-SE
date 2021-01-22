---
title: Partneråtkomst via Microsoft 365 Defender-API:er
description: Lär dig hur du skapar en app för att få programmeringsåtkomst till Microsoft 365 Defender för dina användares räkning.
keywords: partner, åtkomst, api, flera innehavare, medgivande, åtkomsttoken, app
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
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929404"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="16b02-104">Skapa en app med partneråtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="16b02-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="16b02-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="16b02-105">**Applies to:**</span></span>

- <span data-ttu-id="16b02-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b02-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16b02-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="16b02-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="16b02-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="16b02-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="16b02-109">På den här sidan beskrivs hur du skapar en Azure Active Directory-app som har programmeringsåtkomst till Microsoft 365 Defender för användare i flera klientorganisationar.</span><span class="sxs-lookup"><span data-stu-id="16b02-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="16b02-110">Appar med flera klientorganisationer är användbara när du arbetar med stora grupper av användare.</span><span class="sxs-lookup"><span data-stu-id="16b02-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="16b02-111">Om du behöver programmeringsåtkomst till Microsoft 365 Defender för en enskild användares räkning kan du gå till Skapa en app för att få åtkomst till [Microsoft 365 Defender-API:er för en användares räkning.](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="16b02-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="16b02-112">Om du behöver åtkomst utan att en användare uttryckligen definierats (till exempel om du skriver en bakgrundsapp eller ett bakgrundsljud) kan du gå till Skapa en app för att få åtkomst till [Microsoft 365 Defender](api-create-app-web.md)utan en användare.</span><span class="sxs-lookup"><span data-stu-id="16b02-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="16b02-113">Om du är osäker på vilken typ av åtkomst du behöver kan du gå till [Komma igång.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="16b02-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="16b02-114">Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="16b02-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="16b02-115">De HÄR API:erna hjälper dig att automatisera arbetsflöden och använda funktionerna i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="16b02-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="16b02-116">Den här API-åtkomsten kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="16b02-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="16b02-117">Mer information finns i [OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="16b02-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="16b02-118">I allmänhet måste du göra följande för att använda följande API:er:</span><span class="sxs-lookup"><span data-stu-id="16b02-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="16b02-119">Skapa ett Azure Active Directory-program (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="16b02-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="16b02-120">Hämta en åtkomsttoken med hjälp av det här programmet.</span><span class="sxs-lookup"><span data-stu-id="16b02-120">Get an access token using this application.</span></span>
- <span data-ttu-id="16b02-121">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="16b02-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="16b02-122">Eftersom den här appen är en flera innehavare måste du också ha [administratörsmedgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) från varje klientorganisation för dess användares räkning.</span><span class="sxs-lookup"><span data-stu-id="16b02-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="16b02-123">I den här artikeln förklaras hur du:</span><span class="sxs-lookup"><span data-stu-id="16b02-123">This article explains how to:</span></span>

- <span data-ttu-id="16b02-124">Skapa ett **Azure AD-program med** flera innehavare</span><span class="sxs-lookup"><span data-stu-id="16b02-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="16b02-125">Få auktoriserat medgivande från din användaradministratör för ditt program för att få åtkomst till de Microsoft 365 Defender-resurser som behövs.</span><span class="sxs-lookup"><span data-stu-id="16b02-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="16b02-126">Hämta en åtkomsttoken till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b02-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="16b02-127">Verifiera token</span><span class="sxs-lookup"><span data-stu-id="16b02-127">Validate the token</span></span>

<span data-ttu-id="16b02-128">Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="16b02-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="16b02-129">De HÄR API:erna hjälper dig att automatisera arbetsflöden och nyfikna på microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="16b02-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="16b02-130">API-åtkomsten kräver OAuth2.0-autentisering.</span><span class="sxs-lookup"><span data-stu-id="16b02-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="16b02-131">Mer information finns i [OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="16b02-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="16b02-132">I allmänhet måste du göra följande för att använda API:erna:</span><span class="sxs-lookup"><span data-stu-id="16b02-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="16b02-133">Skapa ett **Azure AD-program med** flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="16b02-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="16b02-134">Få auktoriserat (godkännande) av din användaradministratör för programmet för att få åtkomst till de Microsoft 365 Defender-resurser som behövs.</span><span class="sxs-lookup"><span data-stu-id="16b02-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="16b02-135">Hämta en åtkomsttoken med hjälp av det här programmet.</span><span class="sxs-lookup"><span data-stu-id="16b02-135">Get an access token using this application.</span></span>
- <span data-ttu-id="16b02-136">Använd token för att få åtkomst till Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="16b02-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="16b02-137">Följande steg med guide för hur du skapar ett Azure AD-program med flera innehavare, hämtar en åtkomsttoken till Microsoft 365 Defender och verifierar token.</span><span class="sxs-lookup"><span data-stu-id="16b02-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="16b02-138">Skapa appen för flera innehavare</span><span class="sxs-lookup"><span data-stu-id="16b02-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="16b02-139">Logga in på [Azure](https://portal.azure.com) som användare med **rollen Global** administratör.</span><span class="sxs-lookup"><span data-stu-id="16b02-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="16b02-140">Gå till **Azure Active**  >  **Directory-appregistreringar**  >  **Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="16b02-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Bild av Microsoft Azure och navigering till programregistrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="16b02-142">I registreringsformuläret:</span><span class="sxs-lookup"><span data-stu-id="16b02-142">In the registration form:</span></span>

   - <span data-ttu-id="16b02-143">Välj ett namn för programmet.</span><span class="sxs-lookup"><span data-stu-id="16b02-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="16b02-144">Välj **Konton i valfri** organisationskatalog **(Azure AD-katalog) – Flera användare,** från kontotyper som stöds.</span><span class="sxs-lookup"><span data-stu-id="16b02-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="16b02-145">Fyll i avsnittet **Omdirigera URI.**</span><span class="sxs-lookup"><span data-stu-id="16b02-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="16b02-146">Välj typ **av webb** och ange omdirigerings-URI **https://portal.azure.com** som.</span><span class="sxs-lookup"><span data-stu-id="16b02-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="16b02-147">När du har fyllt i formuläret väljer du **Registrera.**</span><span class="sxs-lookup"><span data-stu-id="16b02-147">After you're done filling out the form, select **Register**.</span></span>

   ![Bild av formuläret Registrera en ansökan](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="16b02-149">Välj API-behörigheter Lägg till **behörighets-API:er** som min organisation använder >, skriv Microsoft Threat Protection och  >    >   välj Microsoft **Threat Protection.** </span><span class="sxs-lookup"><span data-stu-id="16b02-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="16b02-150">Nu kan du komma åt Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="16b02-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="16b02-151">*Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="16b02-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="16b02-152">Du måste börja skriva namnet i textrutan för att det ska visas.</span><span class="sxs-lookup"><span data-stu-id="16b02-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Bild av val av API-behörighet](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="16b02-154">Välj **programbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="16b02-154">Select **Application permissions**.</span></span> <span data-ttu-id="16b02-155">Välj de relevanta behörigheterna för ditt scenario (till exempel **Incident.Läsa.Alla)** och välj sedan Lägg **till behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="16b02-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Bild av API-åtkomst och API-markering](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="16b02-157">Du måste välja relevant behörighet för ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="16b02-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="16b02-158">*Läs alla incidenter* är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="16b02-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="16b02-159">Ta reda på vilken behörighet du behöver i avsnittet **Behörigheter** i det API du vill anropa.</span><span class="sxs-lookup"><span data-stu-id="16b02-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="16b02-160">Om du till exempel [vill köra avancerade frågor](api-advanced-hunting.md)väljer du behörigheten Kör avancerade frågor. om [du vill isolera en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)enhet väljer du behörigheten "Isolera dator".</span><span class="sxs-lookup"><span data-stu-id="16b02-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="16b02-161">Välj **Bevilja administratörsmedgivande.**</span><span class="sxs-lookup"><span data-stu-id="16b02-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="16b02-162">Varje gång du lägger till en behörighet måste du välja **Ge administratörsmedgivande för** att den ska gälla.</span><span class="sxs-lookup"><span data-stu-id="16b02-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Bild av Bevilja behörigheter](../../media/grant-consent.PNG)

7. <span data-ttu-id="16b02-164">Om du vill lägga till en hemligt i programmet väljer du **Certifikat & hemligheter,** lägger till en beskrivning till hemligheten och väljer sedan **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="16b02-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="16b02-165">När du har **valt Lägg** till väljer du kopiera **det genererade hemliga värdet.**</span><span class="sxs-lookup"><span data-stu-id="16b02-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="16b02-166">Du kommer inte att kunna hämta det hemliga värdet när du lämnar det.</span><span class="sxs-lookup"><span data-stu-id="16b02-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild av skapa programnyckel](../../media/webapp-create-key2.png)

8. <span data-ttu-id="16b02-168">Spela in ditt program-ID och ditt klient-ID någonstans säkert.</span><span class="sxs-lookup"><span data-stu-id="16b02-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="16b02-169">De visas under Översikt **på** din programsida.</span><span class="sxs-lookup"><span data-stu-id="16b02-169">They're listed under **Overview** on your application page.</span></span>

   ![Bild på skapat program-ID](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="16b02-171">Lägg till programmet i användarens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="16b02-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="16b02-172">Eftersom programmet interagerar med Microsoft 365 Defender åt dina användare behöver det godkännas för alla klientorganisationen du tänker använda det för.</span><span class="sxs-lookup"><span data-stu-id="16b02-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="16b02-173">En **global administratör** från användarens klientorganisation måste visa medgivandelänken och godkänna programmet.</span><span class="sxs-lookup"><span data-stu-id="16b02-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="16b02-174">Medgivande-länken är av formuläret:</span><span class="sxs-lookup"><span data-stu-id="16b02-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="16b02-175">Siffrorna ska `00000000-0000-0000-0000-000000000000` ersättas med ditt Program-ID.</span><span class="sxs-lookup"><span data-stu-id="16b02-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="16b02-176">När du har klickat på medgivandelänken loggar du in med den globala administratören för användarens klientorganisation och godkänner programmet.</span><span class="sxs-lookup"><span data-stu-id="16b02-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Bild på medgivande](../../media/app-consent-partner.png)

   <span data-ttu-id="16b02-178">Du måste också be användaren om deras klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="16b02-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="16b02-179">Klientorganisations-ID:t är en av identifierarna som används för att hämta åtkomsttoken.</span><span class="sxs-lookup"><span data-stu-id="16b02-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="16b02-180">**Klart!**</span><span class="sxs-lookup"><span data-stu-id="16b02-180">**Done!**</span></span> <span data-ttu-id="16b02-181">Du har registrerat ett program!</span><span class="sxs-lookup"><span data-stu-id="16b02-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="16b02-182">Se exemplen nedan för insamling och validering av token.</span><span class="sxs-lookup"><span data-stu-id="16b02-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="16b02-183">Hämta en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="16b02-183">Get an access token</span></span>

<span data-ttu-id="16b02-184">Mer information om Azure AD-token finns i [självstudiekursen om Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="16b02-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16b02-185">Även om exemplen i det här avsnittet uppmuntrar dig att klistra in i hemliga värden för teständamål, ska du **aldrig hårdkoda** hemligheter i ett program som körs i produktion.</span><span class="sxs-lookup"><span data-stu-id="16b02-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="16b02-186">En tredje part kan använda din hemligt för att komma åt resurser.</span><span class="sxs-lookup"><span data-stu-id="16b02-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="16b02-187">Du kan skydda dina appars hemligheter med hjälp av [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="16b02-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="16b02-188">Ett praktiskt exempel på hur du kan skydda din app finns i Hantera hemligheter [i serverapparna med Azure-nyckelvalv.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="16b02-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="16b02-189">I följande exempel använder du en användares klientorganisations-ID för att testa att skriptet fungerar.</span><span class="sxs-lookup"><span data-stu-id="16b02-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="16b02-190">Hämta en åtkomsttoken med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="16b02-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="16b02-191">Hämta en åtkomsttoken med hjälp av C\#</span><span class="sxs-lookup"><span data-stu-id="16b02-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="16b02-192">Följande kod testades med Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="16b02-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="16b02-193">Skapa ett nytt konsolprogram.</span><span class="sxs-lookup"><span data-stu-id="16b02-193">Create a new console application.</span></span>
1. <span data-ttu-id="16b02-194">Installera NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory.](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="16b02-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="16b02-195">Lägg till följande rad:</span><span class="sxs-lookup"><span data-stu-id="16b02-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="16b02-196">Kopiera och klistra in följande kod i programmet (glöm inte att uppdatera de tre variablerna: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="16b02-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="16b02-197">Hämta en åtkomsttoken med Python</span><span class="sxs-lookup"><span data-stu-id="16b02-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="16b02-198">Få en åtkomsttoken genom att avböja</span><span class="sxs-lookup"><span data-stu-id="16b02-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="16b02-199">Krullning är förinstallerat i Windows 10, versionerna 1803 och senare.</span><span class="sxs-lookup"><span data-stu-id="16b02-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="16b02-200">För andra versioner av Windows laddar du ned och installerar verktyget direkt från den [officiella avbildningswebbplatsen.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="16b02-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="16b02-201">Öppna en kommandotolk och ange CLIENT_ID ditt Azure-program-ID.</span><span class="sxs-lookup"><span data-stu-id="16b02-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="16b02-202">Ställ CLIENT_SECRET till Azure-programhemligheten.</span><span class="sxs-lookup"><span data-stu-id="16b02-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="16b02-203">Ange TENANT_ID Azure-klientorganisations-ID för den användare som vill använda appen för att få åtkomst till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="16b02-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="16b02-204">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16b02-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="16b02-205">Ett lyckat svar ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="16b02-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="16b02-206">Verifiera token</span><span class="sxs-lookup"><span data-stu-id="16b02-206">Validate the token</span></span>

1. <span data-ttu-id="16b02-207">Kopiera och klistra in tokenet på [webbplatsen för JSON-webbtokens validator, JWT,](https://jwt.ms) för att avkoda det.</span><span class="sxs-lookup"><span data-stu-id="16b02-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="16b02-208">Kontrollera att rollerna *gör* anspråk i den avkodade token innehåller de önskade behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="16b02-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="16b02-209">I följande bild visas en avkodad token som förvärvats från en app, med ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:</span><span class="sxs-lookup"><span data-stu-id="16b02-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild på tokenverifiering](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="16b02-211">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="16b02-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="16b02-212">Välj det API du vill använda (ärenden eller avancerad sökning).</span><span class="sxs-lookup"><span data-stu-id="16b02-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="16b02-213">Mer information finns i Microsoft [365 Defender-API:er som stöds.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="16b02-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="16b02-214">I http-begäran som du ska skicka anger du rubriken för auktoriseringen till , Bearer är auktoriseringsschemat och token som `"Bearer" <token>` ditt verifierade  token. </span><span class="sxs-lookup"><span data-stu-id="16b02-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="16b02-215">Tokenet förfaller inom en timme.</span><span class="sxs-lookup"><span data-stu-id="16b02-215">The token will expire within one hour.</span></span> <span data-ttu-id="16b02-216">Du kan skicka mer än en begäran under denna tid med samma token.</span><span class="sxs-lookup"><span data-stu-id="16b02-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="16b02-217">I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med hjälp av C#**.</span><span class="sxs-lookup"><span data-stu-id="16b02-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="16b02-218">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="16b02-218">Related articles</span></span>

- [<span data-ttu-id="16b02-219">Översikt över API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b02-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="16b02-220">Få åtkomst till API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b02-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="16b02-221">Skapa programmet Hello world</span><span class="sxs-lookup"><span data-stu-id="16b02-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="16b02-222">Skapa en app för att komma åt Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="16b02-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="16b02-223">Skapa en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="16b02-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="16b02-224">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="16b02-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="16b02-225">Förstå felkoder</span><span class="sxs-lookup"><span data-stu-id="16b02-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="16b02-226">Hantera hemligheter i dina serverappar med Azure-nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="16b02-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="16b02-227">OAuth 2.0-autentisering för användar logga in och API-åtkomst</span><span class="sxs-lookup"><span data-stu-id="16b02-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
