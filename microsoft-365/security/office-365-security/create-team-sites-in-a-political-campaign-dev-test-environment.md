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
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sammanfattning: Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80c975cd181f326fc2766c6ebfbd0d7f8a5164f2
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108157"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="362a1-103">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="362a1-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="362a1-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="362a1-104">**Applies to**</span></span>

- [<span data-ttu-id="362a1-105">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="362a1-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="362a1-106">**Sammanfattning:** Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj.</span><span class="sxs-lookup"><span data-stu-id="362a1-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="362a1-107">Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö med fyra olika typer av SharePoint Online-gruppwebbplatser för lösningen [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="362a1-107">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span> <span data-ttu-id="362a1-108">De här webbplatserna beskrivs i detalj i avsnitt 10, **SharePoint och OneDrive för företag**.</span><span class="sxs-lookup"><span data-stu-id="362a1-108">These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="362a1-109">Fas 1: Skapa en utvecklings-/testmiljö för din politiska kampanj</span><span class="sxs-lookup"><span data-stu-id="362a1-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="362a1-110">Börja med att följa anvisningarna i [Konfigurera grupper och användare till en utvecklings-/testmiljö för en politisk kampanj](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) och skapa prenumerationer, användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="362a1-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="362a1-111">Steg 2: Skapa etiketter</span><span class="sxs-lookup"><span data-stu-id="362a1-111">Phase 2: Create labels</span></span>

<span data-ttu-id="362a1-112">I den här fasen skapar du etiketter för dokumentmapparna med olika säkerhetsnivåer för SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="362a1-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="362a1-113">Om det behövs loggar du in på administrationscentret för Microsoft 365 (<https://admin.microsoft.com>) med autentiseringsuppgifterna för det globala administratörskontot för din utvärderingsprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="362a1-113">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="362a1-114">Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="362a1-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="362a1-115">Gå till sidan **Start**, där du börjar, och klicka på **Visa alla**.</span><span class="sxs-lookup"><span data-stu-id="362a1-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="362a1-116">I avsnittet **Administrationscenter** som visas klickar du på **Efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="362a1-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="362a1-117">På **startsidan** i Microsoft 365 Efterlevnadscenter går du till avsnittet **Lösningar** \> **Informationsskydd**.</span><span class="sxs-lookup"><span data-stu-id="362a1-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="362a1-118">Om du vill gå direkt till sidan **Informationsskydd** använder du <https://compliance.microsoft.com//informationprotection>.</span><span class="sxs-lookup"><span data-stu-id="362a1-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="362a1-119">På sidan **Informationsskydd** kontrollerar du att taggen **Etikett** är vald och klickar sedan på ![Skapa en etikettikon](../../media/m365-cc-sc-create-icon.png) **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="362a1-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="362a1-120">Guiden **Ny känslighetsetikett** öppnas.</span><span class="sxs-lookup"><span data-stu-id="362a1-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="362a1-121">Ange följande värden i steget **Namn och beskrivning**:</span><span class="sxs-lookup"><span data-stu-id="362a1-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="362a1-122">**Namn**: Skriv **Intern**.</span><span class="sxs-lookup"><span data-stu-id="362a1-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="362a1-123">**Visningsnamn**</span><span class="sxs-lookup"><span data-stu-id="362a1-123">**Display name**</span></span>
   - <span data-ttu-id="362a1-124">**Beskrivning för användare**</span><span class="sxs-lookup"><span data-stu-id="362a1-124">**Description for users**</span></span>

   <span data-ttu-id="362a1-125">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="362a1-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="362a1-126">I fönstret **Etikettinställningar** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="362a1-127">I fönstret **Granska inställningarna** klickar du på **Skapa den här etiketten** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="362a1-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="362a1-128">Upprepa steg 5–8 för följande ytterligare etiketter:</span><span class="sxs-lookup"><span data-stu-id="362a1-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="362a1-129">Privat</span><span class="sxs-lookup"><span data-stu-id="362a1-129">Private</span></span>
   - <span data-ttu-id="362a1-130">Känslig</span><span class="sxs-lookup"><span data-stu-id="362a1-130">Sensitive</span></span>
   - <span data-ttu-id="362a1-131">Strikt konfidentiellt</span><span class="sxs-lookup"><span data-stu-id="362a1-131">Highly Confidential</span></span>

9. <span data-ttu-id="362a1-132">I fönstret **Start > Etiketter** klickar du på **Publicera etiketter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="362a1-133">Klicka på **Välj etiketter att publicera** i fönstret **Välj etiketter att publicera**.</span><span class="sxs-lookup"><span data-stu-id="362a1-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="362a1-134">I fönstret **Välj etiketter** klickar du på **Lägg till** och markerar alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="362a1-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="362a1-135">Klicka på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="362a1-135">Click **Done**.</span></span>

13. <span data-ttu-id="362a1-136">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="362a1-137">Klicka på **Nästa** i fönstret **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="362a1-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="362a1-138">I fönstret **Namnge principen** skriver du **Kampanj** i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="362a1-139">I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="362a1-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="362a1-140">Fas 3: Skapa gruppwebbplatser i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="362a1-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="362a1-141">I den här fasen skapar och konfigurerar du SharePoint Online-gruppwebbplatser för din politiska kampanj som motsvarar de fyra typerna av SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="362a1-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="362a1-142">Kampanjens hela gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="362a1-142">Campaign wide team site</span></span>

<span data-ttu-id="362a1-143">Gör så här om du vill skapa en offentlig baslinje för SharePoint Online-gruppwebbplatsen:</span><span class="sxs-lookup"><span data-stu-id="362a1-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="362a1-144">Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="362a1-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="362a1-145">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="362a1-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="362a1-146">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="362a1-147">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="362a1-148">I **Webbplatsnamn** skriver du **Hela kampanjen**.</span><span class="sxs-lookup"><span data-stu-id="362a1-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="362a1-149">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för hela kampanjen**.</span><span class="sxs-lookup"><span data-stu-id="362a1-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="362a1-150">I **Sekretessinställningar** väljer du **Offentlig – alla i organisationen har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-151">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="362a1-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="362a1-152">Därefter konfigurerar du dokumentmappen för kampanjens gruppwebbplats med en intern etikett.</span><span class="sxs-lookup"><span data-stu-id="362a1-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="362a1-153">På fliken **Hela kampanjen-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="362a1-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="362a1-154">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="362a1-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="362a1-155">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="362a1-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="362a1-156">I **Inställningar-Använd etikett** väljer du **Internt**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="362a1-157">Gruppwebbplats för kampanjens projekt 1</span><span class="sxs-lookup"><span data-stu-id="362a1-157">Campaign project 1 team site</span></span>

<span data-ttu-id="362a1-158">Om du vill skapa en baslinje för en privat SharePoint Online-gruppwebbplats till ett projekt i kampanjen, gör du så här:</span><span class="sxs-lookup"><span data-stu-id="362a1-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="362a1-159">Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="362a1-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="362a1-160">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="362a1-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="362a1-161">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="362a1-162">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="362a1-163">I **Webbplatsnamn** skriver du **Kampanj, projekt 1**.</span><span class="sxs-lookup"><span data-stu-id="362a1-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="362a1-164">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanj, projekt 1**.</span><span class="sxs-lookup"><span data-stu-id="362a1-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="362a1-165">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-166">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="362a1-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="362a1-167">Därefter konfigurerar du en privat etikett till dokumentmappen för kampanjens gruppwebbplats för projekt 1.</span><span class="sxs-lookup"><span data-stu-id="362a1-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="362a1-168">På fliken **Kampanj, projekt 1-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="362a1-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="362a1-169">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="362a1-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="362a1-170">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="362a1-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="362a1-171">I **Inställningar-Använd etikett** väljer du **Privat**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="362a1-172">Gruppwebbplats för kampanjmarknadsföring</span><span class="sxs-lookup"><span data-stu-id="362a1-172">Campaign marketing team site</span></span>

<span data-ttu-id="362a1-173">Gör så här om du vill skapa en känslighetsnivå för en isolerad SharePoint Online-gruppwebbplats för kampanjmarknadsföringsresurser:</span><span class="sxs-lookup"><span data-stu-id="362a1-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="362a1-174">Använd webbläsaren på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="362a1-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="362a1-175">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="362a1-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="362a1-176">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="362a1-177">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="362a1-178">Skriv **Kampanjmarknadsföring** i **Namn på gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="362a1-179">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjmarknadsföring (känslig)**.</span><span class="sxs-lookup"><span data-stu-id="362a1-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="362a1-180">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-181">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="362a1-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="362a1-182">Gå till den nya fliken **Kampanjmarknadsföring** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="362a1-183">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="362a1-184">Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="362a1-185">I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du kryssrutorna **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp**. Skriv **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** i **Skicka alla åtkomstbegäranden** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="362a1-186">Klicka på **Kampanjmarknadsföring-Medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="362a1-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="362a1-187">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="362a1-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="362a1-188">I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="362a1-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="362a1-189">Upprepa steg 14 och 15 för gruppen **Analyspersonal** och användarkontot **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="362a1-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="362a1-190">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="362a1-191">Klicka på **Kampanjmarknadsföring-Ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="362a1-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="362a1-192">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="362a1-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="362a1-193">I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="362a1-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="362a1-194">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="362a1-195">Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjmarknadsföring-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="362a1-196">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="362a1-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="362a1-197">SharePoint-gruppen **Kampanjmarknadsföring-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som innehåller användarkontona Candidate, ChiefOfStaff och Strategic1), gruppen **Kampanjmarknadsföring** (som innehåller det globala administratörsanvändarkontot), gruppen **Analyspersonal** (som innehåller användarkontot DataScientist1) och användarkontot **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="362a1-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="362a1-198">SharePoint-gruppen **Kampanjmarknadsföring-Ägare** innehåller bara gruppen **IT-personal** (som bara innehåller användarkontona ITAdmin1 och ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="362a1-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="362a1-199">SharePoint-gruppen **Kampanjmarknadsföring-Besökare** innehåller inga grupp- eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="362a1-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="362a1-200">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjmarknadsföring-Ägare**).</span><span class="sxs-lookup"><span data-stu-id="362a1-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="362a1-201">Andra användarkonton saknar åtkomst till webbplatsen eller dess resurser, men kan begära åtkomst till webbplatsen. Ett e-postmeddelande skickas då till postlådan för ITAdmin1-användarkontot.</span><span class="sxs-lookup"><span data-stu-id="362a1-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="362a1-202">Därefter konfigurerar du dokumentmappen för kampanjmarknadsföringens gruppwebbplats med etiketten Känslig.</span><span class="sxs-lookup"><span data-stu-id="362a1-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="362a1-203">På fliken **Kampanjmarknadsföring-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="362a1-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="362a1-204">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="362a1-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="362a1-205">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="362a1-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="362a1-206">I **Inställningar-Använd etikett** väljer du **Känslig** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="362a1-p106">Därefter konfigurerar du en princip för dataförlustskydd (DLP) som meddelar användarna när de delar ett dokument med etiketten Känslig på en SharePoint Online-gruppwebbplats utanför organisationen. DLP-principen används för resurser som finns på kampanjmarknadsföringens webbplats.</span><span class="sxs-lookup"><span data-stu-id="362a1-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="362a1-209">På fliken **Microsoft Office Home** i webbläsaren genom att klicka på **Säkerhet och efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="362a1-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="362a1-210">På den nya fliken **Säkerhet och efterlevnad** i din webbläsare klickar du på **dataförlustskydd > Policy**.</span><span class="sxs-lookup"><span data-stu-id="362a1-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="362a1-211">I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="362a1-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="362a1-212">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="362a1-213">I fönstret **Namnge principen** skriver du **Etiketten Känslig, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="362a1-214">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="362a1-215">Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-216">I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="362a1-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="362a1-217">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="362a1-218">I fönstret **Etikett** klickar du på **+ Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="362a1-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="362a1-219">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="362a1-220">I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="362a1-221">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="362a1-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="362a1-222">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="362a1-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="362a1-223">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="362a1-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="362a1-224">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="362a1-224">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="362a1-225">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="362a1-225">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="362a1-226">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="362a1-226">Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="362a1-227">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-227">Click **OK**.</span></span>

17. <span data-ttu-id="362a1-228">I fönstret **Vad vill du göra om vi identifierar känslig information?** avmarkerar du kryssrutan **Blockera andra från att dela och begränsa åtkomsten till delat innehåll**, och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="362a1-229">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="362a1-230">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="362a1-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="362a1-231">Gruppwebbplats för kampanjstrategi</span><span class="sxs-lookup"><span data-stu-id="362a1-231">Campaign strategy team site</span></span>

<span data-ttu-id="362a1-232">Gör så här om du vill skapa en isolerad SharePoint Online-gruppwebbplats med hög sekretessnivå för kampanjstrategiresurser:</span><span class="sxs-lookup"><span data-stu-id="362a1-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="362a1-233">Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="362a1-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="362a1-234">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="362a1-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="362a1-235">På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="362a1-236">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="362a1-237">Skriv **Kampanjstrategi** i **Namn på gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="362a1-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="362a1-238">I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjstrategi (strikt konfidentiellt)**.</span><span class="sxs-lookup"><span data-stu-id="362a1-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="362a1-239">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-240">I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="362a1-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="362a1-241">Gå till den nya fliken **Kampanjstrategi** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="362a1-242">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="362a1-243">Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="362a1-244">I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp** (så att alla tre kryssrutorna är avmarkerade). Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="362a1-245">Klicka på **Kampanjstrategi-Medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="362a1-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="362a1-246">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="362a1-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="362a1-247">I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="362a1-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="362a1-248">Klicka på **Kampanjstrategi-Ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="362a1-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="362a1-249">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="362a1-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="362a1-250">I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="362a1-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="362a1-251">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="362a1-252">Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjstrategi-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="362a1-253">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="362a1-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="362a1-254">SharePoint-gruppen **Kampanjstrategi-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som endast innehåller användarkontona Candidate, ChiefOfStaff och Strategic1) och gruppen **Kampanjstrategi** (som bara innehåller det globala administratörsanvändarkontot).</span><span class="sxs-lookup"><span data-stu-id="362a1-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="362a1-255">SharePoint-gruppen **Kampanjstrategi-Ägare** innehåller bara gruppen **IT-personal** (som endast innehåller användarkontona ITAdmin1 och ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="362a1-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="362a1-256">SharePoint-gruppen **Kampanjstrategi-Besökare** innehåller inga grupp- eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="362a1-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="362a1-257">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjstrategi-Ägare**).</span><span class="sxs-lookup"><span data-stu-id="362a1-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="362a1-258">Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="362a1-258">Other user accounts cannot access the site or its resources or request access to the site.</span></span> <span data-ttu-id="362a1-259">Ytterligare behörigheter för webbplatsen måste utföras av en global administratör eller en medlem i gruppen **Kampanjstrategi-Ägare**.</span><span class="sxs-lookup"><span data-stu-id="362a1-259">Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="362a1-260">Därefter konfigurerar du dokumentmappen för kampanjstrategins gruppwebbplats med etiketten Strikt konfidentiellt.</span><span class="sxs-lookup"><span data-stu-id="362a1-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="362a1-261">På fliken **Kampanjstrategi-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="362a1-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="362a1-262">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="362a1-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="362a1-263">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="362a1-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="362a1-264">I **Inställningar-Använd etikett** väljer du **Strikt konfidentiellt** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="362a1-p109">Därefter konfigurerar du en DLP-princip som blockerar användare när de delar ett dokument med etiketten Strikt konfidentiellt på en SharePoint Online-gruppwebbplats som finns utanför organisationen. Den här DLP-principen används för resurser på kampanjstrategins webbplats.</span><span class="sxs-lookup"><span data-stu-id="362a1-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="362a1-267">Om det behövs kan du använda webbläsaren på din lokala dator och logga in på administrationscentret för (<https://admin.microsoft.com>) med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="362a1-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="362a1-268">På fliken **Microsoft Office Home** i webbläsaren genom att klicka på **Säkerhet och efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="362a1-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="362a1-269">På den nya fliken **Säkerhet och efterlevnad** i din webbläsare klickar du på **dataförlustskydd > Policy**.</span><span class="sxs-lookup"><span data-stu-id="362a1-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="362a1-270">I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="362a1-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="362a1-271">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="362a1-272">I fönstret **Namnge principen** skriver du **Etiketten Strikt konfidentiellt, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="362a1-273">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="362a1-274">Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="362a1-275">I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="362a1-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="362a1-276">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="362a1-277">I rutan **Etiketter** klickar du på **+ Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="362a1-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="362a1-278">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="362a1-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="362a1-279">I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="362a1-280">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="362a1-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="362a1-281">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="362a1-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="362a1-282">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="362a1-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="362a1-283">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="362a1-283">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="362a1-284">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="362a1-284">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="362a1-285">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="362a1-285">Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="362a1-286">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-286">Click **OK**.</span></span>

