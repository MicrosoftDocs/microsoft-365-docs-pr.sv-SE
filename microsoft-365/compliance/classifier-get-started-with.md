---
title: Kom igång med utbildningsbara klassificerare
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En Microsoft 365 är ett verktyg som du kan utbilda dig för att identifiera olika typer av innehåll genom att ge den exempel att titta på. I den här artikeln beskrivs hur du skapar och utbildar en anpassad klassificerare och hur du utbildar dem för ökad precision.
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286639"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="06bdc-104">Kom igång med utbildningsbara klassificerare</span><span class="sxs-lookup"><span data-stu-id="06bdc-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="06bdc-105">En Microsoft 365 trainable classifier är ett verktyg som du kan träna för att känna igen olika typer av innehåll genom att ge det urval att titta på.</span><span class="sxs-lookup"><span data-stu-id="06bdc-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="06bdc-106">När du har utbildat dig kan du använda den för att identifiera objektet för tillämpning av Office känslighetsetiketter, principer för kommunikationsefterlevnad och bevarandeetiketter.</span><span class="sxs-lookup"><span data-stu-id="06bdc-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="06bdc-107">Om du skapar en egen utbildare för att klassificera den först ingår att ge det urval som människor har valt och som matchar kategorin positivt.</span><span class="sxs-lookup"><span data-stu-id="06bdc-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="06bdc-108">När de har bearbetats testar du sedan möjligheten att förutsäga klassificerarna genom att ge den en blandning av positiva och negativa prover.</span><span class="sxs-lookup"><span data-stu-id="06bdc-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="06bdc-109">I den här artikeln beskrivs hur du skapar och utbildar en anpassad klassificerare och hur du förbättrar prestanda för anpassade utbildare och föranpassade klassificerare under deras livstid genom omsämring.</span><span class="sxs-lookup"><span data-stu-id="06bdc-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="06bdc-110">Mer information om de olika typerna av klassificerare finns i [Läs mer om utbildare.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="06bdc-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="06bdc-111">Titta på den här videon för en snabb sammanfattning av hur du skapar en utbildande klassificerare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="06bdc-112">Du måste fortfarande läsa den här fullständiga artikeln för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="06bdc-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="06bdc-113">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="06bdc-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="06bdc-114">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="06bdc-114">Licensing requirements</span></span>

<span data-ttu-id="06bdc-115">Klassificerare är en funktion Microsoft 365 E5 regelefterlevnad eller E5-efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="06bdc-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="06bdc-116">Du måste ha en av dessa prenumerationer för att kunna använda dem.</span><span class="sxs-lookup"><span data-stu-id="06bdc-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="06bdc-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="06bdc-117">Permissions</span></span>

<span data-ttu-id="06bdc-118">Så här kommer du åt klassificerare i användargränssnittet:</span><span class="sxs-lookup"><span data-stu-id="06bdc-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="06bdc-119">Den globala administratören måste registrera sig för klientorganisationen för att skapa anpassade klassificerare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="06bdc-120">Efterlevnadsadministratörsroll krävs för att utbilda en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="06bdc-121">Du behöver konton med de här behörigheterna för att använda klassificerare i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="06bdc-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="06bdc-122">Scenario för bevarandeprincip: Roller för arkiveringshantering och bevarandehantering</span><span class="sxs-lookup"><span data-stu-id="06bdc-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="06bdc-123">Scenario för känslighetsetikettsprincip: Säkerhetsadministratör, efterlevnadsadministratör, efterlevnadsdataadministratör</span><span class="sxs-lookup"><span data-stu-id="06bdc-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="06bdc-124">Scenario: Scenario för kommunikationsefterlevnadspolicy: Insider-riskhanteringsadministratör, övervakande granskningsadministratör</span><span class="sxs-lookup"><span data-stu-id="06bdc-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="06bdc-125">Som standard kan endast den användare som skapar en anpassad klassificerare utbilda och granska prognoser som gjorts av den klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="06bdc-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="06bdc-126">Förbereda en egen utbildare</span><span class="sxs-lookup"><span data-stu-id="06bdc-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="06bdc-127">Det är bra att förstå vad som ingår i att skapa en egen utbildare innan du dyker ned.</span><span class="sxs-lookup"><span data-stu-id="06bdc-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="06bdc-128">Tidslinje</span><span class="sxs-lookup"><span data-stu-id="06bdc-128">Timeline</span></span>

