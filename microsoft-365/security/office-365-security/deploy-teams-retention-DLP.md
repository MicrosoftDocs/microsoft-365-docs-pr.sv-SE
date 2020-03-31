---
title: Skydda filer i team med kvarhållningsetiketter och DLP
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Sammanfattning: Tillämpa kvarhållningsetiketter och principer för dataförlustskydd (DLP) för filer i team med olika nivåer av informationsskydd.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808128"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="9f66e-103">Skydda filer i team med kvarhållningsetiketter och DLP</span><span class="sxs-lookup"><span data-stu-id="9f66e-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="9f66e-104">Använd anvisningarna i den här artikeln för att utforma och distribuera kvarhållningsetiketter och principer för dataförlustskydd (DLP) för grundläggande, känsliga och strikt konfidentiella team och de underliggande SharePoint-webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="9f66e-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="9f66e-105">Mer information om de här tre nivåerna av skydd finns i [Skydda filer i Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9f66e-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="9f66e-106">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="9f66e-106">How this works</span></span>

1. <span data-ttu-id="9f66e-107">Skapa de önskade kvarhållningsetiketterna och publicera dem.</span><span class="sxs-lookup"><span data-stu-id="9f66e-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="9f66e-108">Det kan ta upp till 12 timmar innan de publiceras.</span><span class="sxs-lookup"><span data-stu-id="9f66e-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="9f66e-109">För de önskade underliggande SharePoint-webbplatserna redigerar du dokumentbiblioteksinställningarna så att de önskade kvarhållningsetiketterna används för objekt i biblioteket.</span><span class="sxs-lookup"><span data-stu-id="9f66e-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="9f66e-110">Skapa DLP-principer för åtgärder baserat på kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="9f66e-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="9f66e-111">När användare lägger till ett dokument i det underliggande SharePoint-webbplatsbiblioteket för teamet får dokumentet den tilldelade kvarhållningsetiketten som standard.</span><span class="sxs-lookup"><span data-stu-id="9f66e-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="9f66e-112">Användare kan ändra etiketten om det behövs.</span><span class="sxs-lookup"><span data-stu-id="9f66e-112">Users can change the label, if needed.</span></span> <span data-ttu-id="9f66e-113">När en användare delar ett dokument utanför organisationen kommer DLP att kontrollera om en etikett har tilldelats och vidta åtgärder om en DLP-princip matchar etiketten.</span><span class="sxs-lookup"><span data-stu-id="9f66e-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="9f66e-114">DLP kommer även att leta efter andra principmatchningar, t.ex. för att skydda filer med kreditkortsnummer om den typen av princip har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="9f66e-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="9f66e-115">Kvarhållningsetiketter för dina underliggande SharePoint-webbplatser</span><span class="sxs-lookup"><span data-stu-id="9f66e-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="9f66e-116">Det finns tre faser för att skapa och sedan tilldela kvarhållningsetiketter för de underliggande SharePoint-webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="9f66e-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="9f66e-117">Steg 1: Bestäm namnen på kvarhållningsetiketterna</span><span class="sxs-lookup"><span data-stu-id="9f66e-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="9f66e-118">I den här fasen bestämmer du namnen på dina kvarhållningsetiketter för de fyra nivåerna av informationsskydd som tillämpas på underliggande SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="9f66e-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="9f66e-119">I följande tabell visas de rekommenderade namnen för respektive nivå.</span><span class="sxs-lookup"><span data-stu-id="9f66e-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="9f66e-120">**Skyddsnivå för underliggande SharePoint-webbplatser**</span><span class="sxs-lookup"><span data-stu-id="9f66e-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="9f66e-121">**Etikettnamn**</span><span class="sxs-lookup"><span data-stu-id="9f66e-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f66e-122">Baseline-Public</span><span class="sxs-lookup"><span data-stu-id="9f66e-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="9f66e-123">Intern offentlig</span><span class="sxs-lookup"><span data-stu-id="9f66e-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="9f66e-124">Baseline-Private</span><span class="sxs-lookup"><span data-stu-id="9f66e-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="9f66e-125">Privat</span><span class="sxs-lookup"><span data-stu-id="9f66e-125">Private</span></span>  <br/> |
|<span data-ttu-id="9f66e-126">Känslig</span><span class="sxs-lookup"><span data-stu-id="9f66e-126">Sensitive</span></span>  <br/> |<span data-ttu-id="9f66e-127">Känslig</span><span class="sxs-lookup"><span data-stu-id="9f66e-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="9f66e-128">Strikt konfidentiell</span><span class="sxs-lookup"><span data-stu-id="9f66e-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="9f66e-129">Strikt konfidentiell</span><span class="sxs-lookup"><span data-stu-id="9f66e-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="9f66e-130">Steg 2: Skapa kvarhållningsetiketterna</span><span class="sxs-lookup"><span data-stu-id="9f66e-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="9f66e-131">I den här fasen skapar du och publicerar sedan de etiketter som du definierat för olika nivåer av informationsskydd.</span><span class="sxs-lookup"><span data-stu-id="9f66e-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="9f66e-132">Logga in på [efterlevnadsportalen för Microsoft 365](https://compliance.microsoft.com) med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="9f66e-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="9f66e-133">På fliken **Start – Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Klassifikationer > Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="9f66e-134">Klicka på **Kvarhållningsetiketter > Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="9f66e-135">I fönstret **Namnge din etikett** skriver du namnet på etiketten och en beskrivning för administratörer och användare och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="9f66e-136">I fönstret **Filplansbeskrivningar** fyller du i efter behov och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9f66e-137">I fönstret **Etikettinställningar** anger du vid behov **Kvarhållning** till **På** och konfigurerar kvarhållningsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="9f66e-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="9f66e-138">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="9f66e-139">I fönstret **Granska inställningarna** klickar du på **Skapa etiketten**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="9f66e-140">Om du behöver ytterligare etiketter klickar du på **Skapa en etikett** och upprepar sedan steg 3–7 i den här proceduren efter behov.</span><span class="sxs-lookup"><span data-stu-id="9f66e-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="9f66e-141">Publicera dina nya etiketter</span><span class="sxs-lookup"><span data-stu-id="9f66e-141">Publish your new labels</span></span>

