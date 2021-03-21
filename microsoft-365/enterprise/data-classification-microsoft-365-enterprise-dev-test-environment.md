---
title: Dataklassificering för testmiljön Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här testlabbguiden för att skapa och använda bevarandeetiketter på dokument i din Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919194"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="77e08-103">Dataklassificering för testmiljön Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="77e08-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="77e08-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="77e08-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="77e08-105">I den här artikeln beskrivs hur du konfigurerar dataklassificering med hjälp av bevarandeetiketter i testmiljön Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="77e08-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="77e08-106">Klassificering av data i testmiljön omfattar tre faser:</span><span class="sxs-lookup"><span data-stu-id="77e08-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="77e08-107">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="77e08-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="77e08-108">Fas 2: Skapa bevarandeetiketter</span><span class="sxs-lookup"><span data-stu-id="77e08-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="77e08-109">Fas 3: Använda bevarandeetiketter i dokument</span><span class="sxs-lookup"><span data-stu-id="77e08-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="77e08-111">En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.</span><span class="sxs-lookup"><span data-stu-id="77e08-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="77e08-112">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="77e08-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="77e08-113">Om du bara vill konfigurera bevarandeetiketter på ett lätt sätt med minimikraven följer du anvisningarna i Enkel [baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="77e08-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="77e08-114">Om du vill konfigurera bevarandeetiketter i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="77e08-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77e08-115">För testning av bevarandeetiketter krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="77e08-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="77e08-116">Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="77e08-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="77e08-117">Fas 2: Skapa bevarandeetiketter</span><span class="sxs-lookup"><span data-stu-id="77e08-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="77e08-118">I den här fasen skapar du bevarandeetiketter för de olika bevarandenivåerna för SharePoint Online-dokumentmappar:</span><span class="sxs-lookup"><span data-stu-id="77e08-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="77e08-119">Logga in på [Microsoft 365 Säkerhetscenter med](https://security.microsoft.com/homepage) ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="77e08-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="77e08-120">Välj **Klassificeringslagringsetiketter** på fliken Start – Microsoft 365-säkerhet   >  **i webbläsaren.**</span><span class="sxs-lookup"><span data-stu-id="77e08-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="77e08-121">Välj **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="77e08-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="77e08-122">I fönstret **Namnge din etikett** anger du Intern **offentlig** i Namnge **din etikett** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="77e08-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="77e08-123">I fönstret **Filplansbeskrivningar** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="77e08-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="77e08-124">Om det **behövs går** du till fönstret Etikettinställningar och ställer **in Bevarande** **på** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="77e08-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="77e08-125">I fönstret **Granska dina** inställningar väljer du **Skapa etiketten**.</span><span class="sxs-lookup"><span data-stu-id="77e08-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="77e08-126">Upprepa steg 3–7 för ytterligare etiketter med följande namn:</span><span class="sxs-lookup"><span data-stu-id="77e08-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="77e08-127">Privat</span><span class="sxs-lookup"><span data-stu-id="77e08-127">Private</span></span>
  - <span data-ttu-id="77e08-128">Känslig</span><span class="sxs-lookup"><span data-stu-id="77e08-128">Sensitive</span></span>
  - <span data-ttu-id="77e08-129">Strikt konfidentiellt</span><span class="sxs-lookup"><span data-stu-id="77e08-129">Highly Confidential</span></span>
1. <span data-ttu-id="77e08-130">I fönstret **Bevarandeetiketter** väljer du **Publicera etiketter.**</span><span class="sxs-lookup"><span data-stu-id="77e08-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="77e08-131">I fönstret **Välj etiketter som ska publiceras** väljer du Välj etiketter att **publicera.**</span><span class="sxs-lookup"><span data-stu-id="77e08-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="77e08-132">I fönstret **Välj etiketter** väljer du Lägg **till och** markerar alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="77e08-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="77e08-133">Välj **Lägg** till och välj sedan **Klar**.</span><span class="sxs-lookup"><span data-stu-id="77e08-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="77e08-134">Välj Nästa **i fönstret Välj etiketter** som ska **publiceras.**</span><span class="sxs-lookup"><span data-stu-id="77e08-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="77e08-135">I **fönstret Välj platser** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="77e08-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="77e08-136">I fönstret **Namnge principen** anger du Exempel **på organisation** **i Namn** och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="77e08-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="77e08-137">I fönstret **Granska dina inställningar** väljer du Publicera **etiketter**.</span><span class="sxs-lookup"><span data-stu-id="77e08-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="77e08-138">Det kan ta några minuter innan de bevarandeetiketter som publiceras publiceras.</span><span class="sxs-lookup"><span data-stu-id="77e08-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="77e08-139">Fas 3: Använda bevarandeetiketter i dokument</span><span class="sxs-lookup"><span data-stu-id="77e08-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="77e08-140">I den här fasen upptäcker du standardbeteendet för bevarandeetiketter för filer i mappen Dokument på en SharePoint Online-webbplats och ändrar manuellt bevarandeetiketten för ett dokument.</span><span class="sxs-lookup"><span data-stu-id="77e08-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="77e08-141">Skapa först en SharePoint Online-gruppwebbplats med känslig nivå:</span><span class="sxs-lookup"><span data-stu-id="77e08-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="77e08-142">Använd en privat instans av webbläsaren och logga in på [administrationscentret för Microsoft 365 med ditt](https://admin.microsoft.com) globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="77e08-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="77e08-143">Välj SharePoint i listan med **paneler.**</span><span class="sxs-lookup"><span data-stu-id="77e08-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="77e08-144">På den nya **SharePoint-fliken** i webbläsaren väljer du **Skapa webbplats.**</span><span class="sxs-lookup"><span data-stu-id="77e08-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="77e08-145">På sidan **Skapa en webbplats** väljer du **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="77e08-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="77e08-146">I rutan **Gruppwebbplatsens** namn anger du **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="77e08-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="77e08-147">Ange **SharePoint-webbplats för** känsliga filer i **rutan Beskrivning av gruppwebbplats.**</span><span class="sxs-lookup"><span data-stu-id="77e08-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="77e08-148">I **Sekretessinställningar** väljer du **Privat – endast medlemmar kan komma åt den här** webbplatsen och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="77e08-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="77e08-149">I fönstret **Vem vill du lägga till?** väljer du **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="77e08-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="77e08-150">Konfigurera sedan mappen Dokument på gruppwebbplatsen SensitiveFiles för bevarandeetiketten Känslig.</span><span class="sxs-lookup"><span data-stu-id="77e08-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="77e08-151">På **fliken KänsligaFiler** i webbläsaren väljer du **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="77e08-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="77e08-152">Välj ikonen **Inställningar** och välj sedan **Biblioteksinställningar**.</span><span class="sxs-lookup"><span data-stu-id="77e08-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="77e08-153">Under **Behörigheter och hantering** väljer du Använd etikett för objekt i listan eller **biblioteket**.</span><span class="sxs-lookup"><span data-stu-id="77e08-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="77e08-154">Om det här alternativet inte visas har dina kvarhållningsetiketter ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="77e08-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="77e08-155">Prova det här steget senare.</span><span class="sxs-lookup"><span data-stu-id="77e08-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="77e08-156">I **Inställningar-Använd etikett** väljer **du** Känslig i listrutan och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="77e08-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="77e08-157">Skapa sedan ett nytt dokument på webbplatsen SensitiveFiles och ändra dess bevarandeetikett.</span><span class="sxs-lookup"><span data-stu-id="77e08-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="77e08-158">Välj Nytt Word-dokument **i**  >  **dokumentmappen.**</span><span class="sxs-lookup"><span data-stu-id="77e08-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="77e08-159">Skriv lite text i det tomma dokumentet.</span><span class="sxs-lookup"><span data-stu-id="77e08-159">Enter some text in the blank document.</span></span> <span data-ttu-id="77e08-160">Vänta tills texten har sparats.</span><span class="sxs-lookup"><span data-stu-id="77e08-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="77e08-161">På menyraden väljer du **Delade dokument**.</span><span class="sxs-lookup"><span data-stu-id="77e08-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="77e08-162">Markera de **lodrätaDocument.docx** bredvid filnamnet och välj sedan **Information**.</span><span class="sxs-lookup"><span data-stu-id="77e08-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="77e08-163">Observera att bevarandeetiketten  Känslig har använts automatiskt **i** dokumentet under  Använd bevarandeetikett i den högra rutan i avsnittet Egenskaper.</span><span class="sxs-lookup"><span data-stu-id="77e08-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="77e08-164">Klicka **på Redigera alla**.</span><span class="sxs-lookup"><span data-stu-id="77e08-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="77e08-165">I **Document.docx** under Använd **bevarandeetikett** väljer du etiketten **Konfidentiellt** och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="77e08-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="77e08-166">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="77e08-166">Next step</span></span>

<span data-ttu-id="77e08-167">Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="77e08-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="77e08-168">Se även</span><span class="sxs-lookup"><span data-stu-id="77e08-168">See also</span></span>

[<span data-ttu-id="77e08-169">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="77e08-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="77e08-170">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="77e08-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="77e08-171">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="77e08-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)