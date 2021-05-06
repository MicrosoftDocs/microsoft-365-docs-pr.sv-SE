---
title: Distribuera en koppling för att arkivera data på Facebook Business-sidor
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratörer kan konfigurera en inbyggd anslutning för att importera och arkivera Facebook Business-sidor för att Microsoft 365. När dessa data har importerats till Microsoft 365 kan du använda efterlevnadsfunktioner som bevarande av juridiska regler, innehållssökning och bevarandeprinciper för att hantera styrning av din organisations Facebook-data.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "52161638"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="6182a-104">Distribuera en koppling för att arkivera data på Facebook Business-sidor</span><span class="sxs-lookup"><span data-stu-id="6182a-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="6182a-105">Den här artikeln innehåller stegvisa instruktioner för att distribuera en koppling som använder tjänsten Office 365 för att importera data från Facebook Business-sidor till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6182a-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="6182a-106">En översikt över den här processen och en lista över förutsättningar för att distribuera en Facebook-anslutning finns i Konfigurera en anslutning för att [arkivera Facebook-data.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="6182a-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="6182a-107">Steg 1: Skapa en app i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6182a-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="6182a-108">Gå till <https://portal.azure.com> och logga in med autentiseringsuppgifterna för ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="6182a-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Skapa app i AAD](../media/FBCimage1.png)

2. <span data-ttu-id="6182a-110">I det vänstra navigeringsfönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6182a-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Klicka på Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="6182a-112">I det vänstra navigeringsfönstret klickar du **på Appregistreringar (förhandsversion)** och sedan på **Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="6182a-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Klicka på **Appregistreringar (förhandsversion)** och klicka sedan på **Ny registrering**](../media/FBCimage3.png)

4. <span data-ttu-id="6182a-114">Registrera programmet.</span><span class="sxs-lookup"><span data-stu-id="6182a-114">Register the application.</span></span> <span data-ttu-id="6182a-115">Under Omdirigera URI väljer du Webb i listrutan med programtyper och skriver <https://portal.azure.com> sedan i rutan för URI:en.</span><span class="sxs-lookup"><span data-stu-id="6182a-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrera programmet](../media/FBCimage4.png)

5. <span data-ttu-id="6182a-117">Kopiera **program-ID(klient)ID** **och katalog-ID (klientorganisation)** och spara dem i en textfil eller på en annan säker plats.</span><span class="sxs-lookup"><span data-stu-id="6182a-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="6182a-118">Du använder de här ID:erna i senare steg.</span><span class="sxs-lookup"><span data-stu-id="6182a-118">You use these IDs in later steps.</span></span>

   ![Kopiera program-ID och katalog-ID och spara dem](../media/FBCimage5.png)

6. <span data-ttu-id="6182a-120">Gå till **Certifikat & för den nya appen.**</span><span class="sxs-lookup"><span data-stu-id="6182a-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Gå till Certifikat & hemligheter för den nya appen](../media/FBCimage6.png)

7. <span data-ttu-id="6182a-122">Klicka **på Ny klienthemlighet**</span><span class="sxs-lookup"><span data-stu-id="6182a-122">Click **New client secret**</span></span>

   ![Klicka på Ny klienthemlighet](../media/FBCimage7.png)

8. <span data-ttu-id="6182a-124">Skapa en ny hemlig.</span><span class="sxs-lookup"><span data-stu-id="6182a-124">Create a new secret.</span></span> <span data-ttu-id="6182a-125">Skriv hemligheten i beskrivningsrutan och välj sedan en utgångsperiod.</span><span class="sxs-lookup"><span data-stu-id="6182a-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Skriv hemligheten och välj sedan en förfalloperiod](../media/FBCimage8.png)

