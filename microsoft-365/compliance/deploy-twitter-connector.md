---
title: Distribuera en anslutare för att arkivera Twitter-data
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
description: Administratörer kan konfigurera en intern anslutning för att importera och arkivera Twitter-data för att Microsoft 365. När dessa data har importerats till Microsoft 365 kan du använda efterlevnadsfunktioner som bevarande av juridiska regler, innehållssökning och bevarandeprinciper för att hantera styrning av organisationens Twitter-data.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "52161637"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="aedf4-104">Distribuera en anslutare för att arkivera Twitter-data</span><span class="sxs-lookup"><span data-stu-id="aedf4-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="aedf4-105">Den här artikeln innehåller stegvisa instruktioner för att distribuera en anslutare som använder tjänsten Office 365 för att importera data från organisationens Twitter-konto till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aedf4-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="aedf4-106">En översikt över den här processen och en lista över förutsättningar för att distribuera en Twitter-anslutning finns i Konfigurera en anslutning för att arkivera [Twitter-data. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="aedf4-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="aedf4-107">Steg 1: Skapa en app i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="aedf4-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="aedf4-108">Gå till <https://portal.azure.com> och logga in med autentiseringsuppgifterna för ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="aedf4-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Logga in på Azure](../media/TCimage01.png)

2. <span data-ttu-id="aedf4-110">I det vänstra navigeringsfönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Gå till Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="aedf4-112">I det vänstra navigeringsfönstret klickar du **på Appregistreringar (förhandsversion)** och sedan på **Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Skapa en ny appregistrering](../media/TCimage03.png)

4. <span data-ttu-id="aedf4-114">Registrera programmet.</span><span class="sxs-lookup"><span data-stu-id="aedf4-114">Register the application.</span></span> <span data-ttu-id="aedf4-115">Under **Omdirigera URI (valfritt)** väljer du **Webb** i listrutan programtyp och skriver sedan i rutan `https://portal.azure.com` för URI:n.</span><span class="sxs-lookup"><span data-stu-id="aedf4-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="aedf4-116">Ange https://portal.azure.com omdirigerings-URI</span><span class="sxs-lookup"><span data-stu-id="aedf4-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="aedf4-117">Kopiera **program-ID(klient)ID** **och katalog-ID (klientorganisation)** och spara dem i en textfil eller på en annan säker plats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="aedf4-118">Du använder de här ID:erna i senare steg.</span><span class="sxs-lookup"><span data-stu-id="aedf4-118">You use these IDs in later steps.</span></span>

    ![Kopiera och spara program-ID och katalog-ID](../media/TCimage05.png)

6. <span data-ttu-id="aedf4-120">Gå till **Certifikat & för den nya appen och** under Klienthemligheter **klickar** du på **Ny klienthemlighet.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Skapa en ny klienthemlighet](../media/TCimage06.png)

7. <span data-ttu-id="aedf4-122">Skapa en ny hemlig.</span><span class="sxs-lookup"><span data-stu-id="aedf4-122">Create a new secret.</span></span> <span data-ttu-id="aedf4-123">Skriv hemligheten i beskrivningsrutan och välj sedan en utgångsperiod.</span><span class="sxs-lookup"><span data-stu-id="aedf4-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Skriv hemligheten och välj utgångsperiod](../media/TCimage08.png)

8. <span data-ttu-id="aedf4-125">Kopiera värdet för hemligheten och spara den i en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="aedf4-126">Det här är AAD-programhemligheten som du använder i senare steg.</span><span class="sxs-lookup"><span data-stu-id="aedf4-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopiera och spara hemligheten](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="aedf4-128">Steg 2: Distribuera anslutarwebbtjänsten från GitHub till ditt Azure-konto</span><span class="sxs-lookup"><span data-stu-id="aedf4-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="aedf4-129">Gå till [den GitHub webbplatsen](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) och klicka på Distribuera till **Azure.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Gå till Azure-startsidan](../media/FBCimage11.png)

