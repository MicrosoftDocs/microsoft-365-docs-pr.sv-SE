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
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487738"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4918e-103">Data klassificering för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4918e-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4918e-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="4918e-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4918e-105">I den här artikeln beskrivs hur du konfigurerar data klassificering med hjälp av lagrings etiketter i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="4918e-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="4918e-106">Att klassificera data i test miljön inbegriper tre faser:</span><span class="sxs-lookup"><span data-stu-id="4918e-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="4918e-107">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4918e-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4918e-108">Fas 2: skapa behållnings etiketter</span><span class="sxs-lookup"><span data-stu-id="4918e-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="4918e-109">Fas 3: tillämpa behållnings etiketter i dokument</span><span class="sxs-lookup"><span data-stu-id="4918e-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4918e-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="4918e-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4918e-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4918e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4918e-113">Om du bara vill konfigurera behållnings etiketter på ett sätt som uppfyller minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4918e-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4918e-114">Om du vill konfigurera behållnings etiketter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4918e-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4918e-115">Det krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalog-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="4918e-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4918e-116">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="4918e-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="4918e-117">Fas 2: skapa behållnings etiketter</span><span class="sxs-lookup"><span data-stu-id="4918e-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="4918e-118">I den här fasen skapar du lagrings etiketterna för de olika nivåerna av bevarande för dokument i SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="4918e-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="4918e-119">Logga in på [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage) med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="4918e-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="4918e-120">Välj **klassificerings**etiketter på fliken **Start-Microsoft 365-säkerhet** i webbläsaren  >  **Retention labels**.</span><span class="sxs-lookup"><span data-stu-id="4918e-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="4918e-121">Välj **skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="4918e-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="4918e-122">Ange **intern offentlig** i **namn på etiketten**i rutan **namn på etiketten** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="4918e-123">I fönstret **fil Plans beskrivningar** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="4918e-124">I fönstret **etikett inställningar** , om det behövs, ange **Retention** **behållning till på**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="4918e-125">I fönstret **Granska inställningar** väljer du **skapa etiketten**.</span><span class="sxs-lookup"><span data-stu-id="4918e-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="4918e-126">Upprepa steg 3-7 för ytterligare etiketter med följande namn:</span><span class="sxs-lookup"><span data-stu-id="4918e-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="4918e-127">Privat</span><span class="sxs-lookup"><span data-stu-id="4918e-127">Private</span></span>
  - <span data-ttu-id="4918e-128">Känslig</span><span class="sxs-lookup"><span data-stu-id="4918e-128">Sensitive</span></span>
  - <span data-ttu-id="4918e-129">Strikt konfidentiellt</span><span class="sxs-lookup"><span data-stu-id="4918e-129">Highly Confidential</span></span>