9. <span data-ttu-id="6182a-127">Kopiera värdet för hemligheten och spara den i en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="6182a-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="6182a-128">Det här är AAD-programhemligheten som du använder i senare steg.</span><span class="sxs-lookup"><span data-stu-id="6182a-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopiera värdet för hemligheten och spara den](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="6182a-130">Steg 2: Distribuera anslutarwebbtjänsten från GitHub till ditt Azure-konto</span><span class="sxs-lookup"><span data-stu-id="6182a-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="6182a-131">Gå till [den GitHub webbplatsen](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) och klicka på Distribuera till **Azure.**</span><span class="sxs-lookup"><span data-stu-id="6182a-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Klicka på Distribuera till Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="6182a-133">När du har **klickat på Distribuera** till Azure omdirigeras du till en Azure-portal med en anpassad mallsida.</span><span class="sxs-lookup"><span data-stu-id="6182a-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="6182a-134">Fyll i Grunderna **och Inställningar** **och** klicka sedan på **Köp**.</span><span class="sxs-lookup"><span data-stu-id="6182a-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="6182a-135">**Prenumeration:** Välj den Azure-prenumeration som du vill distribuera webbtjänsten Facebook Business pages connector.</span><span class="sxs-lookup"><span data-stu-id="6182a-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="6182a-136">**Resursgrupp:** Välj eller skapa en ny resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="6182a-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="6182a-137">En resursgrupp är en behållare som innehåller relaterade resurser för en Azure-lösning.</span><span class="sxs-lookup"><span data-stu-id="6182a-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="6182a-138">**Plats:** Välj en plats.</span><span class="sxs-lookup"><span data-stu-id="6182a-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="6182a-139">**Web App-namn:** Ange ett unikt namn för webbappen för anslutning.</span><span class="sxs-lookup"><span data-stu-id="6182a-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="6182a-140">Namnet måste vara mellan 3 och 18 tecken långt.</span><span class="sxs-lookup"><span data-stu-id="6182a-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="6182a-141">Det här namnet används för att skapa URL-adressen för Azure-apptjänsten. Om du till exempel anger webbappens namn **för fbconnector** så visas Azures apptjänst-URL **fbconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="6182a-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="6182a-142">**tenantId:** Klientorganisations-ID:t för Microsoft 365 organisation som du kopierade när du skapade Facebook-anslutningsappen i Azure Active Directory steg 1.</span><span class="sxs-lookup"><span data-stu-id="6182a-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="6182a-143">**APISecretKey:** Du kan ange vilket värde som helst som hemlig.</span><span class="sxs-lookup"><span data-stu-id="6182a-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="6182a-144">Det här används för att komma åt webbappen för anslutning i steg 5.</span><span class="sxs-lookup"><span data-stu-id="6182a-144">This is used to access the connector web app in Step 5.</span></span>

     ![Klicka på Skapa en resurs och skriv lagringskonto](../media/FBCimage12.png)

3. <span data-ttu-id="6182a-146">När distributionen är lyckad ser sidan ut ungefär som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="6182a-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Klicka Storage konto och klicka sedan på Storage konto](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="6182a-148">Steg 3: Registrera Facebook-appen</span><span class="sxs-lookup"><span data-stu-id="6182a-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="6182a-149">Gå till , logga in med inloggningsuppgifterna för kontot för din <https://developers.facebook.com> organisations Facebook Business-sidor och klicka sedan på Lägg till nytt **program.**</span><span class="sxs-lookup"><span data-stu-id="6182a-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Lägga till en ny app för Facebook-företagssida](../media/FBCimage25.png)

2. <span data-ttu-id="6182a-151">Skapa ett nytt program-ID.</span><span class="sxs-lookup"><span data-stu-id="6182a-151">Create a new app ID.</span></span>

   ![Skapa ett nytt program-ID](../media/FBCimage26.png)

3. <span data-ttu-id="6182a-153">I det vänstra navigeringsfönstret klickar du på **Lägg till produkter** och sedan på **Konfigurera** i **panelen Facebook-inloggning.**</span><span class="sxs-lookup"><span data-stu-id="6182a-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Klicka på Lägg till produkter](../media/FBCimage27.png)

4. <span data-ttu-id="6182a-155">På sidan Integrera Facebook-inloggning klickar du på **Webb.**</span><span class="sxs-lookup"><span data-stu-id="6182a-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Klicka på Webb på sidan Integrera Facebook-inloggning](../media/FBCimage28.png)

5. <span data-ttu-id="6182a-157">Lägg till URL:en för Azure-apptjänsten. till exempel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="6182a-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Lägg till URL:en för Azure-apptjänsten](../media/FBCimage29.png)

6. <span data-ttu-id="6182a-159">Slutför avsnittet Snabbstart i konfigurationen av Facebook-inloggningen.</span><span class="sxs-lookup"><span data-stu-id="6182a-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Slutför avsnittet Snabbstart](../media/FBCimage30.png)

7. <span data-ttu-id="6182a-161">I det vänstra navigeringsfönstret under **Facebook-inloggning** klickar **Inställningar** och lägger till OAuth-omdirigerings-URI i rutan Giltiga **OAuth-omdirigerings-URI:er.**</span><span class="sxs-lookup"><span data-stu-id="6182a-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="6182a-162">Använd formatet **\<connectorserviceuri> /Vyer/FacebookOAuth**, där värdet för connectorserviceuri är Azure-apptjänstens URL för din organisation, till exempel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="6182a-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Lägga till OAuth-omdirigerings-URI i rutan Giltiga OAuth-omdirigerings-URI:er](../media/FBCimage31.png)