18. <span data-ttu-id="362a1-287">I fönstret **Vad vill du göra om vi identifierar känslig information?** väljer du **Kräv en affärsrelaterad motivering för att åsidosätta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="362a1-288">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="362a1-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="362a1-289">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="362a1-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="362a1-290">Använd instruktionerna i [Aktivera Azure RMS med administrationscentret för Microsoft 365](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="362a1-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="362a1-291">Konfigurera sedan Azure Information Protection med en ny begränsad princip och en underetikett för skydd och behörigheter med följande steg:</span><span class="sxs-lookup"><span data-stu-id="362a1-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="362a1-292">Logga in på administrationscentret med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="362a1-292">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="362a1-293">Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="362a1-293">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="362a1-294">Gå till Azure-portalen (<https://portal.azure.com>) på en separat flik i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="362a1-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="362a1-295">I sökfönstret skriver du **information** och klickar sedan på **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="362a1-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="362a1-296">Klicka på **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-296">Click **Labels**.</span></span>

5. <span data-ttu-id="362a1-297">Högerklicka på etiketten **Strikt konfidentiellt** och klicka sedan på **Lägg till en underetikett**.</span><span class="sxs-lookup"><span data-stu-id="362a1-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="362a1-298">Skriv **CampaignStrategy** i **Namn** och **Etikett för dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="362a1-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="362a1-299">I **Ange behörigheter för dokument och e-postmeddelanden som innehåller den här etiketten** klickar du på **Skydda**.</span><span class="sxs-lookup"><span data-stu-id="362a1-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="362a1-300">I avsnittet **Säkerhet** klickar du på **Azure (molnnyckel)**.</span><span class="sxs-lookup"><span data-stu-id="362a1-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="362a1-301">På bladet **Säkerhet** klickar du på **+ Lägg till behörigheter** under **Skyddsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="362a1-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="362a1-302">På bladet **Lägg till behörigheter** klickar du på **+ Bläddra i katalog** under **Ange användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="362a1-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="362a1-303">I fönstret **AAD-användare och grupper** väljer du **Seniora och strategisk personal**. Klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="362a1-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="362a1-304">Under **Välj behörigheter från förinställt eller ange anpassad** klickar du på **Anpassad** och sedan i kryssrutorna **Visa rättigheter**, **Redigera innehåll**, **Spara**, **Svara** och **Svara alla**.</span><span class="sxs-lookup"><span data-stu-id="362a1-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="362a1-305">Klicka på **OK** två gånger.</span><span class="sxs-lookup"><span data-stu-id="362a1-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="362a1-306">På bladet **Underetikett** klickar du på **Spara** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="362a1-307">Klicka på **Principer > + Lägg till en ny princip** på bladet **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="362a1-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="362a1-308">Skriv **CampaignStrategy** i **Namn** och **Dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="362a1-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="362a1-309">Klicka på **Välj vilka användare eller grupper som får den här principen > Användare/grupper** och välj sedan **Seniora och strategisk personal**.</span><span class="sxs-lookup"><span data-stu-id="362a1-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="362a1-310">Klicka på **Välj \> OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="362a1-311">Klicka på **Lägg till eller ta bort etiketter**.</span><span class="sxs-lookup"><span data-stu-id="362a1-311">Click **Add or remove labels**.</span></span> <span data-ttu-id="362a1-312">I fönstret **Princip: Lägg till eller ta bort etiketter** klickar du på **CampaignStrategy** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-312">In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="362a1-313">Klicka på **Spara** och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="362a1-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="362a1-314">Du är nu redo att börja skapa dokument på dessa fyra webbplatser och testa åtkomsten till dem med olika användarkonton.</span><span class="sxs-lookup"><span data-stu-id="362a1-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="362a1-315">Om du vill skydda ett dokument med Azure Information Protection och den här nya etiketten, måste du [installera Azure Information Protection-klienten](/information-protection/rms-client/install-client-app) på en testdator, installera Office från administrationscentret och sedan logga in med ett konto i gruppen **Seniora och strategisk personal** i utvärderingsprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="362a1-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="362a1-316">Se även</span><span class="sxs-lookup"><span data-stu-id="362a1-316">See Also</span></span>

[<span data-ttu-id="362a1-317">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer</span><span class="sxs-lookup"><span data-stu-id="362a1-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="362a1-318">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="362a1-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="362a1-319">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="362a1-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="362a1-320">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="362a1-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)
