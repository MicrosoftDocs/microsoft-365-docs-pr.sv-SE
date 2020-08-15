---
title: Data klassificering för test miljön av Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att skapa och använda behållnings etiketter i dokument i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686412"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e400e-103">Data klassificering för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e400e-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e400e-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="e400e-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e400e-105">Med instruktionerna i den här artikeln konfigurerar du data klassificering med hjälp av lagrings etiketter i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="e400e-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e400e-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="e400e-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e400e-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e400e-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e400e-109">Om du bara vill konfigurera behållnings etiketter på ett sätt som uppfyller minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e400e-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e400e-110">Om du vill konfigurera behållnings etiketter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e400e-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e400e-111">Det krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalog-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="e400e-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e400e-112">Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="e400e-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="e400e-113">Fas 2: skapa behållnings etiketter</span><span class="sxs-lookup"><span data-stu-id="e400e-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="e400e-114">I den här fasen skapar du lagrings etiketterna för de olika nivåerna av bevarande för SharePoint Online-dokument.</span><span class="sxs-lookup"><span data-stu-id="e400e-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="e400e-115">Logga in på [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage) med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="e400e-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="e400e-116">Klicka på **klassificering > behållnings etiketter**på fliken **hem-Microsoft 365-säkerhet** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e400e-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="e400e-117">Klicka på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="e400e-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="e400e-118">Ange **intern allmän** i **namn på etiketten**i rutan **namn** på etikett och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e400e-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="e400e-119">Klicka på **Nästa**i fönstret **fil Plans beskrivningar** .</span><span class="sxs-lookup"><span data-stu-id="e400e-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="e400e-120">I fönstret **etikett inställningar** , om det behövs, ange **behållningen** till **den**och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e400e-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e400e-121">I fönstret **Granska inställningar** klickar **du på skapa etiketten**.</span><span class="sxs-lookup"><span data-stu-id="e400e-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="e400e-122">Upprepa steg 3-7 för ytterligare etiketter med följande namn:</span><span class="sxs-lookup"><span data-stu-id="e400e-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="e400e-123">Privat</span><span class="sxs-lookup"><span data-stu-id="e400e-123">Private</span></span>
    
  - <span data-ttu-id="e400e-124">Känslig</span><span class="sxs-lookup"><span data-stu-id="e400e-124">Sensitive</span></span>
    
  - <span data-ttu-id="e400e-125">Strikt konfidentiellt</span><span class="sxs-lookup"><span data-stu-id="e400e-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="e400e-126">Klicka på **publicera etiketter**i fönstret **bevarande etiketter** .</span><span class="sxs-lookup"><span data-stu-id="e400e-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="e400e-127">Klicka på **Välj Etiketter**för publicering i fönstret **Välj etiketter för publicering** .</span><span class="sxs-lookup"><span data-stu-id="e400e-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="e400e-128">Klicka på **Lägg till** i fönstret **Välj Etiketter** och markera alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="e400e-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="e400e-129">Klicka på **Lägg till** och sedan på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="e400e-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="e400e-130">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e400e-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="e400e-131">Klicka på **Nästa** i fönstret **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="e400e-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="e400e-132">I fönstret **Namnge principen** skriver du **Organisationsexempel** i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e400e-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="e400e-133">Klicka på **publicera etiketter**i fönstret **Granska inställningar** .</span><span class="sxs-lookup"><span data-stu-id="e400e-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="e400e-134">Det kan ta några minuter innan bevarande etiketterna kan publiceras.</span><span class="sxs-lookup"><span data-stu-id="e400e-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="e400e-135">Fas 3: tillämpa behållnings etiketter i dokument</span><span class="sxs-lookup"><span data-stu-id="e400e-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="e400e-136">I den här fasen får du reda på standard beteendet för kvarhållande av filer i mappen dokument på en SharePoint Online-webbplats och manuellt ändra etiketten för ett dokument.</span><span class="sxs-lookup"><span data-stu-id="e400e-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="e400e-137">Börja med att skapa en grupp webbplats på känslig nivå:</span><span class="sxs-lookup"><span data-stu-id="e400e-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="e400e-138">Använd en privat instans av webbläsaren och logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="e400e-138">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="e400e-139">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="e400e-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e400e-140">Klicka på **Skapa webbplats** **på fliken nytt** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e400e-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="e400e-141">På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="e400e-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e400e-142">I **grupp webbplatsens namn**skriver du **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="e400e-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="e400e-143">I **grupp webbplats Beskrivning**skriver du **SharePoint-webbplats för känsliga filer**.</span><span class="sxs-lookup"><span data-stu-id="e400e-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="e400e-144">I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e400e-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e400e-145">I fönstret **vem vill du lägga till? klickar du** på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e400e-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="e400e-146">Sedan konfigurerar du mappen dokument på SensitiveFiles-grupp webbplatsen efter den känsliga behållnings etiketten.</span><span class="sxs-lookup"><span data-stu-id="e400e-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="e400e-147">Klicka på **dokument**på **SensitiveFiles** -fliken i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e400e-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e400e-148">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="e400e-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e400e-149">Under **behörigheter och hantering**klickar **du på tillämpa etikett på objekt i den här listan eller det här biblioteket**.</span><span class="sxs-lookup"><span data-stu-id="e400e-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="e400e-150">Om det här alternativet inte visas har dina bevarande etiketter ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="e400e-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="e400e-151">Prova det här steget senare.</span><span class="sxs-lookup"><span data-stu-id="e400e-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="e400e-152">I **Inställningar – Använd etikett**, Välj **känslig** i list rutan och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e400e-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="e400e-153">Skapa sedan ett nytt dokument på SensitiveFiles-webbplatsen och ändra etikettens etikett.</span><span class="sxs-lookup"><span data-stu-id="e400e-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="e400e-154">Klicka på **nytt > Word-dokument**i mappen dokument.</span><span class="sxs-lookup"><span data-stu-id="e400e-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="e400e-155">Skriv lite text i det tomma dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e400e-155">Type some text in the blank document.</span></span> <span data-ttu-id="e400e-156">Vänta tills texten har sparats.</span><span class="sxs-lookup"><span data-stu-id="e400e-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="e400e-157">Klicka på **delade dokument**i meny raden.</span><span class="sxs-lookup"><span data-stu-id="e400e-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="e400e-158">Klicka på den lodräta ellipsen bredvid **Document.docx** fil namn och klicka sedan på **information**.</span><span class="sxs-lookup"><span data-stu-id="e400e-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="e400e-159">I det högra fönstret, i avsnittet **Egenskaper** , under **tillämpa bevarande etikett**, ser du att dokumentet har den **känsliga** behållnings etiketten automatiskt tillämpad.</span><span class="sxs-lookup"><span data-stu-id="e400e-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="e400e-160">Klicka på **Redigera alla**.</span><span class="sxs-lookup"><span data-stu-id="e400e-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="e400e-161">Markera den **mycket konfidentiella** etiketten under **Använd bevarande etikett**i **Document.docx** fönstret och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e400e-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="e400e-162">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e400e-162">Next step</span></span>

<span data-ttu-id="e400e-163">Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="e400e-163">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e400e-164">Se även</span><span class="sxs-lookup"><span data-stu-id="e400e-164">See also</span></span>

[<span data-ttu-id="e400e-165">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e400e-165">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e400e-166">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e400e-166">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e400e-167">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="e400e-167">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