8. <span data-ttu-id="6182a-164">I det vänstra navigeringsfönstret klickar du **på Lägg till** produkter och sedan på **Webhooks.**</span><span class="sxs-lookup"><span data-stu-id="6182a-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="6182a-165">Klicka **på Sida** i den nedermenyn **Sida.**</span><span class="sxs-lookup"><span data-stu-id="6182a-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Klicka på Lägg till produkter och sedan på \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="6182a-167">Lägg till Webhooks Callback-URL och lägg till en verifieringstoken.</span><span class="sxs-lookup"><span data-stu-id="6182a-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="6182a-168">Formatet för URL:en för anrop använder du formatet **<connectorserviceuri> /api/FbPageWebhook,** där värdet för connectorserviceuri är Azure-apptjänst-URL:en för din organisation, till exempel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="6182a-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="6182a-169">Verifieringstoken bör likna ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="6182a-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="6182a-170">Kopiera verifieringstoken till en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="6182a-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Lägg till verifieringstoken](../media/FBCimage33.png)

10. <span data-ttu-id="6182a-172">Testa och prenumerera på slutpunkten för feed.</span><span class="sxs-lookup"><span data-stu-id="6182a-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testa och prenumerera på slutpunkten](../media/FBCimage34.png)

11. <span data-ttu-id="6182a-174">Lägg till en sekretess-URL, appikon och företagsanvändning.</span><span class="sxs-lookup"><span data-stu-id="6182a-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="6182a-175">Kopiera även program-ID och programhemlighet till en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="6182a-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Lägga till en sekretess-URL, appikon och företagsanvändning](../media/FBCimage35.png)

12. <span data-ttu-id="6182a-177">Gör appen offentlig.</span><span class="sxs-lookup"><span data-stu-id="6182a-177">Make the app public.</span></span>

    ![Göra appen offentlig](../media/FBCimage36.png)

13. <span data-ttu-id="6182a-179">Lägga till användare i rollen administratör eller testare.</span><span class="sxs-lookup"><span data-stu-id="6182a-179">Add user to the admin or tester role.</span></span>

    ![Lägga till användare i rollen administratör eller testare](../media/FBCimage37.png)

14. <span data-ttu-id="6182a-181">Lägg till **behörigheten Sida med offentlig** innehållsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="6182a-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd behörigheten Sidåtkomst för innehåll](../media/FBCimage38.png)

15. <span data-ttu-id="6182a-183">Lägg till behörigheten Hantera sidor.</span><span class="sxs-lookup"><span data-stu-id="6182a-183">Add Manage Pages permission.</span></span>

    ![Lägg till behörigheten Hantera sidor](../media/FBCimage39.png)