<span data-ttu-id="06bdc-129">Den här tidslinjen återspeglar ett exempel på distribution av utbildande klassificerare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="06bdc-131">Avanmälning krävs första gången för utbildare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="06bdc-132">Det tar tolv dagar Microsoft 365 att slutföra en baslinjeutvärdering av organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="06bdc-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="06bdc-133">Kontakta din globala administratör för att starta processen med att anmäla dig.</span><span class="sxs-lookup"><span data-stu-id="06bdc-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="06bdc-134">Övergripande arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="06bdc-134">Overall workflow</span></span>

<span data-ttu-id="06bdc-135">Mer information om det övergripande arbetsflödet för att skapa anpassade utbildare finns i Processflöde för att skapa anpassade klassificerare som [kan klassificeras av kunder.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="06bdc-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="06bdc-136">Startinnehåll</span><span class="sxs-lookup"><span data-stu-id="06bdc-136">Seed content</span></span>

<span data-ttu-id="06bdc-137">När du vill att en utbildare ska klassificera ett objekt oberoende av varandra och korrekt identifiera det som en viss kategori av innehåll måste du först presentera det med många exempel på den typ av innehåll som ingår i kategorin.</span><span class="sxs-lookup"><span data-stu-id="06bdc-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="06bdc-138">Denna matning av prover till den utbildande klassificeraren kallas för *ifogning*.</span><span class="sxs-lookup"><span data-stu-id="06bdc-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="06bdc-139">Lägga till innehåll väljs av en person och ska nu representera innehållskategorin.</span><span class="sxs-lookup"><span data-stu-id="06bdc-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="06bdc-140">Du måste ha minst 50 positiva tal och upp till 500.</span><span class="sxs-lookup"><span data-stu-id="06bdc-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="06bdc-141">Den utbildande klassificeraren bearbetar upp till de 500 senaste skapade exemplen (som skapas av filen som skapats med datum- och tidsstämpeln).</span><span class="sxs-lookup"><span data-stu-id="06bdc-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="06bdc-142">Ju fler exempel du anger, desto mer exakta är de prognoser som klassificeraren gör.</span><span class="sxs-lookup"><span data-stu-id="06bdc-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="06bdc-143">Testa innehåll</span><span class="sxs-lookup"><span data-stu-id="06bdc-143">Testing content</span></span>

<span data-ttu-id="06bdc-144">När den utbildande klassificeraren har hanterat tillräckligt positiva prover för att skapa en prognosmodell måste du testa de prognoser som den gör för att se om klassificeraren på ett korrekt sätt kan skilja mellan objekt som matchar kategorin och objekt som inte har det.</span><span class="sxs-lookup"><span data-stu-id="06bdc-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="06bdc-145">Det gör du genom att välja en annan, förhoppningsvis större, uppsättning människor som har hämtats innehåll som består av prover som bör gå in i kategorin och exempel som inte kommer att det.</span><span class="sxs-lookup"><span data-stu-id="06bdc-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="06bdc-146">Du bör testa med andra data än de ursprungliga startdata som du angav först.</span><span class="sxs-lookup"><span data-stu-id="06bdc-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="06bdc-147">När de har hanterats går du manuellt igenom resultatet och kontrollerar om varje prognos är korrekt, felaktig eller osäker.</span><span class="sxs-lookup"><span data-stu-id="06bdc-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="06bdc-148">Den utbildande klassificeraren använder den här feedbacken för att förbättra sin prognosmodell.</span><span class="sxs-lookup"><span data-stu-id="06bdc-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="06bdc-149">För bästa resultat bör du ha minst 200 objekt i testuppsättningen med en jämn fördelning av positiva och negativa matchningar.</span><span class="sxs-lookup"><span data-stu-id="06bdc-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="06bdc-150">Så här skapar du en utbildare</span><span class="sxs-lookup"><span data-stu-id="06bdc-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="06bdc-151">Samla in mellan 50–500 startinnehållsobjekt.</span><span class="sxs-lookup"><span data-stu-id="06bdc-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="06bdc-152">Det får endast vara exempel som verkligen representerar den typ av innehåll som du vill att den utbildande klassificeraren ska identifiera som i klassificeringskategorin.</span><span class="sxs-lookup"><span data-stu-id="06bdc-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="06bdc-153">Se [Filnamnstillägg och filtyper som crawlas som](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) standard i SharePoint server för filtyper som stöds.</span><span class="sxs-lookup"><span data-stu-id="06bdc-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="06bdc-154">Start- och testobjekt får inte krypteras och måste vara på engelska.</span><span class="sxs-lookup"><span data-stu-id="06bdc-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="06bdc-155">Kontrollera att elementen i startuppsättningen **är starka** exempel på kategorin.</span><span class="sxs-lookup"><span data-stu-id="06bdc-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="06bdc-156">Den utbildande klassificeraren skapar först sin modell baserat på vad du tillskriver den.</span><span class="sxs-lookup"><span data-stu-id="06bdc-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="06bdc-157">Klassificeraren antar att alla startprov är starka positiva tal och det går inte att se om ett sampel är en svag eller negativ matchning för kategorin.</span><span class="sxs-lookup"><span data-stu-id="06bdc-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="06bdc-158">Placera startinnehållet i en SharePoint Online-mapp som är avsedd att endast *hålla startinnehåll.*</span><span class="sxs-lookup"><span data-stu-id="06bdc-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="06bdc-159">Notera URL-adressen till webbplatsen, biblioteket och mappen.</span><span class="sxs-lookup"><span data-stu-id="06bdc-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="06bdc-160">Om du skapar en ny webbplats och mapp för dina startdata bör du tillåta minst en timme för indexeringen av platsen innan du skapar den trainable-klassificerare som använder dessa tillåtna data.</span><span class="sxs-lookup"><span data-stu-id="06bdc-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="06bdc-161">Logga in på Microsoft 365 Efterlevnadscenter med rollåtkomst från efterlevnadsadministratör eller säkerhetsadministratör och öppna **Microsoft 365 Efterlevnadscenter** eller **Microsoft 365 säkerhetscenter**  >  **Dataklassificering.**</span><span class="sxs-lookup"><span data-stu-id="06bdc-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="06bdc-162">Välj **fliken Utbildare.**</span><span class="sxs-lookup"><span data-stu-id="06bdc-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="06bdc-163">Välj **Skapa utbildare .**</span><span class="sxs-lookup"><span data-stu-id="06bdc-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="06bdc-164">Fyll i lämpliga värden för och fälten för kategorin objekt som du vill att den här `Name` `Description` utbildande klassificeraren ska identifiera.</span><span class="sxs-lookup"><span data-stu-id="06bdc-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="06bdc-165">Välj URL SharePoint för onlinewebbplats, bibliotek och mapp för startinnehållswebbplatsen från steg 2.</span><span class="sxs-lookup"><span data-stu-id="06bdc-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="06bdc-166">Välj `Add` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-166">Choose `Add`.</span></span>

8. <span data-ttu-id="06bdc-167">Granska inställningarna och välj `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="06bdc-168">Inom 24 timmar bearbetar den utbildande klassificeraren startdata och skapar en prognosmodell.</span><span class="sxs-lookup"><span data-stu-id="06bdc-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="06bdc-169">Klassificerarstatusen är när `In progress` den bearbetar startdata.</span><span class="sxs-lookup"><span data-stu-id="06bdc-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="06bdc-170">När klassificeraren har bearbetat startdata ändras statusen till `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="06bdc-171">Du kan nu visa informationssidan genom att välja klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="06bdc-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06bdc-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="06bdc-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="06bdc-173">Samla in minst 200 testinnehållsobjekt (10 000 max) för bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="06bdc-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="06bdc-174">Det bör vara en blandning av objekt som är starka positiva, starka negativa och vissa som till sin natur är lite mindre uppenbara.</span><span class="sxs-lookup"><span data-stu-id="06bdc-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="06bdc-175">Se [Filnamnstillägg och filtyper som crawlas som](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) standard i SharePoint server för filtyper som stöds.</span><span class="sxs-lookup"><span data-stu-id="06bdc-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="06bdc-176">Exempelobjekten får inte krypteras och måste vara på engelska.</span><span class="sxs-lookup"><span data-stu-id="06bdc-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="06bdc-177">Placera testinnehållet i en mapp SharePoint online som endast ska användas för *att hålla testinnehållet.*</span><span class="sxs-lookup"><span data-stu-id="06bdc-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="06bdc-178">Notera URL-adressen SharePoint Online, bibliotek och mapp.</span><span class="sxs-lookup"><span data-stu-id="06bdc-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="06bdc-179">Om du skapar en ny webbplats och mapp för dina testdata ska det ta minst en timme innan den platsen indexeras innan du skapar den trainable-klassificerare som använder dessa startdata.</span><span class="sxs-lookup"><span data-stu-id="06bdc-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="06bdc-180">Välj `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="06bdc-181">Välj URL SharePoint för webbplatsen, biblioteket och mappen Online för testinnehållswebbplatsen från steg 12.</span><span class="sxs-lookup"><span data-stu-id="06bdc-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="06bdc-182">Välj `Add` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-182">Choose `Add`.</span></span>

15. <span data-ttu-id="06bdc-183">Slutför guiden genom att välja `Done` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="06bdc-184">Det tar upp till en timme innan testfilerna bearbetas med din utbildare.</span><span class="sxs-lookup"><span data-stu-id="06bdc-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="06bdc-185">När den utbildande klassificeraren har bearbetat dina testfiler ändras statusen på informationssidan till `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="06bdc-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="06bdc-186">Om du behöver öka testprovstorleken väljer och tillåter du att den utbildande `Add items to test` klassificeraren bearbetar de ytterligare objekten.</span><span class="sxs-lookup"><span data-stu-id="06bdc-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06bdc-187">![skärmbild som är klar att granskas](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="06bdc-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="06bdc-188">Välj `Tested items to review` flik för att granska objekt.</span><span class="sxs-lookup"><span data-stu-id="06bdc-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="06bdc-189">Microsoft 365 med 30 objekt åt gången.</span><span class="sxs-lookup"><span data-stu-id="06bdc-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="06bdc-190">Granska dem och välj ett `We predict this item is "Relevant". Do you agree?` eller `Yes` eller i `No` `Not sure, skip to next item` rutan.</span><span class="sxs-lookup"><span data-stu-id="06bdc-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="06bdc-191">Modellprecisionen uppdateras automatiskt efter var 30:e post.</span><span class="sxs-lookup"><span data-stu-id="06bdc-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06bdc-192">![rutan granska objekt](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="06bdc-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="06bdc-193">Granska *minst* 200 objekt.</span><span class="sxs-lookup"><span data-stu-id="06bdc-193">Review *at least* 200 items.</span></span> <span data-ttu-id="06bdc-194">När korrekthetsresultatet har visats blir **publiceringsalternativet** tillgängligt och det visas som klassificerares `Ready to use` status.</span><span class="sxs-lookup"><span data-stu-id="06bdc-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06bdc-195">![precisionspoäng och redo att publiceras](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="06bdc-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="06bdc-196">Publicera klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="06bdc-196">Publish the classifier.</span></span>

21. <span data-ttu-id="06bdc-197">När du publicerat din klassificerare blir tillgänglig som ett villkor [i Office](apply-sensitivity-label-automatically.md)automatisk märkning med känslighetsetiketter [tillämpar](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) du bevarandeprincip automatiskt utifrån ett villkor och i [kommunikationsefterlevnad.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="06bdc-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
