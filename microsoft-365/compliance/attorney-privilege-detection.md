---
title: Konfigurera identifiering av behörigheter för juristklienter i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd modellen för identifiering av behörigheter i juristklienten om du vill använda maskininlärningsbaserad identifiering av behörighetsinnehåll när innehåll granskas i ett Advanced eDiscovery fall.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2020
ms.locfileid: "52161597"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="2f8fe-103">Konfigurera identifiering av behörigheter för juristklienter i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2f8fe-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="2f8fe-104">En viktig och kostsam del av granskningsfasen av en eDiscovery-process är att granska dokument för privilegierat innehåll.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="2f8fe-105">Advanced eDiscovery innehåller maskininlärningsbaserad identifiering av privilegierat innehåll för att effektivisera processen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="2f8fe-106">Den här funktionen kallas identifiering *av klientbehörighet för jurister.*</span><span class="sxs-lookup"><span data-stu-id="2f8fe-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="2f8fe-107">Hur fungerar det?</span><span class="sxs-lookup"><span data-stu-id="2f8fe-107">How does it work?</span></span>

<span data-ttu-id="2f8fe-108">När identifiering av juristklienter är aktiverat bearbetas alla dokument i en granskningsuppsättning av modellen för identifiering av behörigheter i juristklienten när du analyserar [data](analyzing-data-in-review-set.md) i uppsättningen med granskare.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="2f8fe-109">Modellen söker efter två saker:</span><span class="sxs-lookup"><span data-stu-id="2f8fe-109">The model looks for two things:</span></span>