16. <span data-ttu-id="6182a-185">Få programmet granskat av Facebook.</span><span class="sxs-lookup"><span data-stu-id="6182a-185">Get the application reviewed by Facebook.</span></span>

    ![Få programmet granskat av Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="6182a-187">Steg 4: Konfigurera webbprogrammet för anslutning</span><span class="sxs-lookup"><span data-stu-id="6182a-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="6182a-188">Gå till `https://<AzureAppResourceName>.azurewebsites.net` (där AzureAppResourceName är namnet på azure-appresursen som du döpte i steg 4).</span><span class="sxs-lookup"><span data-stu-id="6182a-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="6182a-189">Om namnet till exempel är **fbconnector går** du till `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="6182a-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="6182a-190">Startsidan för appen ser ut som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="6182a-190">The home page of the app will look like the following screenshot:</span></span>

   ![Gå till kopplingswebbappen](../media/FBCimage41.png)

2. <span data-ttu-id="6182a-192">Klicka **på Konfigurera** för att visa en inloggningssida.</span><span class="sxs-lookup"><span data-stu-id="6182a-192">Click **Configure** to display a sign in page.</span></span>

   ![Klicka på Konfigurera för att visa en inloggningssida](../media/FBCimage42.png)

3. <span data-ttu-id="6182a-194">I rutan Klientorganisations-ID skriver eller klistrar du in ditt klientorganisations-ID (som du fick i steg 2).</span><span class="sxs-lookup"><span data-stu-id="6182a-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="6182a-195">I lösenordsrutan skriver eller klistrar du in APISecretKey (som du fick i steg 2) och klickar sedan på Ange konfigurationsinställningar **Inställningar** att visa sidan med konfigurationsinformation.</span><span class="sxs-lookup"><span data-stu-id="6182a-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Logga in med ditt klientorganisations-ID och lösenord och gå till sidan med konfigurationsinformation](../media/FBCimage43.png)

4. <span data-ttu-id="6182a-197">Ange följande konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="6182a-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="6182a-198">**Facebook-program-ID:** Program-ID för Facebook-programmet som du fick i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6182a-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="6182a-199">**Programhemlighet i Facebook:** Apphemligheten för Facebook-programmet som du skaffade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6182a-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="6182a-200">**Facebook Webhooks verifiera token:** Den verifieringstoken som du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6182a-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="6182a-201">**AAD-program-ID:** Program-ID:t för Azure Active Directory program som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="6182a-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="6182a-202">**AAD-programhemlighet:** Värdet för APISecretKey-hemligheten som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="6182a-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="6182a-203">Spara **kopplingsinställningarna** genom att klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="6182a-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6182a-204">Steg 5: Konfigurera en Facebook-anslutning i Microsoft 365 kompatibilitetscenter</span><span class="sxs-lookup"><span data-stu-id="6182a-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="6182a-205">Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka sedan på Datakopplingar i den vänstra **navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="6182a-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6182a-206">På sidan **Datakopplingar** under **Facebook Business-sidor klickar** du på **Visa**.</span><span class="sxs-lookup"><span data-stu-id="6182a-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="6182a-207">På sidan **för Facebook-företagssidor** klickar du på **Lägg till koppling**.</span><span class="sxs-lookup"><span data-stu-id="6182a-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="6182a-208">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="6182a-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="6182a-209">På sidan **Lägg till autentiseringsuppgifter för kopplingsappen** anger du följande information och klickar sedan på **Validera anslutning.**</span><span class="sxs-lookup"><span data-stu-id="6182a-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Ange autentiseringsuppgifter för kopplingsappen](../media/TCimage38.png)

   - <span data-ttu-id="6182a-211">Ange ett **namn** på kopplingen i rutan Namn, till exempel Facebook **Nyheter-sidan.**</span><span class="sxs-lookup"><span data-stu-id="6182a-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="6182a-212">I rutan **Anslutnings-URL** skriver eller klistrar du in Azure-apptjänstens URL. till exempel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="6182a-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="6182a-213">I rutan **Lösenord** skriver eller klistrar du in värdet för APISecretKey som du lade till i steg 2.</span><span class="sxs-lookup"><span data-stu-id="6182a-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="6182a-214">I rutan **Azure-program-ID** skriver eller klistrar du in värdet för det Program (klient)-ID som även kallas AAD-program-ID som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="6182a-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="6182a-215">När anslutningen har verifierats klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6182a-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="6182a-216">På sidan **Auktorisera Microsoft 365 importera data** skriver eller klistrar du in APISecretKey igen och klickar sedan på **Logga in webbapp.**</span><span class="sxs-lookup"><span data-stu-id="6182a-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="6182a-217">På sidan **Konfigurera facebook-kopplingsappen** klickar du på Logga in med **Facebook** och loggar in med inloggningsuppgifterna för kontot för din organisations Facebook Business-sidor.</span><span class="sxs-lookup"><span data-stu-id="6182a-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="6182a-218">Kontrollera att det Facebook-konto som du loggade in på har tilldelats administratörsrollen för din organisations Facebook Business-sidor.</span><span class="sxs-lookup"><span data-stu-id="6182a-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Logga in med Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="6182a-220">En lista med företagssidor som hanteras av det Facebook-konto som du loggade in på visas.</span><span class="sxs-lookup"><span data-stu-id="6182a-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="6182a-221">Markera den sida som du vill arkivera och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6182a-221">Select the page to archive and then click **Next**.</span></span>

   ![Välj den organisationssida som du vill arkivera](../media/FBCimage52.png)

10. <span data-ttu-id="6182a-223">Klicka **på** Fortsätt för att avsluta installationen av anslutningstjänstappen.</span><span class="sxs-lookup"><span data-stu-id="6182a-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="6182a-224">På sidan **Ange filter** kan du använda ett filter för att först importera objekt som är av en viss ålder.</span><span class="sxs-lookup"><span data-stu-id="6182a-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="6182a-225">Välj en ålder och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6182a-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="6182a-226">På sidan **Välj lagringsplats** skriver du e-postadressen till den Microsoft 365 som Facebook-objekten ska importeras till och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6182a-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="6182a-227">Klicka **på Nästa** för att granska kopplingsinställningarna och klicka sedan på **Slutför** för att slutföra kopplingens konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6182a-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="6182a-228">I **efterlevnadscentret** går du till sidan Datakopplingar och klickar på fliken Kopplingar för att se **importprocessens** förlopp.</span><span class="sxs-lookup"><span data-stu-id="6182a-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