1. <span data-ttu-id="4918e-130">Välj **publicera etiketter**i fönstret **bevarande etiketter** .</span><span class="sxs-lookup"><span data-stu-id="4918e-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="4918e-131">Välj vilka **etiketter du vill publicera**i fönstret **Välj etiketter för publicering** .</span><span class="sxs-lookup"><span data-stu-id="4918e-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="4918e-132">Välj **Lägg till** i fönstret **Välj Etiketter** och markera alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="4918e-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="4918e-133">Välj **Lägg till**och välj sedan **klar**.</span><span class="sxs-lookup"><span data-stu-id="4918e-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="4918e-134">I fönstret **Välj etiketter för publicering väljer du** **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="4918e-135">I fönstret **Välj platser** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="4918e-136">Ange **exempel organisation** i **namn**i fönstret **namn** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="4918e-137">Välj **publicera etiketter**i fönstret **Granska inställningar** .</span><span class="sxs-lookup"><span data-stu-id="4918e-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="4918e-138">Det kan ta några minuter innan bevarande etiketterna kan publiceras.</span><span class="sxs-lookup"><span data-stu-id="4918e-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="4918e-139">Fas 3: tillämpa behållnings etiketter i dokument</span><span class="sxs-lookup"><span data-stu-id="4918e-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="4918e-140">I den här fasen får du reda på standard beteendet för kvarhållande av filer i mappen dokument på en SharePoint Online-webbplats och manuellt ändra etiketten för ett dokument.</span><span class="sxs-lookup"><span data-stu-id="4918e-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="4918e-141">Börja med att skapa en grupp webbplats på känslig nivå:</span><span class="sxs-lookup"><span data-stu-id="4918e-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="4918e-142">Använd en privat instans av webbläsaren och logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="4918e-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="4918e-143">I listan över brickor väljer du **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4918e-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="4918e-144">Välj **Skapa webbplats**på fliken ny **SharePoint** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="4918e-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="4918e-145">Välj **grupp webbplats**på sidan **skapa en webbplats** .</span><span class="sxs-lookup"><span data-stu-id="4918e-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="4918e-146">I rutan **grupp webbplatsens namn** skriver du **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="4918e-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="4918e-147">I rutan **grupp webbplats Beskrivning** anger du **SharePoint-webbplats för känsliga filer**.</span><span class="sxs-lookup"><span data-stu-id="4918e-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="4918e-148">Välj **privata medlemmar**i **Sekretess inställningar**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="4918e-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="4918e-149">I fönstret **vem vill du lägga till? väljer du** **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="4918e-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="4918e-150">Sedan konfigurerar du mappen dokument på SensitiveFiles-grupp webbplatsen efter den känsliga behållnings etiketten.</span><span class="sxs-lookup"><span data-stu-id="4918e-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="4918e-151">På fliken **SensitiveFiles** i webbläsaren väljer du **dokument**.</span><span class="sxs-lookup"><span data-stu-id="4918e-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="4918e-152">Välj ikonen för **Inställningar** och välj sedan **biblioteks inställningar**.</span><span class="sxs-lookup"><span data-stu-id="4918e-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="4918e-153">Under **behörigheter och hantering**väljer **du Använd etikett för objekt i den här listan eller det här biblioteket**.</span><span class="sxs-lookup"><span data-stu-id="4918e-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="4918e-154">Om det här alternativet inte visas har dina lagrings etiketter ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="4918e-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="4918e-155">Prova det här steget senare.</span><span class="sxs-lookup"><span data-stu-id="4918e-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="4918e-156">I **Inställningar – Använd etikett**, Välj **känslig** i list rutan och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4918e-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="4918e-157">Skapa sedan ett nytt dokument på SensitiveFiles-webbplatsen och ändra etikettens etikett.</span><span class="sxs-lookup"><span data-stu-id="4918e-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="4918e-158">Välj **nytt**  >  **Word-dokument**i mappen dokument.</span><span class="sxs-lookup"><span data-stu-id="4918e-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="4918e-159">Skriv text i det tomma dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4918e-159">Enter some text in the blank document.</span></span> <span data-ttu-id="4918e-160">Vänta tills texten har sparats.</span><span class="sxs-lookup"><span data-stu-id="4918e-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="4918e-161">På Meny raden väljer du **delade dokument**.</span><span class="sxs-lookup"><span data-stu-id="4918e-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="4918e-162">Bredvid **Document.docx** fil namn väljer du den lodräta ellipsen och väljer sedan **information**.</span><span class="sxs-lookup"><span data-stu-id="4918e-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="4918e-163">I det högra fönstret, i avsnittet **Egenskaper** , under **tillämpa bevarande etikett**, ser du att dokumentet har den **känsliga** behållnings etiketten automatiskt tillämpad.</span><span class="sxs-lookup"><span data-stu-id="4918e-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="4918e-164">Klicka på **Redigera alla**.</span><span class="sxs-lookup"><span data-stu-id="4918e-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="4918e-165">Markera den **mycket konfidentiella** etiketten under **Använd bevarande etikett**i **Document.docx** fönstret och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4918e-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="4918e-166">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4918e-166">Next step</span></span>

<span data-ttu-id="4918e-167">Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="4918e-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4918e-168">Se även</span><span class="sxs-lookup"><span data-stu-id="4918e-168">See also</span></span>

[<span data-ttu-id="4918e-169">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4918e-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4918e-170">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="4918e-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4918e-171">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="4918e-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