2. <span data-ttu-id="aedf4-131">När du har **klickat på Distribuera** till Azure omdirigeras du till en Azure-portal med en anpassad mallsida.</span><span class="sxs-lookup"><span data-stu-id="aedf4-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="aedf4-132">Fyll i Grunderna **och Inställningar** **och** klicka sedan på **Köp**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Klicka på Skapa en resurs och skriv lagringskonto](../media/FBCimage12.png)

    - <span data-ttu-id="aedf4-134">**Prenumeration:** Välj den Azure-prenumeration du vill distribuera webbtjänsten för Twitter-anslutning till.</span><span class="sxs-lookup"><span data-stu-id="aedf4-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="aedf4-135">**Resursgrupp:** Välj eller skapa en ny resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="aedf4-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="aedf4-136">En resursgrupp är en behållare som innehåller relaterade resurser för en Azure-lösning.</span><span class="sxs-lookup"><span data-stu-id="aedf4-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="aedf4-137">**Plats:** Välj en plats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="aedf4-138">**Web App-namn:** Ange ett unikt namn för webbappen för anslutning.</span><span class="sxs-lookup"><span data-stu-id="aedf4-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="aedf4-139">Namnet måste vara mellan 3 och 18 tecken långt.</span><span class="sxs-lookup"><span data-stu-id="aedf4-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="aedf4-140">Det här namnet används för att skapa URL-adressen för Azure-apptjänsten. Om du till exempel anger webbappens namn **för twitterconnector** kommer Azure-apptjänstens URL att **twitterconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="aedf4-141">**tenantId:** Klientorganisations-ID:t för Microsoft 365 organisationen som du kopierade när du skapade Facebook-anslutningsappen i Azure Active Directory i steg 1.</span><span class="sxs-lookup"><span data-stu-id="aedf4-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="aedf4-142">**APISecretKey:** Du kan ange vilket värde som helst som hemlig.</span><span class="sxs-lookup"><span data-stu-id="aedf4-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="aedf4-143">Det här används för att komma åt webbappen för anslutning i steg 5.</span><span class="sxs-lookup"><span data-stu-id="aedf4-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="aedf4-144">När distributionen är lyckad ser sidan ut ungefär som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="aedf4-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Klicka Storage konto och klicka sedan på Storage konto](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="aedf4-146">Steg 3: Skapa Twitter-appen</span><span class="sxs-lookup"><span data-stu-id="aedf4-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="aedf4-147">Gå till https://developer.twitter.com , logga in med inloggningsuppgifterna för utvecklarkontot för din organisation och klicka sedan på **Appar.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Gå till https://developer.twitter.com och logga in](../media/TCimage25-5.png)
2. <span data-ttu-id="aedf4-149">Klicka **på Skapa ett program.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-149">Click **Create an app**.</span></span>
   
   ![Gå till sidan Program för att skapa ett program](../media/TCimage26.png)

3. <span data-ttu-id="aedf4-151">Lägg **till information** om programmet under Programinformation.</span><span class="sxs-lookup"><span data-stu-id="aedf4-151">Under **App details**, add information about the application.</span></span>

   ![Ange information om programmet](../media/TCimage27.png)

4. <span data-ttu-id="aedf4-153">På instrumentpanelen för Twitter-utvecklare väljer du appen du just skapade och klickar sedan på **Information**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![Kopiera och spara app-ID:t](../media/TCimage28.png)

5. <span data-ttu-id="aedf4-155">Under **Konsument-API-nycklar** på  fliken Nycklar och token kopierar du både API-nyckeln och API-hemliga nyckeln och sparar dem till en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="aedf4-156">Klicka sedan på **Skapa** för att generera en åtkomsttoken och åtkomsttokenhemlighet och kopiera dessa till en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![Kopiera och spara till API-hemlig nyckel](../media/TCimage29.png)

   <span data-ttu-id="aedf4-158">Klicka sedan **på Skapa** för att generera en åtkomsttoken och en åtkomsttokenhemlighet, och kopiera dessa till en textfil eller annan lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="aedf4-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="aedf4-159">Klicka på **fliken** Behörigheter och konfigurera behörigheterna enligt följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="aedf4-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Konfigurera behörigheter](../media/TCimage30.png)

7. <span data-ttu-id="aedf4-161">När du har sparat behörighetsinställningarna klickar du **på fliken Appinformation** och sedan på **Redigera > Redigera information**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Redigera programinformationen](../media/TCimage31.png)

8. <span data-ttu-id="aedf4-163">Gör följande:</span><span class="sxs-lookup"><span data-stu-id="aedf4-163">Do the following tasks:</span></span>

   - <span data-ttu-id="aedf4-164">Markera kryssrutan om du vill tillåta att anslutningsappen loggar in på Twitter.</span><span class="sxs-lookup"><span data-stu-id="aedf4-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="aedf4-165">Lägg till OAuth-omdirigerings-Uri med följande format: **\<connectorserviceuri> /Views/TwitterOAuth**, där värdet för *connectorserviceuri* är Azure-apptjänst-URL:en för organisationen, till exempel https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="aedf4-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Tillåt att anslutningsappen loggar in på Twitter och lägger till OAuth-omdirigerings-Uri](../media/TCimage32.png)

<span data-ttu-id="aedf4-167">Utvecklarappen för Twitter är nu redo att använda.</span><span class="sxs-lookup"><span data-stu-id="aedf4-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="aedf4-168">Steg 4: Konfigurera webbprogrammet för anslutning</span><span class="sxs-lookup"><span data-stu-id="aedf4-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="aedf4-169">Gå till https:// \<AzureAppResourceName> .azurewebsites.net (där **AzureAppResourceName** är namnet på din Azure-appresurs som du döpte i steg 4).</span><span class="sxs-lookup"><span data-stu-id="aedf4-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="aedf4-170">Om namnet till exempel är **twitterconnector går** du till https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="aedf4-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="aedf4-171">Startsidan för appen ser ut som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="aedf4-171">The home page of the app looks like the following screenshot:</span></span>

   ![Gå till sidan Azure-appresurs](../media/FBCimage41.png)

