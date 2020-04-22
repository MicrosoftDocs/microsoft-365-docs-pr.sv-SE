---
title: Dataklassificering för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill skapa och använda kvarhållningsetiketter på dokument i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636098"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b49b5-103">Dataklassificering för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="b49b5-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b49b5-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="b49b5-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b49b5-105">Med instruktionerna i den här artikeln konfigurerar du dataklassificering med hjälp av kvarhållningsetiketter i Microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="b49b5-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b49b5-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="b49b5-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b49b5-108">Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b49b5-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b49b5-109">Om du bara vill konfigurera kvarhållningsetiketter på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b49b5-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b49b5-110">Om du vill konfigurera kvarhållningsetiketter i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b49b5-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b49b5-111">Testning av kvarhållningsetiketter kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="b49b5-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b49b5-112">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="b49b5-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="b49b5-113">Fas 2: Skapa kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="b49b5-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="b49b5-114">I den här fasen skapar du kvarhållningsetiketterna för de olika nivåerna för kvarhållning för SharePoint Online-dokumentmappar.</span><span class="sxs-lookup"><span data-stu-id="b49b5-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="b49b5-115">Logga in på [Microsoft 365-säkerhetscentret](https://security.microsoft.com/homepage) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b49b5-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="b49b5-116">Klicka på **Klassificering > lagringsetiketter**på **fliken Start - Microsoft 365** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="b49b5-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="b49b5-117">Klicka på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="b49b5-118">Skriv **Internt offentligt** i Namn **på etiketten**i fönstret Namn på **etiketten** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="b49b5-119">Klicka på **Nästa**i fönstret **Filplansbeskrivningar** .</span><span class="sxs-lookup"><span data-stu-id="b49b5-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="b49b5-120">Ställ in **Kvarhållning** till **På**i fönstret **Etikettinställningar** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b49b5-121">Klicka på Skapa etiketten **i**fönstret **Granska dina inställningar** .</span><span class="sxs-lookup"><span data-stu-id="b49b5-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="b49b5-122">Upprepa steg 3-7 för ytterligare etiketter med följande namn:</span><span class="sxs-lookup"><span data-stu-id="b49b5-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="b49b5-123">Privat</span><span class="sxs-lookup"><span data-stu-id="b49b5-123">Private</span></span>
    
  - <span data-ttu-id="b49b5-124">Känslig</span><span class="sxs-lookup"><span data-stu-id="b49b5-124">Sensitive</span></span>
    
  - <span data-ttu-id="b49b5-125">Strikt konfidentiell</span><span class="sxs-lookup"><span data-stu-id="b49b5-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="b49b5-126">Klicka på Publicera etiketter i fönstret **Kvarhållningsetiketter.** **Publish labels**</span><span class="sxs-lookup"><span data-stu-id="b49b5-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="b49b5-127">Klicka på Välj etiketter att publicera i fönstret **Välj etiketter** som **ska publiceras.**</span><span class="sxs-lookup"><span data-stu-id="b49b5-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="b49b5-128">Klicka på **Lägg till** i fönstret **Välj etiketter** och markera alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="b49b5-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="b49b5-129">Klicka på **Lägg till**och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="b49b5-130">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="b49b5-131">Klicka på **Nästa** i fönstret **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="b49b5-132">I fönstret **Namnge principen** skriver du **Organisationsexempel** i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="b49b5-133">Klicka på **Publicera etiketter**i fönstret **Granska inställningar** .</span><span class="sxs-lookup"><span data-stu-id="b49b5-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="b49b5-134">Observera att det kan ta några minuter innan lagringsetiketterna publiceras.</span><span class="sxs-lookup"><span data-stu-id="b49b5-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="b49b5-135">Fas 3: Använda lagringsetiketter på dokument</span><span class="sxs-lookup"><span data-stu-id="b49b5-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="b49b5-136">I den här fasen identifierar du standardetiketten för lagringsetikett för filer i mappen Dokument på en SharePoint Online-webbplats och ändrar ett dokuments kvarhållningsetikett manuellt.</span><span class="sxs-lookup"><span data-stu-id="b49b5-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="b49b5-137">Skapa först en sharepoint-gruppwebbplats på känslig nivå:</span><span class="sxs-lookup"><span data-stu-id="b49b5-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="b49b5-138">Logga in på [Office 365-portalen](https://portal.office.com) med hjälp av en privat instans av webbläsaren med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b49b5-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="b49b5-139">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="b49b5-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="b49b5-140">Klicka på **Skapa webbplats**på den nya **fliken SharePoint** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="b49b5-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="b49b5-141">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="b49b5-142">Skriv **Känsliga filer**i **Gruppwebbplatsnamn**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="b49b5-143">Skriv **SharePoint-webbplats för känsliga filer i** **Gruppwebbplatsbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="b49b5-144">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b49b5-145">Klicka på **Slutför**i fönstret **Vem vill du lägga till?**</span><span class="sxs-lookup"><span data-stu-id="b49b5-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="b49b5-146">Konfigurera sedan mappen Dokument på teamplatsen SensitiveFiles för etiketten Känslig kvarhållning.</span><span class="sxs-lookup"><span data-stu-id="b49b5-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="b49b5-147">Klicka på **Dokument**på fliken **Känsliga filer** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="b49b5-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="b49b5-148">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="b49b5-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="b49b5-149">Klicka på **Använd etikett på objekt i listan eller biblioteket under** **Behörigheter och hantering.**</span><span class="sxs-lookup"><span data-stu-id="b49b5-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="b49b5-150">Om det här alternativet inte visas har behållaniketterna ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="b49b5-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="b49b5-151">Prova det här steget vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="b49b5-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="b49b5-152">I **Inställningsansöka etikett**väljer du **Känslig** i listrutan och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="b49b5-153">Skapa sedan ett nytt dokument på plats SensitiveFiles och ändra dess kvarhållningsetikett.</span><span class="sxs-lookup"><span data-stu-id="b49b5-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="b49b5-154">Klicka på Nytt **> Word-dokument i dokumentmappen**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="b49b5-155">Skriv text i det tomma dokumentet.</span><span class="sxs-lookup"><span data-stu-id="b49b5-155">Type some text in the blank document.</span></span> <span data-ttu-id="b49b5-156">Vänta tills texten har sparats.</span><span class="sxs-lookup"><span data-stu-id="b49b5-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="b49b5-157">Klicka på Delade **dokument**på menyraden.</span><span class="sxs-lookup"><span data-stu-id="b49b5-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="b49b5-158">Klicka på den lodräta ellipsen bredvid filnamnet **Document.docx** och klicka sedan på **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="b49b5-159">I det högra fönstret, i avsnittet **Egenskaper,** under **Använd kvarhållningsetikett,** bör du tänka på att dokumentet har tillämpat etiketten **Känslig** kvarhållning automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b49b5-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="b49b5-160">Klicka på **Redigera alla**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="b49b5-161">Markera etiketten **Mycket konfidentiell** under **Använd kvarhållningsetikett**i fönstret **Document.docx** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b49b5-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="b49b5-162">Mer information och länkar till hur du distribuerar kvarhållningsetiketter i produktionen finns i steget [Konfigurera klassificering för din miljö](infoprotect-configure-classification.md) i **informationsskyddsfasen.**</span><span class="sxs-lookup"><span data-stu-id="b49b5-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b49b5-163">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b49b5-163">Next step</span></span>

<span data-ttu-id="b49b5-164">Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="b49b5-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b49b5-165">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="b49b5-165">See also</span></span>

[<span data-ttu-id="b49b5-166">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b49b5-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b49b5-167">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b49b5-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b49b5-168">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="b49b5-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
