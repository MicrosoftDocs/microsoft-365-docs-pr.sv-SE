---
title: 'Åtkomst till Microsoft 365 Defender API: er med för användare'
description: 'Lär dig hur du kommer åt Microsoft 365 Defender API: er med för användare'
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847362"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="1ce60-104">Åtkomst till Microsoft 365 Defender API: er för användare</span><span class="sxs-lookup"><span data-stu-id="1ce60-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1ce60-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1ce60-105">**Applies to:**</span></span>
- <span data-ttu-id="1ce60-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ce60-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1ce60-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="1ce60-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1ce60-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="1ce60-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="1ce60-109">På den här sidan beskrivs hur du skapar ett program för att få programmatisk åtkomst till Microsoft 365 Defender åt en användare.</span><span class="sxs-lookup"><span data-stu-id="1ce60-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="1ce60-110">Om du behöver program mässig åtkomst till Microsoft 365 Defender utan en användare kan du läsa [skapa en app för att få åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="1ce60-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="1ce60-111">Om du inte är säker på vilken åtkomst du behöver läser du [Microsoft 365 Defender API: er](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ce60-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="1ce60-112">Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er.</span><span class="sxs-lookup"><span data-stu-id="1ce60-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1ce60-113">Dessa API: er gör att du kan automatisera arbets flöden och förnyas baserat på Microsoft 365 Defender-funktioner.</span><span class="sxs-lookup"><span data-stu-id="1ce60-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1ce60-114">För API-åtkomst krävs autentisering med OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="1ce60-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1ce60-115">Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="1ce60-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1ce60-116">I allmänhet måste du utföra följande steg för att använda API:</span><span class="sxs-lookup"><span data-stu-id="1ce60-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="1ce60-117">Skapa ett AAD-program</span><span class="sxs-lookup"><span data-stu-id="1ce60-117">Create an AAD application</span></span>
- <span data-ttu-id="1ce60-118">Skaffa en åtkomsttoken med det här programmet</span><span class="sxs-lookup"><span data-stu-id="1ce60-118">Get an access token using this application</span></span>
- <span data-ttu-id="1ce60-119">Använda token för att få åtkomst till Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1ce60-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="1ce60-120">På den här sidan förklaras hur du skapar ett AAD-program, hämtar en åtkomsttoken till Microsoft 365 Defender och validerar token.</span><span class="sxs-lookup"><span data-stu-id="1ce60-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="1ce60-121">När du använder Microsoft 365 Defender API för en användare behöver du rätt program behörighet och användar behörighet.</span><span class="sxs-lookup"><span data-stu-id="1ce60-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="1ce60-122">Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API: t.</span><span class="sxs-lookup"><span data-stu-id="1ce60-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1ce60-123">Skapa en app</span><span class="sxs-lookup"><span data-stu-id="1ce60-123">Create an app</span></span>

1. <span data-ttu-id="1ce60-124">Logga in på [Azure](https://portal.azure.com) med den användare som har rollen **Global administratör** .</span><span class="sxs-lookup"><span data-stu-id="1ce60-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="1ce60-125">Navigera till **Azure Active Directory** -  >  **programregistreringar**  >  **ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="1ce60-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1ce60-127">Ange följande information i registreringen från och klicka sedan på **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="1ce60-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Bild av fönstret Skapa programfönster](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="1ce60-129">**Namn:** Ditt program namn</span><span class="sxs-lookup"><span data-stu-id="1ce60-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="1ce60-130">**Program typ:** Offentlig klient</span><span class="sxs-lookup"><span data-stu-id="1ce60-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="1ce60-131">**OMDIRIGERA URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="1ce60-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="1ce60-132">Om du vill göra det möjligt för din app att komma åt Microsoft 365 Defender och tilldela behörigheter, väljer du **API-behörigheter**  >  **Lägg till behörighets** -API: er för att lägga till behörigheter i  >  **APIs my organization uses** >, Skriv **Microsoft 365 Defender** och sedan **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="1ce60-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="1ce60-133">Microsoft 365 Defender visas inte i den ursprungliga listan.</span><span class="sxs-lookup"><span data-stu-id="1ce60-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="1ce60-134">Du måste börja skriva dess namn i text rutan för att se det.</span><span class="sxs-lookup"><span data-stu-id="1ce60-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Bild av API-åtkomst och API-val](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="1ce60-136">Välj **delegerade behörigheter** > välja relevanta behörigheter för scenariot, **t. ex.** **Add permissions**</span><span class="sxs-lookup"><span data-stu-id="1ce60-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Bild av API-åtkomst och API-val](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="1ce60-138">Du måste välja relevanta behörigheter.</span><span class="sxs-lookup"><span data-stu-id="1ce60-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="1ce60-139">Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API du är intresse rad av.</span><span class="sxs-lookup"><span data-stu-id="1ce60-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="1ce60-140">Klicka på **bevilja medgivande**</span><span class="sxs-lookup"><span data-stu-id="1ce60-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="1ce60-141">Varje gång du lägger till behörighet måste du klicka på **bevilja medgivande** för att den nya behörigheten ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="1ce60-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Bild av beviljande behörigheter](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="1ce60-143">Skriv in ditt program-ID och ditt klient-ID:</span><span class="sxs-lookup"><span data-stu-id="1ce60-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="1ce60-144">Gå till **Översikt** och kopiera följande på program sidan:</span><span class="sxs-lookup"><span data-stu-id="1ce60-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1ce60-146">Skaffa en åtkomsttoken med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ce60-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="1ce60-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1ce60-147">Related topics</span></span>
- [<span data-ttu-id="1ce60-148">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ce60-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1ce60-149">Åtkomst till Microsoft 365 Defender med program kontext</span><span class="sxs-lookup"><span data-stu-id="1ce60-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