2. <span data-ttu-id="aedf4-173">Klicka **på Konfigurera** för att visa en inloggningssida.</span><span class="sxs-lookup"><span data-stu-id="aedf4-173">Click **Configure** to display a sign in page.</span></span>

   ![Klicka på Konfigurera för att visa inloggningssidan](../media/FBCimage42.png)

3. <span data-ttu-id="aedf4-175">I rutan Klientorganisations-ID skriver eller klistrar du in ditt klientorganisations-ID (som du fick i steg 2).</span><span class="sxs-lookup"><span data-stu-id="aedf4-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="aedf4-176">I lösenordsrutan skriver eller klistrar du in APISecretKey (som du fick i steg 2) och klickar sedan på Ange konfigurationsinställningar **Inställningar** att visa sidan med konfigurationsinformation.</span><span class="sxs-lookup"><span data-stu-id="aedf4-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Logga in med klientorganisations-ID och API-hemlig nyckel](../media/TCimage35.png)

4. <span data-ttu-id="aedf4-178">Ange följande konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="aedf4-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="aedf4-179">**Api-nyckel för Twitter:** API-nyckeln för Twitter-programmet som du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="aedf4-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aedf4-180">**Twitter Api-hemlig nyckel:** API-hemlig nyckel för Twitter-programmet som du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="aedf4-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aedf4-181">**Twitter-åtkomsttoken:** Åtkomsttoken som du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="aedf4-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aedf4-182">**Twitter Access Token Secret:** Den åtkomsttokens hemligt som du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="aedf4-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aedf4-183">**AAD-program-ID:** Program-ID för Azure Active Directory som du skapade i steg 1</span><span class="sxs-lookup"><span data-stu-id="aedf4-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="aedf4-184">**AAD-programhemlighet:** Värdet för APISecretKey-hemligheten som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="aedf4-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="aedf4-185">Spara **kopplingsinställningarna** genom att klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aedf4-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="aedf4-186">Steg 5: Konfigurera en Twitter-anslutning i Microsoft 365 för efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="aedf4-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="aedf4-187">Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och klicka sedan på Datakopplingar i den vänstra **navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="aedf4-188">På sidan **Datakopplingar** under **Twitter klickar** du på **Visa**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="aedf4-189">Klicka på **Lägg** till koppling på **Twitter-sidan.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="aedf4-190">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="aedf4-191">På sidan **Lägg till autentiseringsuppgifter för kopplingsappen** anger du följande information och klickar sedan på **Validera anslutning.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Ange autentiseringsuppgifter för kopplingsappen](../media/TCimage38.png)

    - <span data-ttu-id="aedf4-193">Ange ett **namn** på kopplingen i rutan Namn, till exempel **Twitter-hjälphandtaget**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="aedf4-194">I rutan **Kopplings-URL** skriver eller klistrar du in Azure-apptjänst-URL:en. till exempel `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="aedf4-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="aedf4-195">I rutan **Lösenord** skriver eller klistrar du in värdet för APISecretKey som du skapade i steg 2.</span><span class="sxs-lookup"><span data-stu-id="aedf4-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="aedf4-196">I rutan **Azure-app-ID** skriver eller klistrar du in värdet för Azure Application App-ID (kallas även *klient-ID)* som du fick i steg 1.</span><span class="sxs-lookup"><span data-stu-id="aedf4-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="aedf4-197">När anslutningen har verifierats klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="aedf4-198">På sidan **Auktorisera Microsoft 365 importera data** skriver eller klistrar du in APISecretKey igen och klickar sedan på **Logga in webbapp.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="aedf4-199">Klicka **på Logga in med Twitter.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="aedf4-200">På inloggningssidan för Twitter loggar du in med inloggningsuppgifterna för din organisations Twitter-konto.</span><span class="sxs-lookup"><span data-stu-id="aedf4-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Logga in på Twitter-konto](../media/TCimage42.png)

   <span data-ttu-id="aedf4-202">När du har loggat in visas följande meddelande på Twitter-sidan: "Twitter Connector Job Successfully set up".</span><span class="sxs-lookup"><span data-stu-id="aedf4-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="aedf4-203">Klicka **på Fortsätt** för att slutföra kon settingen av Twitter-anslutningen.</span><span class="sxs-lookup"><span data-stu-id="aedf4-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="aedf4-204">På sidan **Ange filter** kan du använda ett filter för att först importera objekt som är av en viss ålder.</span><span class="sxs-lookup"><span data-stu-id="aedf4-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="aedf4-205">Välj en ålder och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="aedf4-206">På sidan **Välj lagringsplats** skriver du e-postadressen till den Microsoft 365 postlådan som Twitter-objekten ska importeras till och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="aedf4-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="aedf4-207">Klicka **på Nästa** för att granska kopplingsinställningarna och klicka sedan på **Slutför** för att slutföra kopplingens konfiguration.</span><span class="sxs-lookup"><span data-stu-id="aedf4-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="aedf4-208">I **efterlevnadscentret** går du till sidan Datakopplingar och klickar på fliken Kopplingar för att se **importprocessens** förlopp.</span><span class="sxs-lookup"><span data-stu-id="aedf4-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