- <span data-ttu-id="2f8fe-110">Privilegierat innehåll – I modellen används maskininlärning för att avgöra hur troligt det är att dokumentet innehåller innehåll som är lagligt.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="2f8fe-111">Deltagare – Som en del av inställningarna för identifiering av juristklienter måste du skicka en lista med jurister för organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="2f8fe-112">Modellen jämför sedan deltagarna i dokumentet med juristlistan för att avgöra om ett dokument har minst en juristdeltagare.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="2f8fe-113">Modellen ger följande tre egenskaper för varje dokument:</span><span class="sxs-lookup"><span data-stu-id="2f8fe-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="2f8fe-114">**AttorneyClientPrivilegeScore:** Sannolikheten att dokumentet är lagligt. värdena för poäng är mellan **0** och **1.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="2f8fe-115">**HasAttorney:** Den här egenskapen är **satt till sant** om en av dokumentdeltagarna finns med i juristlistan. annars är värdet **falskt.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="2f8fe-116">Värdet är också inställt på **falskt** om organisationen inte har laddat upp en juristlista.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="2f8fe-117">**IsPrivilege:** Den här egenskapen  är inställd på sant om värdet för **AttorneyClientPrivilegeScore** är över tröskelvärdet eller om dokumentet har en juristdeltagare.  annars är värdet **falskt.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="2f8fe-118">Dessa egenskaper (och deras motsvarande värden) läggs till i dokumentets metadata i en granskningsuppsättning, enligt skärmbilden nedan:</span><span class="sxs-lookup"><span data-stu-id="2f8fe-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Egenskaper för juristklientbehörighet visas i filens metadata](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="2f8fe-120">De här tre egenskaperna är också sökbara i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="2f8fe-121">Mer information finns i [Skapa en fråga för data i en granskningsuppsättning](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="2f8fe-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="2f8fe-122">Konfigurera modellen för identifiering av behörigheter i juristklienten</span><span class="sxs-lookup"><span data-stu-id="2f8fe-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="2f8fe-123">För att aktivera modellen för identifiering av behörigheter för juristklienten måste organisationen aktivera den och sedan ladda upp en juristlista.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="2f8fe-124">Steg 1: Aktivera identifiering av behörighet för juristklienten</span><span class="sxs-lookup"><span data-stu-id="2f8fe-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="2f8fe-125">En person som är eDiscovery-administratör i organisationen (medlem i undergruppen för eDiscovery-administratör i rollgruppen för eDiscovery-hanteraren) måste göra modellen tillgänglig i Advanced eDiscovery fall.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="2f8fe-126">I Säkerhets- & efterlevnadscenter går du till **eDiscovery > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="2f8fe-127">Klicka **Advanced eDiscovery** på Konfigurera globala **analysinställningar Inställningar** panelen på **startsidan för global analys.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Välj "Konfigurera experimentella funktioner"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="2f8fe-129">På fliken **Inställningar för analys** väljer du Hantera inställningen för **klientbehörighet för jurister.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="2f8fe-130">På den **utfällande sidan** med juristklienter använder du växlingsknappen för att aktivera funktionen och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="2f8fe-131">Steg 2: Upload en lista över jurister (valfritt)</span><span class="sxs-lookup"><span data-stu-id="2f8fe-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="2f8fe-132">För att till fullo utnyttja modellen för identifiering av  juristklienter  och använda resultaten från har juristen eller potentiellt privilegierad identifiering som beskrevs tidigare rekommenderar vi att du laddar upp en lista med e-postadresser för den medarbetare och juridisk personal som arbetar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="2f8fe-133">Så här laddar du upp en juristlista som ska användas med modellen för identifiering av behörigheter för juristklienten:</span><span class="sxs-lookup"><span data-stu-id="2f8fe-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="2f8fe-134">Skapa en .csv (utan rubrikrad) och lägg till e-postadressen för varje person på en separat rad.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="2f8fe-135">Spara filen på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="2f8fe-136">På **Advanced eDiscovery,** i panelen **Inställningar,** väljer du Konfigurera experimentella funktioner **och** sedan Hantera inställning för **klientbehörighet för jurister.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="2f8fe-137">Sidan **Med behörigheten Juristklient** visas och växlingsknappen för identifiering av **klientbehörighet** för jurist är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Utfällsida för juristklientbehörighet](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="2f8fe-139">Välj **Bläddra** och leta reda på och .csv filen som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="2f8fe-140">Välj **Spara** för att ladda upp juristlistan.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="2f8fe-141">Använda modellen för identifiering av behörigheter med juristklienter</span><span class="sxs-lookup"><span data-stu-id="2f8fe-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="2f8fe-142">Följ stegen i det här avsnittet för att använda identifiering av behörigheter för juristklienter för dokument i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="2f8fe-143">Steg 1: Skapa en smart etikettgrupp med modell för identifiering av behörigheter för juristklienter</span><span class="sxs-lookup"><span data-stu-id="2f8fe-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="2f8fe-144">Ett av de huvudsakliga sätten att visa resultatet av identifiering av behörigheter för juristklienter i granskningsprocessen är att använda en grupp med smarta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="2f8fe-145">En smart etikettgrupp visar resultatet av identifiering av behörigheter för juristklienten och visar resultatet på rad bredvid taggarna i en grupp med smarta etiketter.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="2f8fe-146">På så sätt kan du snabbt identifiera dokument som kan vara behöriga under dokumentgranskning.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="2f8fe-147">Du kan också använda taggarna i gruppen för smarta etiketter om du vill tagga dokument som behöriga eller icke-behöriga.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="2f8fe-148">Mer information om smarta etiketter finns i [Konfigurera smarta etiketter i Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="2f8fe-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="2f8fe-149">I granskningsuppsättningen som innehåller de dokument du analyserade i steg 1 väljer du **Hantera granskningsuppsättning** och sedan **Hantera taggar.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="2f8fe-150">Under **Taggar** väljer du 300-listan bredvid **Lägg till grupp** och väljer sedan Lägg till grupp för smarta **etiketter.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Välj "Lägg till smart tagggrupp"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="2f8fe-152">På sidan **Välj en modell för din smarta etikett** väljer du Välj **bredvid** Behörighet **för juristklient.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="2f8fe-153">En tagggrupp med **namnet Juristbehörighet** visas.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="2f8fe-154">Den innehåller två underordnade taggar med **namnet Positivt** **och** Negativt, som motsvarar möjliga resultat som skapas av modellen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Smart tagggrupp för juristklienter](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="2f8fe-156">Byt namn på tagggruppen och taggarna efter behov för din granskning.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="2f8fe-157">Du kan till exempel byta namn på **Positivt till** **Privilegierad och** Negativt **till** **Inte behörig.**</span><span class="sxs-lookup"><span data-stu-id="2f8fe-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="2f8fe-158">Steg 2: Analysera en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="2f8fe-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="2f8fe-159">När du analyserar dokumenten i en granskningsuppsättning körs även modellen för identifiering av juristklienter och motsvarande egenskaper (beskrivs i Hur fungerar [det?](#how-does-it-work) läggs till i alla dokument i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="2f8fe-160">Mer information om hur du analyserar data i en granskningsuppsättning finns i [Analysera data i en granskningsuppsättning Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="2f8fe-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="2f8fe-161">Steg 3: Använda gruppen för smarta etiketter för granskning av privilegierat innehåll</span><span class="sxs-lookup"><span data-stu-id="2f8fe-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="2f8fe-162">När du har analyserat granskningsuppsättningen och ställt in smarta etiketter är nästa steg att granska dokumenten.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="2f8fe-163">Om modellen har fastställt att dokumentet är potentiellt privilegierat visar motsvarande smarta etikett i panelen Märkning följande resultat som produceras av identifiering av behörigheter för juristklienten: </span><span class="sxs-lookup"><span data-stu-id="2f8fe-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="2f8fe-164">Om dokumentet har innehåll som kan vara  lagligt visas etiketten Juridiskt innehåll bredvid motsvarande smart etikett (vilket i det här fallet är standardinställningen **För** positiv etikett).</span><span class="sxs-lookup"><span data-stu-id="2f8fe-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="2f8fe-165">Om dokumentet innehåller en deltagare som finns med i organisationens juristlista visas etiketten Jurist bredvid motsvarande smart etikett (vilket i det här fallet också är standardinställningen positiv **etikett).** </span><span class="sxs-lookup"><span data-stu-id="2f8fe-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="2f8fe-166">Om dokumentet har innehåll som kan vara lagligt och det finns  en deltagare  i juristlistan visas både innehållet i juridiska frågor och etiketterna för jurister. </span><span class="sxs-lookup"><span data-stu-id="2f8fe-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="2f8fe-167">Om modellen avgör att ett dokument inte innehåller något juridiskt innehåll eller som inte innehåller en deltagare från juristlistan visas inget av etiketterna i märkningspanelen.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="2f8fe-168">Följande skärmbilder visar till exempel två dokument.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="2f8fe-169">Den första innehåller innehåll som är lagligt och innehåller en deltagare som finns med i listan över jurister.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="2f8fe-170">Det andra innehåller varken etiketter eller etiketter.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Dokument med etiketter för jurist och juridiskt innehåll](../media/AeDTaggingPanelLegalContentAttorney.png)

![Dokument utan etiketter](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="2f8fe-173">När du har granskat ett dokument för att se om det innehåller behörighetsinnehåll kan du tagga dokumentet med rätt tagg.</span><span class="sxs-lookup"><span data-stu-id="2f8fe-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
