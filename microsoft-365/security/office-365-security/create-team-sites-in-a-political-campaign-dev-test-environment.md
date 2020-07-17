---
title: Skapa gruppwebbplatser – politisk kampanj utv miljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sammanfattning: Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj.'
ms.openlocfilehash: d22ada823877d4c0996be942c379e12929242eaf
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755242"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="41d82-103">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="41d82-103">Create team sites in a political campaign dev/test environment</span></span>

 <span data-ttu-id="41d82-104">**Sammanfattning:** Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj.</span><span class="sxs-lookup"><span data-stu-id="41d82-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
  
<span data-ttu-id="41d82-105">Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö med fyra olika typer av SharePoint Online-gruppwebbplatser för lösningen [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="41d82-105">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="41d82-106">De här webbplatserna beskrivs i detalj i avsnitt 10, **SharePoint och OneDrive för företag**.</span><span class="sxs-lookup"><span data-stu-id="41d82-106">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="41d82-107">Fas 1: Skapa en utvecklings-/testmiljö för din politiska kampanj</span><span class="sxs-lookup"><span data-stu-id="41d82-107">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="41d82-108">Börja med att följa anvisningarna i [Konfigurera grupper och användare till en utvecklings-/testmiljö för en politisk kampanj](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) och skapa prenumerationer, användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="41d82-108">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>
  
## <a name="phase-2-create-labels"></a><span data-ttu-id="41d82-109">Steg 2: Skapa etiketter</span><span class="sxs-lookup"><span data-stu-id="41d82-109">Phase 2: Create labels</span></span>

<span data-ttu-id="41d82-110">I den här fasen skapar du etiketter för dokumentmapparna med olika säkerhetsnivåer för SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="41d82-110">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>
  
1. <span data-ttu-id="41d82-111">Om det behövs loggar du in på administrationscentret med autentiseringsuppgifterna för utvärderingsprenumerationens globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="41d82-111">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="41d82-112">Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="41d82-112">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="41d82-113">På fliken **Microsoft Office Home** klickar du på panelen **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="41d82-113">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="41d82-114">På den nya fliken **Administrationscenter för Microsoft 365** i webbläsaren klickar du på **Administrationscenter > Säkerhet &amp; efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="41d82-114">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="41d82-115">Klicka på **Klassifikationer > Etiketter** på den nya fliken \*\*Start – Säkerhet &amp; \*\*efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="41d82-115">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="41d82-116">I fönstret **Start > Etiketter** klickar du på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="41d82-116">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="41d82-117">I fönstret **Namnge din etikett** skriver du **Internt**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-117">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="41d82-118">I fönstret **Etikettinställningar** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-118">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-119">I fönstret **Granska inställningarna** klickar du på **Skapa den här etiketten** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="41d82-119">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="41d82-120">Upprepa steg 5–8 för följande ytterligare etiketter:</span><span class="sxs-lookup"><span data-stu-id="41d82-120">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="41d82-121">Privat</span><span class="sxs-lookup"><span data-stu-id="41d82-121">Private</span></span>
    
  - <span data-ttu-id="41d82-122">Känslig</span><span class="sxs-lookup"><span data-stu-id="41d82-122">Sensitive</span></span>
    
  - <span data-ttu-id="41d82-123">Strikt konfidentiellt</span><span class="sxs-lookup"><span data-stu-id="41d82-123">Highly Confidential</span></span>
    
10. <span data-ttu-id="41d82-124">I fönstret **Start > Etiketter** klickar du på **Publicera etiketter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-124">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="41d82-125">Klicka på **Välj etiketter att publicera** i fönstret **Välj etiketter att publicera**.</span><span class="sxs-lookup"><span data-stu-id="41d82-125">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="41d82-126">I fönstret **Välj etiketter** klickar du på **Lägg till** och markerar alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="41d82-126">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="41d82-127">Klicka på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="41d82-127">Click **Done**.</span></span>
    
14. <span data-ttu-id="41d82-128">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-128">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="41d82-129">Klicka på **Nästa** i fönstret **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="41d82-129">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="41d82-130">I fönstret **Namnge principen** skriver du **Kampanj** i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-130">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="41d82-131">I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="41d82-131">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="41d82-132">Fas 3: Skapa gruppwebbplatser i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="41d82-132">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="41d82-133">I den här fasen skapar och konfigurerar du SharePoint Online-gruppwebbplatser för din politiska kampanj som motsvarar de fyra typerna av SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="41d82-133">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>
  
### <a name="campaign-wide-team-site"></a><span data-ttu-id="41d82-134">Kampanjens hela gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="41d82-134">Campaign wide team site</span></span>

<span data-ttu-id="41d82-135">Gör så här om du vill skapa en offentlig baslinje för SharePoint Online-gruppwebbplatsen:</span><span class="sxs-lookup"><span data-stu-id="41d82-135">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="41d82-136">Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret ([https://admin.microsoft.com](https://admin.microsoft.com)) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="41d82-136">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="41d82-137">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="41d82-137">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="41d82-138">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-138">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="41d82-139">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-139">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="41d82-140">I **Webbplatsnamn** skriver du **Hela kampanjen**.</span><span class="sxs-lookup"><span data-stu-id="41d82-140">In **Site name**, type **Campaign wide**.</span></span> 
    
6. <span data-ttu-id="41d82-141">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för hela kampanjen**.</span><span class="sxs-lookup"><span data-stu-id="41d82-141">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>
    
7. <span data-ttu-id="41d82-142">I **Sekretessinställningar** väljer du **Offentlig – alla i organisationen har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-142">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-143">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="41d82-143">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="41d82-144">Därefter konfigurerar du dokumentmappen för kampanjens gruppwebbplats med en intern etikett.</span><span class="sxs-lookup"><span data-stu-id="41d82-144">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>
  
1. <span data-ttu-id="41d82-145">På fliken **Hela kampanjen-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="41d82-145">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="41d82-146">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="41d82-146">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="41d82-147">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="41d82-147">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="41d82-148">I **Inställningar-Använd etikett** väljer du **Internt**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-148">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>
    
### <a name="campaign-project-1-team-site"></a><span data-ttu-id="41d82-149">Gruppwebbplats för kampanjens projekt 1</span><span class="sxs-lookup"><span data-stu-id="41d82-149">Campaign project 1 team site</span></span>

<span data-ttu-id="41d82-150">Om du vill skapa en baslinje för en privat SharePoint Online-gruppwebbplats till ett projekt i kampanjen, gör du så här:</span><span class="sxs-lookup"><span data-stu-id="41d82-150">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>
  
1. <span data-ttu-id="41d82-151">Om det behövs kan du använda webbläsaren på din lokala dator och logga in på administrationscentret ([https://admin.microsoft.com](https://admin.microsoft.com)) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="41d82-151">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="41d82-152">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="41d82-152">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="41d82-153">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-153">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="41d82-154">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-154">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="41d82-155">I **Webbplatsnamn** skriver du **Kampanj, projekt 1**.</span><span class="sxs-lookup"><span data-stu-id="41d82-155">In **Site name**, type **Campaign project 1**.</span></span> 
    
6. <span data-ttu-id="41d82-156">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanj, projekt 1**.</span><span class="sxs-lookup"><span data-stu-id="41d82-156">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>
    
7. <span data-ttu-id="41d82-157">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-157">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-158">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="41d82-158">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="41d82-159">Därefter konfigurerar du en privat etikett till dokumentmappen för kampanjens gruppwebbplats för projekt 1.</span><span class="sxs-lookup"><span data-stu-id="41d82-159">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="41d82-160">På fliken **Kampanj, projekt 1-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="41d82-160">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="41d82-161">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="41d82-161">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="41d82-162">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="41d82-162">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="41d82-163">I **Inställningar-Använd etikett** väljer du **Privat**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-163">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="campaign-marketing-team-site"></a><span data-ttu-id="41d82-164">Gruppwebbplats för kampanjmarknadsföring</span><span class="sxs-lookup"><span data-stu-id="41d82-164">Campaign marketing team site</span></span>

<span data-ttu-id="41d82-165">Gör så här om du vill skapa en känslighetsnivå för en isolerad SharePoint Online-gruppwebbplats för kampanjmarknadsföringsresurser:</span><span class="sxs-lookup"><span data-stu-id="41d82-165">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>
  
1. <span data-ttu-id="41d82-166">Använd webbläsaren på din lokala dator och logga in på administrationscentret ([https://admin.microsoft.com](https://admin.microsoft.com)) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="41d82-166">Using a browser on your local computer, sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="41d82-167">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="41d82-167">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="41d82-168">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-168">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="41d82-169">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-169">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="41d82-170">Skriv **Kampanjmarknadsföring** i **Namn på gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-170">In **Team site name**, type **Campaign marketing**.</span></span>
    
6. <span data-ttu-id="41d82-171">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjmarknadsföring (känslig)**.</span><span class="sxs-lookup"><span data-stu-id="41d82-171">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>
    
7.  <span data-ttu-id="41d82-172">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-172">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-173">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="41d82-173">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="41d82-174">Gå till den nya fliken **Kampanjmarknadsföring** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-174">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="41d82-175">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="41d82-176">Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-176">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="41d82-177">I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du kryssrutorna **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp**. Skriv **ITAdmin1@**<your organization name> **.onmicrosoft.com** i **Skicka alla åtkomstbegäranden** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-177">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**<your organization name> **.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="41d82-178">Klicka på **Kampanjmarknadsföring-Medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="41d82-178">Click **Campaign marketing Members** in the list.</span></span>
    
14. <span data-ttu-id="41d82-179">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="41d82-179">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="41d82-180">I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="41d82-180">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="41d82-181">Upprepa steg 14 och 15 för gruppen **Analyspersonal** och användarkontot **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="41d82-181">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>
    
17. <span data-ttu-id="41d82-182">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-182">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="41d82-183">Klicka på **Kampanjmarknadsföring-Ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="41d82-183">Click **Campaign marketing Owners** in the list.</span></span>
    
19. <span data-ttu-id="41d82-184">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="41d82-184">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="41d82-185">I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="41d82-185">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="41d82-186">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-186">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="41d82-187">Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjmarknadsföring-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-187">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="41d82-188">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="41d82-188">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="41d82-189">SharePoint-gruppen **Kampanjmarknadsföring-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som innehåller användarkontona Candidate, ChiefOfStaff och Strategic1), gruppen **Kampanjmarknadsföring** (som innehåller det globala administratörsanvändarkontot), gruppen **Analyspersonal** (som innehåller användarkontot DataScientist1) och användarkontot **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="41d82-189">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>
    
- <span data-ttu-id="41d82-190">SharePoint-gruppen **Kampanjmarknadsföring-Ägare** innehåller bara gruppen **IT-personal** (som bara innehåller användarkontona ITAdmin1 och ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="41d82-190">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="41d82-191">SharePoint-gruppen **Kampanjmarknadsföring-Besökare** innehåller inga grupp- eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="41d82-191">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="41d82-192">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjmarknadsföring-Ägare**).</span><span class="sxs-lookup"><span data-stu-id="41d82-192">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>
    
- <span data-ttu-id="41d82-193">Andra användarkonton saknar åtkomst till webbplatsen eller dess resurser, men kan begära åtkomst till webbplatsen. Ett e-postmeddelande skickas då till postlådan för ITAdmin1-användarkontot.</span><span class="sxs-lookup"><span data-stu-id="41d82-193">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="41d82-194">Därefter konfigurerar du dokumentmappen för kampanjmarknadsföringens gruppwebbplats med etiketten Känslig.</span><span class="sxs-lookup"><span data-stu-id="41d82-194">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="41d82-195">På fliken **Kampanjmarknadsföring-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="41d82-195">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="41d82-196">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="41d82-196">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="41d82-197">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="41d82-197">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="41d82-198">I **Inställningar-Använd etikett** väljer du **Känslig** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-198">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="41d82-199">Därefter konfigurerar du en princip för dataförlustskydd (DLP) som meddelar användarna när de delar ett dokument med etiketten Känslig på en SharePoint Online-gruppwebbplats utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="41d82-199">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization.</span></span> <span data-ttu-id="41d82-200">DLP-principen används för resurser som finns på kampanjmarknadsföringens webbplats.</span><span class="sxs-lookup"><span data-stu-id="41d82-200">This DLP policy will apply to resources in the Campaign marketing site.</span></span>
  
1. <span data-ttu-id="41d82-201">På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Säkerhet &amp;efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="41d82-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="41d82-202">Klicka på **Dataförlustskydd > Princip** på den nya fliken **Säkerhet &amp; efterlevnad** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="41d82-203">I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="41d82-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="41d82-204">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="41d82-205">I fönstret **Namnge principen** skriver du **Etiketten Känslig, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-205">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="41d82-206">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="41d82-207">Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-208">I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="41d82-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="41d82-209">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="41d82-210">I fönstret **Etikett** klickar du på **+ Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="41d82-210">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="41d82-211">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="41d82-212">I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="41d82-213">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="41d82-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="41d82-214">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="41d82-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="41d82-215">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="41d82-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="41d82-216">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="41d82-216">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="41d82-217">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="41d82-217">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="41d82-218">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="41d82-218">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="41d82-219">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-219">Click **OK**.</span></span>
    
17. <span data-ttu-id="41d82-220">I fönstret **Vad vill du göra om vi identifierar känslig information?** avmarkerar du kryssrutan **Blockera andra från att dela och begränsa åtkomsten till delat innehåll**, och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-220">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="41d82-221">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-221">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="41d82-222">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="41d82-222">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
### <a name="campaign-strategy-team-site"></a><span data-ttu-id="41d82-223">Gruppwebbplats för kampanjstrategi</span><span class="sxs-lookup"><span data-stu-id="41d82-223">Campaign strategy team site</span></span>

<span data-ttu-id="41d82-224">Gör så här om du vill skapa en isolerad SharePoint Online-gruppwebbplats med hög sekretessnivå för kampanjstrategiresurser:</span><span class="sxs-lookup"><span data-stu-id="41d82-224">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>
  
1. <span data-ttu-id="41d82-225">Om det behövs kan du använda webbläsaren på din lokala dator och logga in på administrationscentret ([https://admin.microsoft.com](https://admin.microsoft.com)) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="41d82-225">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="41d82-226">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="41d82-226">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="41d82-227">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-227">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="41d82-228">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-228">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="41d82-229">Skriv **Kampanjstrategi** i **Namn på gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="41d82-229">In **Team site name**, type **Campaign strategy**.</span></span>
    
6. <span data-ttu-id="41d82-230">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjstrategi (strikt konfidentiellt)**.</span><span class="sxs-lookup"><span data-stu-id="41d82-230">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="41d82-231">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-231">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-232">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="41d82-232">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="41d82-233">Gå till den nya fliken **Kampanjstrategi** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-233">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="41d82-234">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-234">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="41d82-235">Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-235">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="41d82-236">I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp** (så att alla tre kryssrutorna är avmarkerade). Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-236">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="41d82-237">Klicka på **Kampanjstrategi-Medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="41d82-237">Click **Campaign strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="41d82-238">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="41d82-238">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="41d82-239">I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="41d82-239">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="41d82-240">Klicka på **Kampanjstrategi-Ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="41d82-240">Click **Campaign strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="41d82-241">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="41d82-241">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="41d82-242">I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="41d82-242">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="41d82-243">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-243">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="41d82-244">Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjstrategi-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-244">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="41d82-245">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="41d82-245">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="41d82-246">SharePoint-gruppen **Kampanjstrategi-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som endast innehåller användarkontona Candidate, ChiefOfStaff och Strategic1) och gruppen **Kampanjstrategi** (som bara innehåller det globala administratörsanvändarkontot).</span><span class="sxs-lookup"><span data-stu-id="41d82-246">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="41d82-247">SharePoint-gruppen **Kampanjstrategi-Ägare** innehåller bara gruppen **IT-personal** (som endast innehåller användarkontona ITAdmin1 och ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="41d82-247">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="41d82-248">SharePoint-gruppen **Kampanjstrategi-Besökare** innehåller inga grupp- eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="41d82-248">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="41d82-249">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjstrategi-Ägare**).</span><span class="sxs-lookup"><span data-stu-id="41d82-249">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>
    
- <span data-ttu-id="41d82-250">Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="41d82-250">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="41d82-251">Ytterligare behörigheter för webbplatsen måste utföras av en global administratör eller en medlem i gruppen **Kampanjstrategi-Ägare**.</span><span class="sxs-lookup"><span data-stu-id="41d82-251">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>
    
<span data-ttu-id="41d82-252">Därefter konfigurerar du dokumentmappen för kampanjstrategins gruppwebbplats med etiketten Strikt konfidentiellt.</span><span class="sxs-lookup"><span data-stu-id="41d82-252">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="41d82-253">På fliken **Kampanjstrategi-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="41d82-253">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="41d82-254">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="41d82-254">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="41d82-255">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="41d82-255">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="41d82-256">I **Inställningar-Använd etikett** väljer du **Strikt konfidentiellt** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-256">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="41d82-257">Därefter konfigurerar du en DLP-princip som blockerar användare när de delar ett dokument med etiketten Strikt konfidentiellt på en SharePoint Online-gruppwebbplats som finns utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="41d82-257">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization.</span></span> <span data-ttu-id="41d82-258">Den här DLP-principen används för resurser på kampanjstrategins webbplats.</span><span class="sxs-lookup"><span data-stu-id="41d82-258">This DLP policy will apply to resources in the Campaign strategy site.</span></span>
  
1. <span data-ttu-id="41d82-259">Om det behövs kan du använda webbläsaren på din lokala dator och logga in på administrationscentret för ([https://admin.microsoft.com](https://admin.microsoft.com)) med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="41d82-259">If needed, use a browser on your local computer and sign in to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="41d82-260">På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Säkerhet &amp;efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="41d82-260">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="41d82-261">Klicka på **Dataförlustskydd > Princip** på den nya fliken **Säkerhet &amp; efterlevnad** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-261">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="41d82-262">I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="41d82-262">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="41d82-263">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-263">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="41d82-264">I fönstret **Namnge principen** skriver du **Etiketten Strikt konfidentiellt, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-264">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="41d82-265">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-265">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="41d82-266">Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-266">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
9. <span data-ttu-id="41d82-267">I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="41d82-267">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
10. <span data-ttu-id="41d82-268">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-268">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
11. <span data-ttu-id="41d82-269">I rutan **Etiketter** klickar du på **+ Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="41d82-269">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
12. <span data-ttu-id="41d82-270">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="41d82-270">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
13. <span data-ttu-id="41d82-271">I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-271">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="41d82-272">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="41d82-272">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
15. <span data-ttu-id="41d82-273">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="41d82-273">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
16. <span data-ttu-id="41d82-274">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="41d82-274">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="41d82-275">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="41d82-275">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="41d82-276">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="41d82-276">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="41d82-277">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="41d82-277">Send the password in a separate email or other means of communication.</span></span>
    
17. <span data-ttu-id="41d82-278">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-278">Click **OK**.</span></span>
    
18. <span data-ttu-id="41d82-279">I fönstret **Vad vill du göra om vi identifierar känslig information?** väljer du **Kräv en affärsrelaterad motivering för att åsidosätta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-279">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="41d82-280">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="41d82-280">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
20. <span data-ttu-id="41d82-281">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="41d82-281">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="41d82-282">Använd instruktionerna i [Aktivera Azure RMS med administrationscentret för Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="41d82-282">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="41d82-283">Konfigurera sedan Azure Information Protection med en ny begränsad princip och en underetikett för skydd och behörigheter med följande steg:</span><span class="sxs-lookup"><span data-stu-id="41d82-283">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="41d82-284">Logga in på administrationscentret med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="41d82-284">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="41d82-285">Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="41d82-285">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="41d82-286">Gå till Azure-portalen ([https://portal.azure.com](https://portal.azure.com)) på en separat flik i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="41d82-286">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
4. <span data-ttu-id="41d82-287">I sökfönstret skriver du **information** och klickar sedan på **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="41d82-287">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="41d82-288">Klicka på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-288">Click **Labels**.</span></span>
    
6. <span data-ttu-id="41d82-289">Högerklicka på etiketten **Strikt konfidentiellt** och klicka sedan på **Lägg till en underetikett**.</span><span class="sxs-lookup"><span data-stu-id="41d82-289">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="41d82-290">Skriv **CampaignStrategy** i **Namn** och **Etikett för dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="41d82-290">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>
    
8. <span data-ttu-id="41d82-291">I **Ange behörigheter för dokument och e-postmeddelanden som innehåller den här etiketten** klickar du på **Skydda**.</span><span class="sxs-lookup"><span data-stu-id="41d82-291">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="41d82-292">I avsnittet **Säkerhet** klickar du på **Azure (molnnyckel)**.</span><span class="sxs-lookup"><span data-stu-id="41d82-292">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="41d82-293">På bladet **Säkerhet** klickar du på **+ Lägg till behörigheter** under **Skyddsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="41d82-293">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="41d82-294">På bladet **Lägg till behörigheter** klickar du på **+ Bläddra i katalog** under **Ange användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="41d82-294">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="41d82-295">I fönstret **AAD-användare och grupper** väljer du **Seniora och strategisk personal**. Klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="41d82-295">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="41d82-296">Under **Välj behörigheter från förinställt eller ange anpassad** klickar du på **Anpassad** och sedan i kryssrutorna **Visa rättigheter**, **Redigera innehåll**, **Spara**, **Svara** och **Svara alla**.</span><span class="sxs-lookup"><span data-stu-id="41d82-296">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="41d82-297">Klicka på **OK** två gånger.</span><span class="sxs-lookup"><span data-stu-id="41d82-297">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="41d82-298">På bladet **Underetikett** klickar du på **Spara** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-298">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="41d82-299">Klicka på **Principer > + Lägg till en ny princip** på bladet **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="41d82-299">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="41d82-300">Skriv **CampaignStrategy** i **Namn** och **Dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="41d82-300">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="41d82-301">Klicka på **Välj vilka användare eller grupper som får den här principen > Användare/grupper** och välj sedan **Seniora och strategisk personal**.</span><span class="sxs-lookup"><span data-stu-id="41d82-301">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>
    
19. <span data-ttu-id="41d82-302">Klicka på **Välj > OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-302">Click **Select > OK**.</span></span>

20. <span data-ttu-id="41d82-303">Klicka på **Lägg till eller ta bort etiketter**.</span><span class="sxs-lookup"><span data-stu-id="41d82-303">Click **Add or remove labels**.</span></span> <span data-ttu-id="41d82-304">I fönstret **Princip: Lägg till eller ta bort etiketter** klickar du på **CampaignStrategy** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-304">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>   

21. <span data-ttu-id="41d82-305">Klicka på **Spara** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="41d82-305">Click **Save**, and then click **OK**.</span></span>
  
<span data-ttu-id="41d82-306">Du är nu redo att börja skapa dokument på dessa fyra webbplatser och testa åtkomsten till dem med olika användarkonton.</span><span class="sxs-lookup"><span data-stu-id="41d82-306">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span> 
  
<span data-ttu-id="41d82-307">Om du vill skydda ett dokument med Azure Information Protection och den här nya etiketten, måste du [installera Azure Information Protection-klienten](https://docs.microsoft.com/information-protection/rms-client/install-client-app) på en testdator, installera Office från administrationscentret och sedan logga in med ett konto i gruppen **Seniora och strategisk personal** i utvärderingsprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="41d82-307">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41d82-308">Se även</span><span class="sxs-lookup"><span data-stu-id="41d82-308">See Also</span></span>

[<span data-ttu-id="41d82-309">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer</span><span class="sxs-lookup"><span data-stu-id="41d82-309">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="41d82-310">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="41d82-310">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="41d82-311">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="41d82-311">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="41d82-312">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="41d82-312">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