<span data-ttu-id="9f66e-142">Följ de här anvisningarna för att publicera de nya kvarhållningsetiketterna.</span><span class="sxs-lookup"><span data-stu-id="9f66e-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="9f66e-143">I fönstret **Etiketter** klickar du på fliken **Kvarhållningsetiketter** och sedan på **Publicera etiketter**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="9f66e-144">I fönstret **Välj etiketter att publicera** klickar du på **Välj etiketter att publicera**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="9f66e-145">I fönstret **Välj etiketter** klickar du på **Lägg till**, markerar alla fyra etiketterna och klickar på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="9f66e-146">Klicka på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="9f66e-147">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="9f66e-148">I fönstret **Välj platser** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="9f66e-149">I fönstret **Namnge principen** skriver du ett namn på uppsättningen med etiketter i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9f66e-150">I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="9f66e-151">Steg 3: Tillämpa kvarhållningsetiketterna för dina underliggande SharePoint-webbplatser</span><span class="sxs-lookup"><span data-stu-id="9f66e-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="9f66e-152">Använd de här anvisningarna för att tillämpa kvarhållningsetiketterna för dokumentmapparna på de underliggande SharePoint-webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="9f66e-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="9f66e-153">Klicka på **Filer** i teamet och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="9f66e-154">På den nya fliken för SharePoint-webbplatsen i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="9f66e-155">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="9f66e-156">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="9f66e-157">Välj önskad kvarhållningsetikett i **Inställningar – Använd etikett** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="9f66e-158">Stäng fliken för SharePoint-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9f66e-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="9f66e-159">Upprepa steg 1–6 för att tilldela kvarhållningsetiketter till dina underliggande SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="9f66e-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="9f66e-160">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="9f66e-160">Here is your resulting configuration.</span></span>
  
![Kvarhållningsetiketter för de fyra typerna av underliggande SharePoint-webbplatser.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="9f66e-162">DLP-principer för dina underliggande SharePoint-webbplatser</span><span class="sxs-lookup"><span data-stu-id="9f66e-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="9f66e-163">Använd följande steg för att konfigurera en DLP-princip som meddelar användare när de delar ett dokument på en underliggande SharePoint-webbplats utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f66e-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="9f66e-164">Logga in på [efterlevnadsportalen för Microsoft 365](https://compliance.microsoft.com/) med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="9f66e-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="9f66e-165">På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="9f66e-166">I fönstret **Start > Dataförlustskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="9f66e-167">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassad** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="9f66e-168">I fönstret **Namnge principen** skriver du namnet på DLP-principen för känslig nivå i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9f66e-169">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9f66e-170">Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9f66e-171">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="9f66e-172">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="9f66e-173">I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="9f66e-174">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="9f66e-175">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="9f66e-176">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="9f66e-177">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="9f66e-178">I textrutan skriver du eller klistrar in något av följande tips:</span><span class="sxs-lookup"><span data-stu-id="9f66e-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="9f66e-179">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="9f66e-179">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="9f66e-180">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="9f66e-180">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="9f66e-181">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="9f66e-181">Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="9f66e-182">Strikt konfidentiella filer skyddas med kryptering.</span><span class="sxs-lookup"><span data-stu-id="9f66e-182">Highly confidential files are protected with encryption.</span></span> <span data-ttu-id="9f66e-183">Bara externa användare som har beviljats åtkomst till dessa filer av IT-avdelningen kan läsa dem.</span><span class="sxs-lookup"><span data-stu-id="9f66e-183">Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="9f66e-184">Alternativt kan du skriva eller klistra in egna principtips som instruerar användarna om hur de delar en fil utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f66e-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="9f66e-185">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="9f66e-186">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="9f66e-187">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="9f66e-188">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="9f66e-189">Här är konfigurationsresultatet för känsliga team.</span><span class="sxs-lookup"><span data-stu-id="9f66e-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![DLP-princip för känsligt team med hjälp av kvarhållningsetiketten Känsligt](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="9f66e-191">Använd följande steg för att konfigurera en DLP-princip som blockerar användare när de delar ett dokument på en underliggande SharePoint-webbplats utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f66e-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="9f66e-192">På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="9f66e-193">I fönstret **Dataförlustskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="9f66e-194">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassad** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="9f66e-195">I fönstret **Namnge principen** skriver du namnet på DLP-principen för mycket känslig nivå i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="9f66e-196">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="9f66e-197">Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9f66e-198">I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="9f66e-199">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="9f66e-200">I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="9f66e-201">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="9f66e-202">I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="9f66e-203">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="9f66e-204">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="9f66e-205">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="9f66e-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="9f66e-206">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="9f66e-206">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="9f66e-207">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="9f66e-207">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="9f66e-208">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="9f66e-208">Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="9f66e-209">Alternativt kan du skriva eller klistra in egna principtips som instruerar användarna om hur de delar en fil utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f66e-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="9f66e-210">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="9f66e-211">I fönstret **Vad vill du göra om vi identifierar känslig information?**, under **Identifiera när en viss mängd känslig information delas vid ett tillfälle**, klickar du på **Begränsa åtkomst eller kryptera innehållet** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="9f66e-212">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="9f66e-213">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9f66e-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="9f66e-214">Här är konfigurationsresultatet för strikt konfidentiellt team.</span><span class="sxs-lookup"><span data-stu-id="9f66e-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![DLP-princip för ett strikt konfidentiellt team som använder kvarhållningsetiketten Strikt konfidentiellt](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="9f66e-216">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9f66e-216">Next step</span></span>

[<span data-ttu-id="9f66e-217">Skydda filer i team med känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="9f66e-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="9f66e-218">Se även</span><span class="sxs-lookup"><span data-stu-id="9f66e-218">See Also</span></span>

[<span data-ttu-id="9f66e-219">Skydda filer i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66e-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="9f66e-220">Införande av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="9f66e-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


